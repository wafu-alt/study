출처 : 엘리스 SW엔지니어 트랙



# 1. 실행컨텍스트와 스코프

- 참조할 수 있는 유효범위를 의미
- 전역, 지역 스코프

### 중괄호 → 블록이 경계선이 된다

```jsx
let x = 0; //글로벌

	function ex1() { //지역2
	let x = 1;

		function ex2() { // 지역1
		let x = 2;
		}
	ex2();
}
ex1();
```
## 실행컨텍스트(Execution Context) 란?

- 실행 가능한 코드가 실행되기 위해 필요한 환경(객체형태) : 실행환경 , 자바스크립트 돌아가는 환경
- 변수, 함수, 스코프(scope), this
- 코드를 형상화하고 구분하는 추상적 개념임(찍어서 확인하기가 힘듬)
- 코드가 실행시 생성되고, 완료되면 소멸됨

### 3가지 종류

- 전역 실행 컨텍스트(Global Execution Context)
- 함수 실행 컨텍스트(Function Execution Context)
- ~~Eval 실행컨텍스트(Eval Execution Context)~~ - 거의 안씀

## 스택구조

```jsx
function ex1() {
	function ex2() {}
	ex2();
}
ex1();//호출해야 실행 컨텍스트에 쌓임
```
![1](https://user-images.githubusercontent.com/83447120/177237449-5609606e-3b2d-4874-9846-f5981c398835.jpg)
- 글로벌은 무조건 생겨서 밑에 깔려 있음

## 실제로어떤값이들어있나?

- 추상적 개념이므로 추상적으로 객체처럼 표현한 것임!
- 컨텍스트가 만들어지는 상황에 따라 값이 바뀌어 들어갈 예정

```jsx
"Context": {
	variableObject: { //모든 변수가 들어감
		arguments: null, //변수 넘겨 받는 곳
		variable: [...], //담기는 곳
	},
	scopeChain: ["해당 되는 스코프"],
	this: "함수가 호출된 형태에 따라 할당"
}
```

## Lexical Scope

- 함수 호출이 아닌 함수 선언한 곳을 기준으로 스코프를 결정 : 정적 스코프
- 지역 스코프내에서  전역 스코프에 접근 불가

```jsx
let x = 0;

//실행
function ex1() { 
	let x = 1;
	console.log(x); //1
	ex2(); //호출 //1(x) -> 0
}

//실행 선언이 글로벌에서 되었기 때문에 
//funcEx1의 x=1접근 못함
function ex2() { 
	console.log(x);
}
ex1(); //호출
```
## Scope Chain

- 클로저가 가능한 기본 개념

```jsx
let x = 1;
let y = 2;
	function ex1() {
		let x = 3;
		function ex2() {
			console.log(x); //3 ex1에 영향 받음
			console.log(y); //2 
		//ex1은 y값이 따로 설정 안되어있어서 글로벌을 가져옴
		//앞쪽 스코프를 가져온다고 해서 chain
	}
	ex2();
}
ex1();
```

- 함수 선언(정의)될 때 메모리에 담기는데 scope가 (생성)결정이 됨
- 스코프의 레퍼런스가 차례로 저장된 리스트
# 2. 호이스팅과 this

- 실행 컨텍스트는 2단계를 거쳐 수행됨
1. 생성단계(creation Phase) 
  scope정보 및 this생성,  메모리 공간을 확보(선언)
2. 실행단계(Execution Phase)
 실제코드가 1줄씩 실행되는 단계, 변수에 값을 할당(할당)

## 호이스팅

- 코드 실행 전, 변수/함수 선언이 해당 스코프의 최상단으로 끌어올려진 것 같은 현상
- 실행전 : 코드 실행
- 변수,함수 선언 : 메모리 공간 확보

```jsx

// 1. 함수 선언
function insertText(text) {
	document.write(text);
	return "ok";
}

// 2. 함수 표현식
// 함수는 호이스팅 되지않음
let insertText = function(text) {
	document.write(text);
	return "ok";
}
//처음 함수선언식과 변수 선언만 호이스팅 되고
//함수표현식으로 변수의 메모리에 할당됨
```

```jsx
let name = "John";

var getName = function() {
	console.log(name); //undefined

	var name = "Bob"; //let으로 바뀌면 아예 에러남
	console.log(name); //Bob
}
getName ();

```
## this가 가리키는 것

1. Global Context - 여기서(브라우저기준) this는window를 의미함 = 웹에서는 브라우저
2. Function Context - 함수를 호출하는 방법에 따라 달라짐

```jsx
function example() {
	return this.a; // window를 가리킴. 함수를 가릴킬순 없음
}
window.example() //window는 생략이 가능
```
### bind

```jsx
let person = {
	name: "John",
	hello: function() {
		console.log(`Hi, ${this.name}`);
	}
}
person.hello(); // Hi, John 
let newHello = person.hello;
newHello();//window가리켜서 에러 혹은 무시해서 공백

name = "park";
newHello();// Hi, park window 네임을 팍을 저장됨
```

```jsx
let person = {
	name: "John",
	hello: function() {
		console.log(`Hi, ${this.name}`);
	}
}
let newHello = person.hello;
newHello = newHello.bind(person);//앞것을 묶어서 복사함
newHello();// Hi, John 

person.name = "Park";
newHello(); // Hi, Park
```
- bind(ES5개념)는 묶어서 계속 연결될 수 있게 함

```jsx
let person = {
	name: "John",
	hello: function() {
		console.log(`Hi, ${this.name}`);
	}
}
setTimeout(person.hello, 1000); // Hi, 공백
//1초후 함수 실행
//실행컨텍스트가 종료되고 함수가 실행됨(window를 가리킴)

//클로저를 활용해서 해결가능
```

- 1초 후에 실행하기위해 다른 영역에서 보관하다보니 실행컨테스트가 끝나서 빈곳을 가르키게 됨
- 실행이 쭉 되다가 setTimeout은 따로 실행이되다보니 쭉 실행이 됬을때는 john을 가리키다가. setTimeout이 실행될 차례일때는 john이 사라져서 window를 가리킨다
- 호이스팅 → 기존 코드 실행 → 이후 후처리 함수 실행


# 3. 클로저(Closure) 이해하기

- 함수와 그 함수가 선언 됐을 때의 레시컬(Lexcial) 환경과의 조합
- 자신이 선언될 당시의 환경을 기억하는 함수 - bind와 비슷한 느낌?

```jsx
function outer() {
	let x = 10;
	let inner = function () {
			console.log(x);
		}
	inner(); //호출
}
outer();

// 클로저 사용
function outer() {
	let x = 10;
	let inner = function () {
		console.log(x);
	}
	return inner; //리턴유무 호출하지않고, innerFunc 로 들어감, outer컨텐스트 사라짐
//outer 컨테스트가 소멸되더라도 메모리는 회수 안되고 inner()은 outer를 계속 참조하고 있음
//갈비지컬랙터 GC 메모리 회수하는 로직
}
let innerFunc = outer(); //함수표현식 ,  innerFunc 로 들어간 후에
innerFunc(); // 이때 호출되면서 컨텐스트(context)가 쌓임
```

```jsx
function clickHandler() {
  let count = 0; //변수 선언으로 메모리 배당이 되고

  return function () {
    count++;

    console.log(count);
  };
}

const handler = clickHandler();//return되는 count++;,console.log(count);만 남아있음
//변수count 메모리 배당을 남겨놓고 계속 활용함

let count = 0; //메모리 계속 남아있음 하지만 위에것과 같은 동작함
//단점 : 다른곳에서 count 변수 못씀
function clickHandler2 () {
	 count++;
   console.log(count);
}

const countUpBtn = document.querySelector(".count-up-btn");
countUpBtn.addEventListener("click", handler);
countUpBtn.addEventListener("click", clickHandler2 );
```

```jsx
function showHelp(help) {
  document.getElementById("help").innerHTML = help;
}

function setupHelp() {
  var helpText = [
    { id: "email", help: "Your e-mail address" },
    { id: "name", help: "Your full name" },
    { id: "age", help: "Your age (you must be over 16)" },
  ];
  for (var i = 0; i < helpText.length; i++) {
    var item = helpText[i];

// 문제발생점
// item이 변경되는 것이 독립적이지 못함
    document.getElementById(item.id).onfocus = function () {
      showHelp(item.help); //item부분을 독립적 시켜줘야함
	
    };
	//showhelp를 독립시킴
	//document.getElementById(item.id).onfocus = makeHelpCallback(item.help);
  }
}

// function makeHelpCallback(help) {
// 	return function() {
// 		showHelp(help);
// 	};
// }

setupHelp();
```
# 4. 고차원함수

- 함수를 인자로 받거나 리턴하는 함수
- 자바스크립트 대부분 함수가 고차원 함수임
- 내부적으로 클로저 환경을 쓰고있음

## map() , reduce() - 서로 반대됨

- 배열 중 각각 하나씩 따로 처리하고 다시 합칠 수 있는 함수
- 활용도가 매우 높고, 원본 값을 변경하지 않는 점이 매우 좋음

```jsx
let nums = [1,2,3,4,5];
let result = nums.map(num => num*2); // = function (num) {return num*2;}
// map이 배열 요소를 하나씩 매개변수로 넘겨줌

let users = [
	{ id : 1, name : "james' },
	{ id : 2, name : "james' },
	{ id : 3, name : "james' },
];
let names = users.map(
	user => user.name;
);
```
## reduce함수

- 각 요소를 돌며 누적으로 수행하는 함수

```jsx
let nums = [1,2,3,4,5];
const initialValue =0;
let res nums.reduce(
	(prevNum , nextNum) => prevNum + nextNum,
	initialValue
);
console.log(res); //15

// reduce 옵션
let res nums.reduce(
	(누적값, 현재요소값, 인덱스값, 배열) => 누적값+ 현재요소값,
	초기값
);
```

- map 뭔가를 추출하고, reduce는 추출 된 것을 합친다.
    
    예를 들어 wordCount
    
    #map은 input : 문장 , 문장을 단어 단위로 쪼개고 count증가 , 반환 : { 단어 : 1 }
    
    #reduce input :  { 단어 : 1 }, 같은 단어가 들어오면 count증가, 반환 : 마지막으로 누적된 값
    
    ⇒ 특정 단어1 : 20394 , 특정 단어2 : 2948 같은 통계를 얻을 수 있음

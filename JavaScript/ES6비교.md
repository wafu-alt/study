## es6과 이전과 비교

```jsx
//let, const 
//상수와 변수 구분이 없음
var TITLE = 'NODE.JS';
var director = 'elice';
director = 'rabbit';
TITLe = 'ES6'// 오류 없음

//ES6 상수와 변수 구분 가능
const TITLE = 'NODE.JS'; // 상수 선언가능
let director = 'elice';
director = 'reabbit';
TITLE = 'ES6'//오류발생
```

```jsx
//Tenokate String
var name = 'elice';
var age = 5;
	//+를 사용해 문자열과 변수 연결
	//줄 바꿈 문자 \n사용 필요
var hi = 'My name is '
	+ name
	+ '.\n I\'m '
	+ age
	+ 'years old.';
console.log(hi);

//ES6 
const name = 'elice';
const age = 5;
	//문자열 사이에 간단하게 변수 사용가능
	//따옴표 간단하게 사용가능
	//줄 바꿈 지원
const hi =
`My name is ${name}.
I'm ${age} years old`;
console.log(hi);
```

```jsx
//arrow function
//기본 함수 표현 방법
function doSomthing (param){
	console.log('do something');
}

//익명함수 표현 방법
setTimeout(function(param) {
	console.log('no name fucntion');
}, 0)

//함수 새로 선언가능
function doSomething() {
	console.log('do other');
}

//ES6 
//상수형으로 표현가능
const doSomthing = (param) => {
	console.log('do something');
}

//익명함수 간결하게 표현 가능
setTimeout((param) => {
	console.log('no name function');
}, 0)

//함수 새로 선언 불가능
doSomething = () => { //const 상수에 담을 수 있어서 오류 발생, 중복 피함
	console.log('do other');
}
```

```jsx
//class
function Model (name, age) {
	this.name = name;
	this.age = age;
}
//prototype으로 class함수 구현
Model.prototype.getInfo = function() {
	console.log(this.name, this.age);
}
var model = new Model('elice', 5);
model.getInfo();

//ES6
//일반적인 형태의 class구현 가능
class Model {
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}
	getInfo() {
		console.log(this.name, this.age);	
	}
}
const model = new Model('elice', 5);
model.getInfo();
```

```jsx
//destructing
var obj = {name:'elice' , age:5};
var name = obj.name;
var age = obj.age;

var arr = ['some' , 'values'];
var first = arr[0];
var second = arr[1];

//ES6
const obj = {name:'elice' , age:5};
//Object의 key와 같은 이름으로 변수 선언 가능
const {name, age} = obj;
//다른 이름으로 변수 선언하는 방법
const {name:n1, age:a1} = obj;

const arr = ['some' , 'values'];
//arr에서 순차적으로 변수 선언 가능
const [first , second] = arr;
```

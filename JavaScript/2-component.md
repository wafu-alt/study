출처 : 엘리스 SW엔지니어 트랙
# 1. 컴포넌트

## 컴포넌트(component)란?

- 검색 나온 것들 컴포넌트.
- 캡슐화를 통해하여 재사용이 가능한 독립된 모듈
- 틀을 만들고 비슷한 내용을 바꿔주기만 한다.
- 어디다가 넣어도 모습 그대로 유지 (독립) 깨지거나 변형 xx
- 조각들을 조합해서 하나의 웹사이트로 보여주는 개념
- 라이브러리도 결과적으로는 같은 개념

## export와 default export

- 함수, 객체, 원시(1,2, string ..) 값을 내보냄
- 다른 파일에서 import로 가져올 수 있음
- default는 한번만 사용가능 (사용할거면 하나, 안써도 됨)
- as로 이름 바꿔서 보낼 수 있음
- default를 주로 사용

## import

- 다른 모듈에서 내보낸 것을 가져올때 사용
- 가져올때는 중괄호{} 감싸서 가져와야함
- import + from 결합
- “*”을 사용하여 내보내진 모든 값을 가져올 수 도 있음 + as해서 이름 정해져줘야함
- default로 내보낸 것을  import에서 {}없이 가져와서 이름을 정해주고 씀
- html에서 타입 모듈 설정 중요!

참조 : 01-02
## 컴포넌트화 해보자 (모듈화)

참조 : \code\01-02\1 , 완성은 \code\practice-01

1. components폴더 만들기
2. header, mian, footer 로 나눌 것임
3. 각 header, mian, footer .js만들고 그 안에 html을 잘라내서 붙임

```jsx
//js 다른 main. footer.js도 같은 형태
const htmlStr = `
<header>
    <nav>
    <ul>
        <li class="menu-btn"><a href="#">홈</a></li>
        <li class="menu-btn"><a href="#">이력서</a></li>
        <li class="nav-space"></li>
        <li>/*elice*/</li>
    </ul>
    </nav>
</header>
`;

let ex1 = "ex1";
export { ex1 }; // 섞어서 불러올 수 있음
//import Header,{ex1} from "./components/Header.js"; 으로 가져올것
export default htmlStr;
```

4. 불러오기

```jsx
import Header from "./components/Header.js";
import Main from "./components/Main.js";
import Footer from "./components/Footer.js";
```

5. reat.js에서는 컴퍼넌트를 어플리케이션으로 봐서 . main.js에서 불러와서 사용

```jsx
//html
<div id="app"></div>

//js
const app = document.getElementById("app");
app.innerHTML = `
${Header}
${Main}
${Footer}
`;
```
# 변수에 대해 더 깊이 알기

## Arrow function(ES6)

참조 : \code\03

- 기존의 함수를 간단하게 사용 할 수 있음 = 축약
예시) onclick많이 씀,  map 많이 씀
- 대신 몇가지 제한점이 존재
    - this값이 바인딩되지 않음
    - 생성자를 사용할 수 없음
- 파라미터가 1개일대 괄호() ⇒ 중괄호{} 생략 가능
- 함수명이 없기때문에 변수에 화살함수를 담아서 호출해서 사용해야함

```jsx
const hello = (name) => {
    return `Hi, ${name}`;
}
// 파라미터1개 = 괄호 생략
const hello = name => `Hi, ${name}`;
```
- this안됨

```jsx
function printHello() {
    console.log(this);
}

const helloBtn = document.getElementById("hello");
helloBtn.onclick = printHello;
// helloBtn.onclick = () => {
//     console.log(this); //window 찍힘
// };
```

- 이것말고 더 제한점이 있음
## Truthy / Falsy

- boolean이 필요할 때, 어떻게 판단하는지 ?
정의된 값들이 있음
- Truthy는 Falsy가 아닌 모든 값임

## 객체

참조 :  \code\practice-02

- 객체는 데이터와 함수의 집합
- 값을 가진 것을 프로퍼티property
- 함수를 가진 것을 메소드method
- 객체 리터럴 Object Literal  = 객체 형태를 담은 형태

### for문의 in과 of

```jsx
for (let i =0; i<myProfile.skill.length; i++) {
    console.log(myProfile.skill[i];)
}
for (let i in myProfile.skill) {
    console.log(myProfile.skill[i];)
}
for (let i of myProfile.skill) {
    console.log(myProfile.skill[i];)
}
```

- in은 i에 대한 배열 수 인덱스 받아옴
- of은 값의 덩어리를 들고옴

```jsx
let arr = [5,6,7,8];
for (let i =0; i < arr.length; i++){
    console.log(arr[i]);
}

for (let i in arr) {
    console.log(`${i} : ${arr[i]}`); // key값 가져옴
}

//의미적으로 같음
let arr1 = {
    0:5,
    1:6,
    2:7,
    3:8,
};

for (let key in arr1) {
    console.log(arr[key]); // key값 가져옴
}
for (let value of arr1) {
    console.log(value[i]); // key의 벨류값 가져옴
}
```
## 객체와 const

참조 : \code\05 (오후라서 다시 다운받아서 넣을것)

- const있으면 상수일때 많이 쓰는데 객체일때도 사용한다
- 메모리에 주소값이고 값에도 주소값이 들어가고 그 주소값을 따라가보면 진짜 값이 있음
- 객체의 하나에 키 값에 대입으로 바꾸는건 가능
- 객체 전체에서 값을 바꾸는건 불가

```jsx
console.log({} === {}); 
//false 객체 간에 서로 다른 메모리 주소값이라서 같지 않음
```

## 얇은 복사, 깊은 복사

- 객체인지 주소인지

```jsx
//객체 얇은 복사
const newPerson = person;
newPerson.name = "newPerson";
console.log(newPerson); 했을때 person내용도 수정이 됨

//객체 깊은 복사
const deepCopyPerson = JSON,parse(JSON.stringify(person));
객체를 문자열로 바꾸고 그것을 다시 새로운 객체로 만듦
```
## rest / spread   
- 반복 가능한 객체를 여러개 요소로 펼치거나spread 모아주는rest 방법
- 배열 혹은 객체 리터럴에서 사용가는 (객체는 ES2018부터)

```jsx
let arr = [1, 2, 3];
let newArr = [...arr, 4, 5]; // spread 사용
//[1,2,3] + [4,5]
console.log(newArr);

let [a, b, c, d, e] = newArr;
console.log(a);

let [first, ...rest] = newArr; // rest 사용 destructure
//첫번째만 가져옴, rest아닌 tmp적어도 가능
console.log(first);
```
## Class란?

- 기본 개념 , 상속까지 설명
- 객체를 생성하기 위한 템플릿
- constructor : 생성된 객체를 초기화하기 위한 특수한 함수 (예약어, 생성자)
- 변수 이름만, 함수 이름만 적음 다 생략됨

## Instance란?

- 클래스 : 레시피
- 인스턴스 : 레시피로 만들어진 요리
- new를 쓰면 새로운 객체가 만들어짐
- 같은 클래스로 만들어진 인스턴스는 모두 같은 프로퍼티와 메소드를 가짐

set, get 

객체 지향 , 일괄적으로 하게 만드는 함수

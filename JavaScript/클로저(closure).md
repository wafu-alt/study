참조 : [https://www.youtube.com/watch?v=bwwaSwf7vkE](https://www.youtube.com/watch?v=bwwaSwf7vkE) 생활코딩

```jsx
// 지역 스코프 판단
let a0 = "a0";

function fn1() {
  let a1 = "a1";
}

fn1();
console.log(a0); //a0
console.log(a0, a1); // Uncaught ReferenceError: a1 is not defined
/*
fn1의 값을 가지고 못나옴
*/

// 실험1
let a0 = "a0";

function fn1() {
  let a1 = "a1";
  console.log(a0, a1);
}

fn1();
/*
밖에서 만든 a0가 fn1함수까지 영향을 미친다
fn1는 local scope인데 a0를 찾지 못하니 밖에 있는 a0을 참조함
*/

// 실험2
let a0 = "a0";
function fn2() {
  let a2 = "a2";
  console.log(a0, a2); //a1을 지우면 a0, a2는 에러없이 출력한다
}

function fn1() {
  let a1 = "a1";
  console.log(a0, a1); //정상 출력
  fn2();
}

fn1();
/*
Uncaught ReferenceError: a1 is not defined
    at fn2 at fn1 
참조에러 뜸
fn2는 fn1안에서 호출되서 fn1와 연결 되어있는 것처럼 보이지만
그렇지 않음!
=> fn2는 독립적임, fn2는 a0를 접근할 수 있다.
fn1의 변수에 접근못하므로 정적이다고 할 수 있음 만약 접근 할 수 있다면 동적dynamic scope라고 할 수 있지만 자바스크립트는 정적임
*/

// 실험3
let a0 = "a0";

function fn1() {
  function fn2() {
    let a2 = "a2";
    console.log(a0, a1, a2); //a0 a1 a2
  }
  let a1 = "a1";
  console.log(a0, a1); //a0 a1
  fn2();
}

fn1();
/*
에러 없이 정상 출력됨
fn2함수는 fn1에서 a1을 찾음
fn1함수는 전역변수에서 a0를 찾음
=>fn2를 정적static scope, 어휘적lexical scope라고 부름
*/

//실험4
let a0 = "a0";

function fn1() {
  let a1 = "a1";
  let fn2 = function () {
    let a2 = "a2";
    return "fn2";
  };
  return fn2;
}

fn1();
console.log(fn1());
/*
fn2함수 자체를 가리킨다.
	ƒ () {
    let a2 = "a2";
    return "fn2";
  }
*/
let f11 = fn1(); // f11변수에 저장한 후
console.log(f11()); //fn2, fn2함수의 리턴값을 반환한다
console.log(a0); //a0
console.log(a2); //Uncaught ReferenceError: a2 is not defined
console.log(a0, a1);//Uncaught ReferenceError: a1 is not defined

/*
console.log(fn1())과 console.log(f11()) 는 서로 다르다
변수에 저장해서 함수 호출하면 저장하는 순간을 기억해서
console로 찍으면 return값을 반환하는것 같다
*/

```

```jsx
function sumFac(initial) {
  function sum(nums) {
    console.log(initial, nums);
    return initial + nums;
  }
  return sum;
}

let sum1 = sumFac(1);
console.log(sum1(1)); //2
sumFac(5); // 변동 되지 않는다
console.log(sum1(2)); //3

let sum2 = sumFac(2);
console.log(sum2(1)); //3
console.log(sum2(2)); //4

/*
sum1(1)에서 nums가 1을 넘겨받고, sumFac(1)로 1이 넘겨 받아져서 1+1 =2가 되는 상황이 되는데
sum1(2)에서 sumFac(1)로 1이 남겨져 있어서 1+2= 3이 된다
=> sum1에 저장될 때 sumFac(1)이 그대로 복사되었고, sumFac(5)라고 해도 이전값을 간직한다.
이것을 접근 불가로 판단하고 폐쇄 되었다고해서 클로저라고 한다

*/
```

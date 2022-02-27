[https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/sort](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

```jsx
let months = ["March", "Jan", "Feb", "Dec"];
months.sort(); //기본 정렬 - 알파벳 순서
console.log(months);
let array1 = [1, 30, 4, 21, 100000]; // [ 'Dec', 'Feb', 'Jan', 'March' ]
array1.sort(); //기본 정렬 - 앞의 숫자 우선(유니코드 순서)
console.log(array1); //[ 1, 100000, 21, 30, 4 ]

array1.sort(function (a, b) {
  //오름차순 정렬
  return a - b; //양수로 인정
});
console.log(array1); //[ 1, 4, 21, 30, 100000 ]
array1.sort(function (a, b) {
  //내림차순 정렬
  return -a + b; //음수로 인정
});
console.log(array1); //[ 100000, 30, 21, 4, 1 ]

let items = ["réservé", "premier", "cliché", "communiqué", "café", "adieu"];
items.sort(function (a, b) {
  //비 ASCII 문자 정렬
  return a.localeCompare(b);
});
console.log(items); //[ 'adieu', 'café', 'cliché', 'communiqué', 'premier', 'réservé' ]
```

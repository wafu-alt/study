[https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/filter](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

`arr.filter(callback(element[, index[, array]])[, thisArg])`

## 테스트

```jsx
let exArray = ["1", "7", "0", "3", "7", "3", "0", "0"];
let testArray = exArray.filter(function (element, index, array) {
  console.log(element);
  console.log(index);
  console.log(array);
});

console.log(testArray);
```

## 결과

```jsx
1
0
[
  '1', '7', '0',
  '3', '7', '3',
  '0', '0'
]
7
1
[
  '1', '7', '0',
  '3', '7', '3',
  '0', '0'
]
0
2
[
  '1', '7', '0',
  '3', '7', '3',
  '0', '0'
]
3
3
[
  '1', '7', '0',
  '3', '7', '3',
  '0', '0'
]
7
4
[
  '1', '7', '0',
  '3', '7', '3',
  '0', '0'
]
3
5
[
  '1', '7', '0',
  '3', '7', '3',
  '0', '0'
]
0
6
[
  '1', '7', '0',
  '3', '7', '3',
  '0', '0'
]
0
7
[
  '1', '7', '0',
  '3', '7', '3',
  '0', '0'
]
[]
```

- testArray에는 아무것도 들어가지 않는다.
element : array 각 값을 표시
index : 위치 표시
array : 전체값 표시

```jsx
let count = 0;
let exArray = ["1", "7", "0", "3", "7", "3", "0", "0"];
let testArray = exArray.filter(function (element) {
  if (element == 0) {
    count++;
  }
});

console.log(testArray); //[]
console.log(count); //3
```


[https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)

## 요소 검색예시

```jsx
var array = [2, 9, 9];
array.indexOf(2);     // 0
array.indexOf(7);     // -1
array.indexOf(9, 2);  // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0
```

indexof(찾을요소, 시작위치)

결과값 : 찾은index위치 0~배열길이, 

-1 : 찾을 수 없음

## 모든요소 검색

```jsx
var indices = [];
var array = ['a', 'b', 'a', 'c', 'a', 'd'];
var element = 'a';
var idx = array.indexOf(element);
while (idx != -1) { // 있을 경우
  indices.push(idx); // 그 위치값 index를 배열에 입력
  idx = array.indexOf(element, idx + 1); // 찾은 index 다음 위치부터 검색
}
console.log(indices);
// [0, 2, 4]
```

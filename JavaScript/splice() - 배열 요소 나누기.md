[https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/splice](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

```jsx
array.splice(배열 위치 인덱스, 제거할 영역, 추가할 요소)
```

- 제거할 영역 : 0 - 제거 안함 / 1 - 1개 제거

## 제거

```jsx
var words = [  "i",  "have",  "a",  "pen",  
"i",  "have",  "pineapple",  
"i",  "have",  "an",  "apple",  "pen",
];

let lyrics = words.splice(4, 2);
console.log(words); 
//[ 'i', 'have',a',pen', 'pineapple', 'i',have',an',apple',pen']
console.log(lyrics);
//[ 'i', 'have' ]
=======================
var words = [  "i",  "have",  "a",  "pen",  
"i",  "have",  "pineapple",  
"i",  "have",  "an",  "apple",  "pen",
];
let lyrics = words.splice(4, 3);
console.log(words);
//[ 'i','have','a','pen', 'i','have','an','apple','pen']
console.log(lyrics);
//[ 'i','have', 'pineapple' ]
=======================
var words = [  "i",  "have",  "a",  "pen",  
"i",  "have",  "pineapple",  
"i",  "have",  "an",  "apple",  "pen",
];
let lyrics = words.splice(2, 5);
console.log(words);
//[ 'i','have',  'i','have','an','apple','pen']
console.log(lyrics);
//[ 'a', 'pen', 'i', 'have', 'pineapple' ]
```

- 4번째(인덱스)  `i` 기준으로 2번째(인덱스)까지 살림 - 나머지는 삭제
- `words.splice(2, 5)` 에서 알 수 있음

## 추가

```jsx
var myFish = ["angel", "clown", "drum", "sturgeon"];
var removed = myFish.splice(2, 1, "trumpet");

console.log(myFish, removed);
//["angel", "clown", "trumpet", "sturgeon"]  [ 'drum' ]

=======================
var myFish = ["angel", "clown", "drum", "sturgeon"];
var added = myFish.splice(2, 0, "trumpet");

console.log(myFish, added);
//[ 'angel', 'clown', 'trumpet', 'drum', 'sturgeon' ][]
```

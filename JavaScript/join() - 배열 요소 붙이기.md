[https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/join](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

```jsx
var words = [
  "i",
  "have",
  "a",
  "pen",
  "i",
  "have",
  "pineapple",
  "i",
  "have",
  "an",
  "apple",
  "pen",
];

words.splice(4, 2);
console.log(words);
//[ 'i', 'have', 'a', 'pen', 'pineapple', 'i', 'have', 'an', 'apple', 'pen']
words.splice(5, 3);
console.log(words);
//[ 'i', 'have', 'a', 'pen', 'pineapple', 'apple', 'pen' ]

let lyrics = words.join(" ");
console.log(words);
//[ 'i', 'have', 'a', 'pen', 'pineapple', 'apple', 'pen' ]
console.log(lyrics);
//i have a pen pineapple apple pen
```

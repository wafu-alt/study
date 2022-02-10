https://developer.mozilla.org/ko/docs/Web/CSS/:root

# CSS3 `:root{}`

## CSS에서 변수를 선언하여 사용할 수 있다. 

### 변수선언
`하이픈(-)` + `하이픈(-)` + `변수명` + `:` + `값` + `;`
```
:root {
  --변수명 : 값 ;
}
```

- 예시
```
:root {
  --color-black: #000000;
  --color-white: #ffffff;
  --color-blue: #3b88c3;
  --color-yellow: #fbbe28;
  --color-pink: #fd7f84;
  --color-light-grey: #dfdfdf;
  
  --space-size : 6px;
  --base-space : 10px;
  --font-size : 18px;
 ```
 
 ### 변수 적용
 - 예시
 ```
 .box {
  background-color: var(--color-black);
 }
 
 .txt {
  fadding : var(--space-size);
  margin : var(--base-space);
  font-size : var(--font-size);
 }
 
 ```

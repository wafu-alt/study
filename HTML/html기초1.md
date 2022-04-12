출처 : 엘리스 코딩 교육에서 

    
# 자바스크립트 - 웹코딩 기초, HTML

- web이해
- 웹사이트의 뼈대 만들기
- 웹사이트 꾸미기
- 반응형 웹사이트로 만들기


## 웹이 무엇인지 이해한다

www , w3 - World Wide Web

복잡한 소스코드가 보여지는 이유? 브라우저가 코드를 해석하고 그려줌 

점유율에 따라 지원되는 브라우저 염두에서 코드를 짜는게 유리함

### HTML의 기본개념잡기

Hyper Text Markup Language 마크업 언어

마크업 - 목업, 레이아웃으로 나누는 것 (header, main) 

`<h1>`Hello, World Wide Web`</h1>`

- `Hello, World Wide Web` 컨텐츠

- `<h1>` 태그(꼭 닫아주기)  , 대소문자 구분하지 않음

<div *style*="color: red">Web</div>

*`style`* 속성명

`color: red` 속성값

문서당 `h1`(heading)은 거의 하나 들어감 (2개면 (seo)검색이 잘 안됨)

`a`(anchor) 링크를 만들어 줌

`img`(image) 이미지를 보여줌

`p`(paragraph) 문단 단위를 의미,일반적인 내용을 쓸때 씀

`ul ol li` un(ordered list) 순서가 없는 / 있는 목록을 의미

list item의 약자 , 목록의 내용을 의미

`strong` `em` (emphasis) 모두 강조되는 내용을 의미, 굵게/ 기울기

더 많은 태그는 아래에서 참조

w3school : [https://www.w3schools.com/tags/tag_a.asp](https://www.w3schools.com/tags/tag_a.asp)

MDN : [https://developer.mozilla.org/ko/docs/Web/HTML/Element/a](https://developer.mozilla.org/ko/docs/Web/HTML/Element/a)

`<!DOCTYPE *html*>` 문서 선언, 없어도 에러 없음

`<html *lang*="en">` *lang*="en"은 스크린 리더가 인식함 , 시각장애인을 위한 보조 공학, 스크린 리더가 언어를 인식하여 자동으로 음성을 변환하거나 언어에 적합한 발음을 제공

`<head>`

`<meta *charset*="utf-8"/>`  메타는 내장되어 있는 정보

인코딩설정, 문자 표현할 수있는 인코딩

`<title>My Website</title>` 페이지 제목

`</head>`

`<body>` 표시되는 모든 컨텐츠

`<h1>Hello, World Wide Web!</h1>`

`</body>`

`</html>`

`<meta charset="utf-8"/>`  meta태그를 열고 닫는것을 한줄로 표현도 가능하다 `<meta />`

vscode에서 ctrl+x에서 플러그인

****`Prettier - Code formatter` 를 설치해서 줄 바꿈 이쁘게 할 수 있음**

****`Live Server` 코드 고치고 웹에서 새로고침 안되도 반영됨**

****`Auto Rename Tag` 여는태그 고치면 닫는 태그도 고쳐줌**

### HTML으로 구조 잡기

inline과 block 차이

웹 개발자도구에서 아래 아이콘을 클릭하고 각 해당하는 영역에 가져다 되면 각 태그의 영역을 알 수 있다

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b2d9ab72-62f8-4f63-9c7b-1c9bceb54e3f/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d166d796-cedf-434d-bec8-cf66a5f29eec/Untitled.png)

     block : 한줄 차지 `div` 태그가 영역나눌때 사용

inline : 포함된 내용만(컨텐츠) `span` 태그가 영역 나눌때 사용

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/784475b3-f1b5-4471-8929-5ab741d60246/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/15576705-fa38-4817-9c29-469b404eb41e/Untitled.png)

 `header` (header) 웹사이트의 머리글을 의미

 `nav` (navigation) 주로 메뉴버튼을 의미

`mian` body내의 주요 컨텐츠를 의미

`article` 사이트 내 독립적인 구분을 의미(ex.블로그글, 뉴스기사) 

- h1이 항상 필수

`footer` 웹사이트의 맨 하단을 의미, 주로 저작권, 작성자 등의 정보를 적음

### CSS 맛보기

Cascading Style Sheet

html로 만들어진 뼈대를 꾸며줌

각 요소에 레이아웃을 조절

애니메이션 효과도 가능

div { background-color : blue; }

`div` : 선택자  - 어떤 요소에 스타일을 적용할지 선택

`background-color` : 속성 - 어떤 속성을 적용할지 정의

`;` : 구분자 - 각 속성과 속성값 간에는 세미클론(;)으로 구분

### 인라인 스타일(Inline Style)

```jsx
<div style="background-color: blue;">
  저는 인라인 스타일의 div입니다.
  <span style="background-color: red;">
    저는 인라인 스타일의 span입니다.
  </span>
</div>
```

- 우선순위가 가장 높음
- 고드 재활용이 좋지 못함
- 가급적 쓰지 않는 것이 좋음(테스트 용도로 사용)

### 내부스타일(Internal Style)

```jsx
<head>
  <style>
    div {
      background-color: blue;
    }
    span {
      background-color: red;
    }
  </style>
</head>
```

- 인라인 스타일 다음으로 우선순위 적용
- 특정 페이지에서만 적용하기 위해서 사용
- 주로 <head> 태그 안에 정의

### 외부 스타일(External Style)

```jsx
<head>
  <link rel="stylesheet" href="main.css" />
</head>
```

- 가장 많이 사용하는 방식
- 협업에 우수함
- 여러 html에 동일한 스타일을 적용할 수 있음

인라인 > 내부 > 외부 > 브라우저 기본 스타일

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6d00aec5-48f6-4f19-af28-db96656273d7/Untitled.png)

### 선택자 비교

`body` : 태그 선택자 - 선택자에 태그명을 그대로 써주면 됨, 문서 전체 태그에 적용

`#example1` : ID 선택자 - 선택자 앞에 샾(#)을 붙여주면 ID를 의미, 특정 요소만 적용할 때 사용 (중복 사용 불가)

`.example2` : CLASS선택자 - 선택자 앞에 점(.)을 붙여주면 CLASS를 의미 범용적으로 적용할 때 사용 (중복 사용 가능)

### 주요 속성

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/eaf2a2b4-5d18-4a2d-b3da-dfeb6835abed/Untitled.png)

`width` 요소 너비를 설정 ( px, %, rem, ...)

`height` 요소 높이를 설정 ( px, %, rem ...)

`color` 글자의 색상을 설정 (#999999, brown ....)

`font-size`  글자 크기를 설정

`font-family` 글자의 폰트를 설정, 여러개 설정시 앞에 폰트부터 있는 것을 적용

`font-style` 글자의 기울기를 설정 (italic)

`font-weight` 글자의 두께를 설정 (bold,100,200, ...900), 글자체가 지원하지 않으면 근처 수치에 붙음

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4e22ac8e-f60b-4794-a90d-7756650e591b/Untitled.png)

`border-style` 테두리 스타일을 설정 (dotted, double .. )

`border-color` 테두리 색상을 설정 (#999999, brown .. )

`border-width` 테두리 두께를 설정

`border` 위 속성들을 한 번에 정의할 수 있음

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2ac3177b-b30e-4f73-b033-f7485545a2b7/Untitled.png)

`background-color` 배경의 색상을 설정

`image` 이미지를 설정 , 여러개 가능 (height가 있어야 이미지가 보임)

`repeat` 반복여부를 설정 (repeat, repeat-x, round .. )

`position` 정렬 위치를 설정 (top, left .. )

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/20765166-03de-450f-bdf6-696b94cff708/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/777eda54-bcd6-4ec3-a6d4-59e24381d60c/Untitled.png)

`margin`  바깥 여백 영역 설정

`padding`  안쪽 여백 영역 설정

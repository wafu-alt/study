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

1. 불러오기

```jsx
import Header from "./components/Header.js";
import Main from "./components/Main.js";
import Footer from "./components/Footer.js";
```

1. reat.js에서는 컴퍼넌트를 어플리케이션으로 봐서 . main.js에서 불러와서 사용

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

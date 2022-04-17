# Cascading Style Sheet

- html로 만들어진 뼈대를 꾸며줌
- 각 요소에 레이아웃을 조절
- 애니메이션 효과도 가능

## 기본 구성

```css
div { background-color : blue; }
```

- `div` : 선택자(selector) - 어떤 요소에 스타일을 적용할지 선택
- `background-color` : 속성(property) - 어떤 속성을 적용할지 정의
- `;` : 구분자 - 각 속성과 속성값 간에는 세미클론(;)으로 구분

### 주석

```css
/* 주석처리 */
```

### 인라인 스타일(Inline Style)

```html
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

```css
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

```
<head>
  <link rel="stylesheet" href="main.css" />
</head>
```

- 가장 많이 사용하는 방식
- 협업에 우수함
- 여러 html에 동일한 스타일을 적용할 수 있음

우선도 순서
- 인라인 > 내부 > 외부 > 브라우저 기본 스타일
        
  ![1](https://user-images.githubusercontent.com/83447120/163708682-71290109-1cb8-4d2f-913e-dcba16d73797.jpg)


### 선택자 비교

- `p` : 태그 선택자 - 선택자에 태그명을 그대로 써주면 됨, 문서 전체 태그에 적용
- *`.classPtag`* : CLASS선택자 - 선택자 앞에 점(.)을 붙여주면 CLASS를 의미 범용적으로 적용할 때 사용 (중복 사용 가능)
- *`#idPtag`* : ID 선택자 - 선택자 앞에 샾(#)을 붙여주면 ID를 의미, 특정 요소만 적용할 때 사용 (중복 사용 불가)

### 주요 속성

```css
	/* 글자 관련 */
  font-family: "맑은 고딕", serif, sans-serif; /* 폰트 설정 */
  font-weight: 400; /* (bold, nomal, 100~900 ..) 글자 두께 */
  font-style: italic; /* 글자 스타일 */
  font-size: 16px; /* (1.2em, 80%, rem .. ) 글자 크기 */

  color: blue;
  /* (rgba(255, 152, 100, 10),rgb(255, 152, 100),#664485 .. ) 글자 색상 */
  text-align: center; /* 글자 정렬 */
  text-decoration: solid; /* 글자 밑줄 스타일 */
  text-transform: uppercase; /* 글자 대문자 소문자 선택 */
  text-indent: -99999; /* (px,em .. ) 글자 들여쓰기 */
  text-shadow: 10px 10px 2px gray; /* 박스 그림자 */
  /*  그림자수평 | 수직 | 흐림 | 색  */

  letter-spacing: 1px; /* 글자 간격 */
  line-height: 1.6; /* 줄높이 */
  white-space: pre; /* 공백문자 처리 */

  /* 보이는 부분 */
  display: none; /* (block, flex, gird) 레이아웃 설정 none = 공간차지 x */
  visibility: hidden; /* (visible) 숨김 여부 hidden = 공간차지*/
  opacity: 0.2; /* 투명도 */
  overflow: scroll; /* (visible, hidden) 컨첸츠가 클때 처리법 */

  /* 크기 */
  width: 50%; /* 가로 크기 */
  height: 100px; /* 세로 크기 */

  /* 내부 공간 */
  padding-top: 20px;
  padding-right: 10%;
  padding-bottom: 10px;
  padding-left: 10px;
  padding: 10px 0; /* 상하 좌우 , 상 좌우 하 , 위 오른쪽 아래 왼쪽 */

  /* 외부 공간 */
  margin-top: 10px;
  margin-right: 10%;
  margin-bottom: 15px;
  margin-left: 5px;
  margin: 10px 20px 20px; /* 상하 좌우 , 상 좌우 하 , 위 오른쪽 아래 왼쪽 */

  /* 배경관련 */
  background-color: #78fe54; /* 배경 색 */
  background-image: url("../folder/image.jpg"); /* 배경이미지 경로 */
  background-position: center 200px; /* 배경이미지 위치 */
  background-repeat: no-repeat; /* 배경이미지 반복여부 */
  background-attachment: scroll; /* 배경이미지 뷰포트에 고정할지 설정 */
  background: url("image.gif") #3f0 no-repeat center 200px; /* 순서상관없음 */

  /* 외각선 */
  border-top: 10px solid #f33; /* 윗 라인만 해당 */
  border-right: 10px solid #f33;
  border-bottom: 10px solid #f33;
  border-left: 10px solid #f33;
  border-style: dotted;
  border-color: aquamarine;
  border-width: 2px;
  border: 10px solid #f33; /* 둘레 전체 해당 순서 상관없음 */
  border-radius: 1.5px 30px; /* 왼쪽위 오른쪽위 오른쪽아래 왼쪽아래 */

  box-shadow: 10px -15px 5px red;
  /*  그림자수평 | 수직 | 흐림 | 색  */

  /* 위치관련 */
  float: left; /* (right) 요소를 띄워서 정렬 */
  clear: both; /* (left, right)float을 해제 */

  position: absolute; /* (relative, static) 요소 배치 */
  left: 20px; , top: 0; /* 요소 이동 */
  z-index: 2; /* 요소가 겹쳤을 때 숫자가 클수록 위에 보임 */

  /* display : flex; */
  flex-direction: row; /* (column) flex요소의 방향 */
  flex-wrap: nowrap; /* (wrap) 뷰포트 넘었을때 설정 */
  align-content: flex-end; /* 여러행 수직 축 방향 설정 */
  justify-content: unset;  /* 메인방향 설정 */
  align-items: center; /* 수직 축 방향 설정 */
  .flexItems { /* flex item에 각각 설정 */
    flex-grow: 1; /* 여백의 비율 */
    flex-shrink: 1; /* 아이템이 컨테이너보다 클때 아이템을 축소시키는 옵션 */
    flex-basis: 30px; /* (10%) 요소의 기본 크기 */
    flex : 1 1 30px ; /* 위의 설정 단축 */
  }

  /* display : gird; */
  grid-template-columns: 1fr 1fr; /*(repeat(2, 1fr)) 아이템 공간 설정 fraction*/
  
  row-gab: 20px; /* 수평간의 간격 */
  column-gab: 10px; /* 수직간의 간격 */
  gab : 20px 10px ; /* 단축 설정 */
  grid-gab : 20px 10px; /* 브라우저마다 호환안할 시 old한 사용법 */

  /* grid line기준으로 설정 - 바둑판 생각하면 될듯 */
  .gridItem:nth-child(1) {
    grid-column-start: 1; /* 세로 1줄부터 */
    grid-column-end: 3;  /* 세로 3줄까지 */
    grid-column: 1 / 3; /* 총 2칸 차지 */

    grid-row-start: 1; /* 가로 1줄부터 */
    grid-row-end: 2;  /* 가로 2줄까지 */
    grid-row: 1 / 2; /* 총 1칸 차지 */
  }

  /* grid or flex 정렬 */
  justify-items: center; /* 가로방향정렬 */
  align-items: end; /* 세로방향정렬 */
  place-items: center end; /* 윗 둘다 설정 */

  justify-self: stretch; /*  아이템가로방향정렬 */
  align-self: start; /* 아이템세로방향정렬 */
  place-self: stretch start; /* 윗 둘다 설정 */

  /* 애니메이션 관련 */
  transform: rotate(90deg);  /* 회전, 이동, 크기조절, 기울이기 */
  /* (translate(120px,50%), scale(2,0.5), skew(30deg,20deg))  */

  transition-property: width, height; /* (all)애니메이션 속성 대상 */
  transition-duration: 2s; (1000ms = 1s) /* 진행 시간 */
  transition-timing-function: linear; /* (ease, ease-in ...)진행 속도 */
  transition-delay: 1000ms; /* 애니메이션 전 대기시간 */
  transition: width,height 2s linear 1000ms ; 
  /* 순서상관없음, 먼저 적은 시간은 duration임 */

  animation-name: aniTest; /* @keyframes에 적은 이름 */
  animation-duration: 1000ms;
  animation-timing-function: ease-out;
  animation-delay: 2s;
  animation-iteration-count: infinite; /* 반복 횟수 */
  animation-direction: alternate; /* 진행방향 form > to > from > to방식 */
  animation: aniTest 1000ms ease-out 2s infinite alternate;
  /* 순서상관없음, 먼저 적은 시간은 duration임 */
  
  @keyframes aniTest {
    fromm { /* 1번째 방식 */ width: 100%;}
    to { height: 50%;}
    0% { /* 2번째 방식 */ width: 100%;}
    50% {width: 50%;}
    100% {width: 0%;}
  }

  /* 기타 */
  cursor: pointer; /* 마우스 모양이 포인터로 바뀌 */
```

### margin 병합 현상

- 형제간 - 큰값 따라감
    
    ![margin병합_-형제](https://user-images.githubusercontent.com/83447120/163708700-cf7bb670-bc89-401f-b601-4ef98f328fec.jpg)
    
    ```html
    <style>
    	.margin1,
    	.margin2 {
    	  width: 80%;
    	  height: 100px;
    	  margin: 20px;
    	  background: green;
    	}
    	.margin2 {
    	  margin-top: 50px; <!-- 아래부분을 더 크게하면 50px로 적용된다. -->
    	}
    </style>
    
    <div>
      <div class="margin1"></div>
      <div class="margin2"></div>
    </div>
    ```
    
- 부모간 - 포지션으로 위치고정으로 해결, 부모에 border선을 만들서어 브라우저에게 위치 인식 시킴
부모간의 margin 병합 부모는 margin값이 없지만 자식 margin값이 적용됨
    
   ![margin병합_-부모0](https://user-images.githubusercontent.com/83447120/163708701-23990986-2bac-454c-8e5c-db936f00435f.jpg)
    
    ```html
    <style>
    .marginParents {
      background: blue; 
    }
    .margin1 {
      width: 80%;
      height: 100px;
      margin: 20px;
      background: green;
    }
    .margin1 {
      margin-top: 100px; /* 문제의 발생 */
    }
    .margin2 {
      margin-top: 50px;
    }
    </style>
    
    <div class="marginParents">
    	<div class="margin1"></div>
    	<div class="margin2"></div>
    </div>
    ```
    
   ![margin병합_-부모1](https://user-images.githubusercontent.com/83447120/163708704-0257d9f1-9e4c-49a2-a2ae-39522012beba.jpg)
    
    border 선을 활용한 해결책
    
  ![margin병합_-부모2](https://user-images.githubusercontent.com/83447120/163708706-7857c15e-10cd-4fdb-ac76-829a4b49831f.jpg)
    
    ```css
    
    .marginParents {
      background: blue;
      border: 1px solid black;  /* 해결책 */
    }
    .margin1 {
      width: 80%;
      height: 100px;
      margin: 20px;
      background: green;
    }
    .margin1 {
      margin-top: 100px;
    }
    .margin2 {
      margin-top: 50px;
    }
    
    ```
    
    자식요소 margin1에 `position: absolute;` 으로 해결
    
    ![margin병합_-부모3](https://user-images.githubusercontent.com/83447120/163708709-b42ce426-6ca2-470d-a575-def2049a42a8.jpg)
    
    ```css
    .margin1 {
      width: 80%;
      height: 100px;
      margin: 20px;
      background: green;
    }
    .margin1 {
      position: absolute; /*해결책*/
      margin-top: 100px;
    }
    .margin2 {
      margin-top: 50px;
    }
    ```
    

### CSS 프레임 워크

- [http://bootstrapk.com/](http://bootstrapk.com/)
- 편리하고 빠르게 사용 가능

### **Vendor Prefix**(접두사)

```css
.item {
	-webkit-transform: all 4s ease; // 크롬, 사파리, 최신버젼 오페라 ,iOS
	-moz-transform: all 4s ease;    // 파이어폭스
	-ms-transform: all 4s ease;     // 익스플로러 , 엣지
	-o-transform: all 4s ease;      // 올드버젼 오페라
}
```

### 그룹선택자

- 두 개 이상을 선택해서 같은 속성을 줄 때
    
    ```css
    .selector1 , .selector2 { 
    	width: 100px;
    	height: 100px;
    	margin : 100px 0;
    } 
    ```
    

### 가상선택자 (클래스와 요소)

- `**:pseudo-class` 가상클래스선택자**
    
    ```css
    a:link {} /* 방문한적 없는 링크 */
    a:visited {} /* 방문한 링크 */
    a:hover {} /* 커서 가져다 대었을 때 */
    a:active {} /* 클릭하는 순간 */
    a:focus {} /* 마우스 클릭이나 키보드 탭했을때 요소가 활성화 될 때 */
    li:first-child {} /* li형제 중 첫번째 */
    li:last-child {} /* li형제 중 마지막 */
    li:nth-child(n) {} /* li형제 중 n번째 (2n+1 : 홀수번째) */
    ```
    
- `**:pseudo-element` 가상요소선택자**
    
    ```css
    p:first-line {} /* p요소의 첫번째 줄을 제어, 색, 백그라운드, 폰트*/
    p:first-letter {} /* p요소으 첫번째 문자 제어 */
    div:before {} /* div 앞에 컨텐츠를 생성 */ 
    div:after {} /* div 뒤에 컨텐츠를 생성 */
    
    ```
    

### 미디어 쿼리

- pc말고 다른 화면에 웹사이트를 만들기 위함

```css
<head>
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
</head>
/* 헤드의 메타 태그의 viewport와 같이 사용한다 */

.item {
	width:100%;
	height : 100px;
	background : blue;
}

@media screen and (min-width: 320px) and (max-width: 800px) {
	.item {
		width: 50%;
		height:300px;
		background : green;
	}
}
/* 화면이 최소 320px과 최대 800px일때 @media 아래의 .item 코드가 우선된다*/
```

- `name="viewport"`  기기의  화면상 표시되는 영역
- `content="width=device-width”` 뷰포트의 가로폭 = 기기의 화면 가로폭
- `content="initial-scale=1.0"` 비율은 1:1
- 화면 나누는 보통 기준
1920 -< 피씨 >- 1200 or 1024 -< 렙탑 >- 1024 -< 테블릿 >- 768 -< 모바일 >- 320

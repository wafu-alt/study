

### window객체

```jsx
window.innerHeight; // 웹페이지의 높이
window.innerWidth; // 웹페이지의 너비
window.alert("안녕하세요?"); // 브라우저에 알림창 표시
window.confirm("사용하시겠습니까?"); // 브라우저에 확인창 표시
window.close(); // 현재 창 닫기
window.open("URL", "이름", "설정"); // 새로운 창 열기
window.scrollTo(0, 100); // 지정한 위치로 스크롤
window.scrollBy(0, 10); // 지정한 만큼 스크롤
window.resizeTo(300, 300); // 창 크기를 지정한 크기로 변경
window.resizeBy(100, 100); // 창 크기를 지정한 크기만큼 변경
```

- .xx() 괄호가 붙은 것은 함수임

```jsx
//html
<!-- 윈도우 객체 사용해보기 -->
<button id="bg-change-btn">배경색 바꾸기</button>
<button id="new-window-btn">새창 열기</button>
<button id="window-close-btn">새창 닫기</button>

<button id="window-resize-btn">새창 크기 재조정</button>
<button id="window-increase-btn">새창 크기 키우기</button>
<button id="window-reduce-btn">새창 크기 줄이기</button>

<button id="window-scroll-top-btn">새창 스크롤 최상단 이동</button>
<button id="window-scroll-down-btn">새창 스크롤 내리기</button>
<button id="window-scroll-up-btn">새창 스크롤 올리기</button>

//js
//배경색 바꾸기
let bgChangeBtn = window.document.getElementById("bg-change-btn");

bgChangeBtn.addEventListener("click", function () {
  let isOk = window.confirm("배경색을 바꾸시겠습니까?");
  //console.log(isOk); //true , false 반환함
  if (isOk) {
    document.querySelector("body").style.backgroundColor = "brown";
  }
});
//새 창 열기
let newWindowBtn = window.document.getElementById("new-window-btn");

newWindowBtn.addEventListener("click", function () {
  newWindow = window.open(
    "new.html",
    "새로운 창",
    "width=300, height=300",
    (target = "_blank")
  );
});
//새 창 닫기
let windowCloseBtn = window.document.getElementById("window-close-btn");

windowCloseBtn.addEventListener("click", function () {
  newWindow.close();
});
//새 창 열때 고정된 크기 열기
let windowResizeBtn = window.document.getElementById("window-resize-btn");

windowResizeBtn.addEventListener("click", function () {
  newWindow.resizeTo(1000, 1000);
});
//버튼 클릭시 새 창 사이즈 늘리기(양수)
let windowIncreaseBtn = window.document.getElementById("window-increase-btn");

windowIncreaseBtn.addEventListener("click", function () {
  newWindow.resizeBy(100, 100);
});
//버튼 클릭시 새 창 사이즈 줄이기(음수)
let windowReduceBtn = window.document.getElementById("window-reduce-btn");

windowReduceBtn.addEventListener("click", function () {
  newWindow.resizeBy(-100, -100);
});
//스크롤 최상단 올리기
let windowScrollTopBtn = window.document.getElementById(
  "window-scroll-top-btn"
);

windowScrollTopBtn.addEventListener("click", function () {
  newWindow.scrollTo(0, 0);
});
//스크롤 수치만큼 내리기(양수, 음수x)
let windowScrollDownBtn = window.document.getElementById(
  "window-scroll-down-btn"
);

windowScrollDownBtn.addEventListener("click", function () {
  newWindow.scrollBy(0, 10);
});
//스크롤 수치만큼 올리기(음수!!)
let windowScrollUpBtn = window.document.getElementById("window-scroll-up-btn");

windowScrollUpBtn.addEventListener("click", function () {
  newWindow.scrollBy(0, -10);
});
```
  

출처 : 엘리스 SW엔지니어 트랙


https://axios-http.com/kr/docs/intro
## **Axios란?**

Axios는 웹 브라우저와 Node.js를 위한 HTTP 비동기(작성된 순서대로 실행되지 않는 처리) 통신 라이브러리입니다. 쉽게 말해서 백엔드와 프론트엔드 간 통신을 쉽게 하기 위해 사용되는 것으로 [Ajax](https://ko.wikipedia.org/wiki/Ajax)처럼 사용되는 것입니다. 비동기 통신 라이브러리를 사용하지 않으면 모든 코드가 순차적으로 처리되어야 하므로 코드의 순서를 신경 써서 작성해야 합니다. 즉, 코드 작성이 매우 복잡해집니다. 따라서 비동기 통신을 쉽게 해주는 Axios나 Ajax 같은 것이 자주 사용되는 것입니다.

Ajax란 비동기 자바스크립트란 의미로 Asynchronous JavaScript and XML의 약자입니다. Ajax는 브라우저가 가지고 있는 [XMLHttpRequest](https://developer.mozilla.org/ko/docs/Web/API/XMLHttpRequest) 객체를 이용하여 화면 전체를 새로 고침 하지 않고 변경된 일부 데이터만 로드하는 비동기 처리가 가능합니다. Axios는 Ajax와 유사하며 API를 이용한 통신을 할 때 주로 사용합니다.

> Axios는 Promise를 기반으로 만들어진 라이브러리입니다. Promise는 자바스크립트 ES6에서 비동기 처리를 위해 주로 사용되는 객체입니다.
>

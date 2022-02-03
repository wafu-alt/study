[https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-defer](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-defer)

```jsx
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>

    <script>
      document.write("Hello World! top");
    </script>
    <script src="defer3.js"></script>
    <script src="defer.js" defer></script>
  </head>
  <body>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <p>Hi!, I'm practicing using the defer attribute.</p>
    <script>
      document.write("Hello World! bottom");
    </script>
    <script src="defer2.js"></script>
  </body>
</html>
```

결과창

Hello World! top이 가장 먼저 출력되고,

Hello World! mid가 두번째로 바로 출력된다.

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/237624dd-fe5f-408b-b575-e33305b4947f/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220203%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220203T123720Z&X-Amz-Expires=86400&X-Amz-Signature=71da573fdcb61512aec9bdce2240f7c7e22057e709ae4bb3283fe045a58a883e&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

async
일반 스크립트에 async 속성이 존재하면 HTML 구문 분석 중에도 스크립트를 가져오며, 사용 가능해지는 즉시 평가를 수행합니다.

모듈 스크립트에 async 속성이 존재하면 모듈 스크립트와 모든 의존 스크립트를 지연 큐에서 실행하므로 함께 병렬로 불러오며, 이와 동시에 구문 분석을 수행하고 사용 가능해지는 즉시 평가합니다.

기존 방식은 브라우저가 HTML 분석을 계속하기 전에 스크립트를 불러오고 평가했어야 하므로, async 속성을 사용하면 분석기를 멈추는 JavaScript를 제거할 수 있습니다. defer도 비슷한 효력을 냅니다.

async는 불리언 속성입니다. 속성이 존재하면 참을 나타내고, 속성이 존재하지 않으면 거짓을 나타냅니다.

브라우저 호환성을 참고하세요.

defer
브라우저가 스크립트를 문서 분석 이후에, 그러나 DOMContentLoaded 발생 이전에 실행해야 함을 나타내는 불리언 속성입니다.

defer 속성을 가진 스크립트는 자신의 평가가 끝나기 전까지 DOMContentLoaded 이벤트의 발생을 막습니다.

src 속성이 존재하지 않을 때(인라인 스크립트인 경우 등)에는 아무런 효과도 없으므로 사용해서는 안됩니다.

또한 모듈 스크립트는 기본적으로 지연 평가하므로, defer를 지정해도 변화가 없습니다.

defer 속성을 가진 스크립트는 문서상의 순서를 따라 실행됩니다.

기존 방식은 브라우저가 HTML 분석을 계속하기 전에 스크립트를 불러오고 평가했어야 하므로, defer 속성을 사용하면 분석기를 멈추는 JavaScript를 제거할 수 있습니다. async도 비슷한 효과를 가집니다.

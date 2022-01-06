# 문제 인식

---

![Untitled](https://user-images.githubusercontent.com/83447120/148393453-01afe732-feb9-4f1a-89bc-4ca49de690e2.png)
위는 강의

아래는 나의 코드
![1](https://user-images.githubusercontent.com/83447120/148393348-4437d4d8-47d4-4efa-8d82-6455007129fd.jpg)

인터넷 강의듣고 분명 코드를 똑같이 했는데 안된다. 그래서 fetch를 밖에서 빼왔는데 된다. 왜 함수 안에 있는것은 안나올까?

## 드림코딩에서 운영하는 slack에서 질문

---

![2](https://user-images.githubusercontent.com/83447120/148393367-17b5b1a9-dde0-4855-a534-4d143dd4323c.jpg)

아니!!! 하루전까지 되었는데 이번에는 둘 다 안된다 why??? 

---

> [Moon-Il Son](https://dream-coding.slack.com/team/U01FV7UD35M)님의 답변
> 
> 
> “바로 직전에 올려주신 스샷을 보면 서버를 띄우지 않고 바로 html 파일을 브라우져로 여신 것 같아요. 이 경우에 fetch api는 아래 링크의 answer의 내용에 있는 것 처럼 SOP 정책으로 인해서 정상 동작하지 않는 것으로 보여요([https://www.tutorialguruji.com/javascript/fetch-api-cannot-load-url-scheme-file-is-not-supported/](https://www.tutorialguruji.com/javascript/fetch-api-cannot-load-url-scheme-file-is-not-supported/))
> 질문 주셨던 내용이 이거와 관련된게 아니라면 다시 thread에 댓글 부탁드려요~
> 위 질문 주신 두 케이스 모두 서버실행 후
> 브라우져에서 확인을 했던 건데 한번은
> 
> ```jsx
> function loadItems() {
> return (
> fetch("data/data.json")
> .then((response) => response.json())
> .then((json) => console.log(json))
> );
> }
> ```
> 
> 이렇게 정의된 loadItems를 호출했는데 출력이 되지 않고,
> 다른 한번은
> 
> ```jsx
> fetch("data/data.json")
> .then((response) => response.json())
> .then((json) => console.log(json));
> ```
> 
> 를 직접 호출했더니 정상적으로 콘솔에 출력이 되었다는 질문인지 좀 모호해서요”
> 

## 결론 해결법

![Untitled 1](https://user-images.githubusercontent.com/83447120/148393525-530b29b4-79d6-4f87-94c3-d1199d56e698.png)

다른분들을 통해서 해결을 먼저 했다.
vscode 우측하단에 live server있냐고 묻는데 그때 바로 느낌와서 live server 다운받아서 웹을 열었더니 해결 됬다. 해결은 했는데 가장 중유한 이유를 알아야 공부 되는것 아니겠나.

## 공부 시작

1. fetch에 대해서 알아야할 것 같다.
2. 에러 메세지에 대한 이해가 필요할 것 같다.
3. live server가 어떤 역할을 하는지 알아야 할 것 같다.

그러면 서로 연결이 되서 해결된 이유도 자연스럽게 알 것 같다.

1~2번까지만 알아도 무엇이 필요한지 알것이고,

3번에서 어떻게 건너다리 역할을 하는지 알 수 있을 것 같다.

1 [fetch](https://www.notion.so/fetch-739ef55c2e8145c1a6f76d877de0291b)

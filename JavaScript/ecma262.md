모르는 단어 표시

ECMA-262 / 2022년 8월 10일 초안ECMA스크립트® 2023 언어 사양

### 사양정보

- [https://tc39.es/ecma262/](https://tc39.es/ecma262/)의 문서는 가장 정확한 최신 ECMA스크립트 사양. 이 내용에는 최근 연간 기록들과 완료된 제안(제안 프로세스에서 4단계에 도달하여 여러 구현에서 구현되며 다음 실제 개정에서 진행될 예정)들의 내용을 포함하고 있습니다.
  이 페이지는 싱글페이지와 멀티페이지들로 제공됩다.

이 사양정보의 기여

- 이 사양은 ECMA스크립트 커뮤니티의 도움을 받아 깃허브에서 개발되었습니다. 이 규격의 개발에 기여할 수 있는 방법은 다음과 같습니다.
  - GitHub Repository: [https://github.com/tc39/ecma262](https://github.com/tc39/ecma262)
  - Issues: [All Issues](https://github.com/tc39/ecma262/issues), [File a New Issue](https://github.com/tc39/ecma262/issues/new)
  - Pull Requests: [All Pull Requests](https://github.com/tc39/ecma262/pulls), [Create a New Pull Request](https://github.com/tc39/ecma262/pulls/new)
  - Test Suite(테스트 제품) : [Test262](https://github.com/tc39/test262)
  - Editors:
    - [Shu-yu Guo](mailto:syg%20at%20google%20dot%20com) ([@\_shu](https://twitter.com/_shu))
    - [Michael Ficarra](mailto:ecma262-editor-list%20at%20michael%20dot%20ficarra%20dot%20me) ([@smooshMap](https://twitter.com/smooshMap))
    - [Kevin Gibbons](mailto:bakkot%20at%20gmail%20dot%20com) ([@bakkoting](https://twitter.com/bakkoting))
  - Community:
    - Discourse: [https://es.discourse.group](https://es.discourse.group/)
    - Chat: [Matrix](https://github.com/tc39/how-we-work/blob/HEAD/matrix-guide.md)
    - Mailing List Archives(메일 목록 보관소): [https://esdiscuss.org/](https://esdiscuss.org/)
- 이 문서 작성 방법에 대한 자세한 내용은 [[colophon](https://tc39.es/ecma262/#sec-colophon)]을 참조하십시오.

# 소개

- 이 Ecma 표준은 ECMA 스크립트 2023 언어를 정의한다. ECMA 스크립트 언어 사양의 14번째 버전이다. 1997년 초판이 출판된 이후 ECMA스크립트는 세계에서 가장 널리 사용되는 범용 프로그래밍 언어 중 하나로 성장했다. 웹 브라우저에 내장된 언어로 가장 잘 알려져 있지만 서버 및 임베디드 응용 프로그램에도 널리 채택되었다.
- ECMA스크립트는 여러 원천 기술을 기반으로 하며, 가장 잘 알려진 것은 자바스크립트(넷스케이프)와 J스크립트(마이크로소프트)이다. 이 언어는 넷스케이프 사의 Brendan Eich에 의해 발명되었으며 그 회사의 네비게이터 2.0 브라우저에 처음 등장했다. 넷스케이프의 모든 후속 브라우저와 인터넷 익스플로러 3.0을 시작으로 마이크로소프트의 모든 브라우저에 등장했다.
- ECMA스크립트 언어 규격의 개발은 1996년 11월에 시작되었다. 이 Ecma 표준의 초판은 1997년 6월 Ecma 총회에서 채택되었다.
- 그 Ecma 표준은 패스트트랙 절차에 따라 채택을 위해 ISO/IEC JTC 1에 제출되었으며 1998년 4월에 국제 표준 ISO/IEC 16262로 승인되었다. 1998년 6월, ECMA-262의 제2판은 ISO/IEC 16262와 완전히 일치하도록 승인되었다. 제1판과 제2판 사이의 변화는 본질적으로 편집이다.
- 이 표준의 제3판은 강력한 정규 표현식, 더 나은 문자열 처리, 새로운 제어문, 시도/캐치 예외 처리, 오류의 더 엄격한 정의, 숫자 출력의 형식 및 미래의 언어 성장을 예상하는 사소한 변화를 도입하였다. ECMA스크립트 표준의 세 번째 판은 1999년 12월 Ecma 총회에서 채택되었으며 2002년 6월 ISO/IEC 16262:2002로 출판되었다.
- 세 번째 판이 출판된 후 ECMA스크립트는 월드 와이드 웹과 함께 대규모 채택을 이루었으며, 기본적으로 모든 웹 브라우저에서 지원하는 프로그래밍 언어가 되었다. ECMA 스크립트의 4번째 에디션을 개발하기 위해 중요한 작업이 수행되었습니다. 그러나 이 작업은 완료되지 않았고 ECMA 스크립트의 4번째 에디션으로 출판되지 않았지만 일부는 6번째 에디션의 개발에 통합되었다.
- ECMA-262 제5판(ECMA-262 제5판)은 브라우저 구현 중 보편화된 언어 사양에 대한 사실상의 해석을 성문화하고, 제3판 발행 이후 등장한 새로운 기능에 대한 지원을 추가하였다. 이러한 기능들은 [접근자 속성](https://tc39.es/ecma262/#sec-object-type)([accessor properties](https://tc39.es/ecma262/#sec-object-type)), 객체의 반사적 생성 및 검사, 속성 속성의 프로그램 제어, 추가적인 배열 조작 기능, JSON 객체 인코딩 포맷 지원, 향상된 오류 검사 및 프로그램 보안을 제공하는 엄격한 모드를 포함한다. 제5판은 2009년 12월 Ecma 총회에서 채택되었다.
- 제5판은 패스트트랙 절차에 따라 ISO/IEC JTC 1에 제출되었으며 국제 표준 ISO/IEC 16262:2011로 승인되었다. ECMA스크립트 표준의 5.1 판은 사소한 수정을 포함했으며 ISO/IEC 16262:2011과 동일한 텍스트이다. 5.1 에디션은 2011년 6월 Ecma 총회에서 채택되었다.
- 2009년 5판이 출판을 준비하면서 6판의 집중적인 개발이 시작되었다. 그러나, 이것은 1999년 제3판이 출판되기 전까지 상당한 실험과 언어 향상 디자인 노력이 선행되었다. 매우 현실적인 의미에서, 제6판의 완성은 15년간의 노력의 정점이다. 이 에디션의 목표는 대규모 응용 프로그램, 라이브러리 작성, ECMA스크립트를 다른 언어의 컴파일 대상으로 사용할 수 있도록 더 나은 지원을 제공하는 것이다. 주요 개선 사항 중 일부는 모듈, 클래스 선언, lexical block scoping, iterators 및 generators, 비동기 프로그래밍에 대한 promises, destructuring patterns, proper tail calls을 포함한다. built-ins ECMA스크립트 라이브러리는 지도, 세트, 이진 숫자 값의 배열을 포함한 추가 데이터 추상화뿐만 아니라 문자열과 정규 표현식의 유니코드 보조 문자에 대한 추가 지원을 위해 확장되었다.built-ins은 하위 분류를 통해 확장 가능해졌다. 제6판은 정규적이고 점진적인 언어 및 라이브러리 개선을 위한 기초를 제공한다. 제6판은 2015년 6월 총회에서 채택되었다.
- ECMA스크립트 2016은 Ecma TC39의 새로운 연간 출시와 오픈 개발 과정으로 출시된 최초의 ECMA스크립트 에디션이다. ECMAScript 2015 소스 문서에서 일반 텍스트 소스 문서는 전적으로 깃허브에서 추가 개발을 위한 기초가 되었다. 이 표준이 개발되는 1년 동안 수천 개의 버그 수정, 편집 수정 및 기타 개선 사항을 나타내는 수백 개의 pull requests과 issues가 접수되었습니다. 또한 Ecmarkup, Ecmarkdown, Grammarkdown을 포함한 수많은 소프트웨어 도구들이 개발되었다. ES2016은 또한 새로운 거듭제곱근 연산자에 대한 지원을 포함하였으며, 포함이라는 새로운 메소드를 Array.protype에 추가하였다.
- ECMA스크립트 2017은 비동기 함수, Shared Memory, Atomics를 더 작은 언어와 라이브러리 개선, 버그 수정, 편집 업데이트와 함께 도입하였다. 비동기 함수는 약속 반환 함수에 대한 구문을 제공함으로써 비동기 프로그래밍 경험을 향상시킨다. Shared Memory와 Atomics는 병렬 CPU에서도 잘 정의된 실행 순서를 보장하는 Atomics 연산을 사용하여 multi-[agent](https://tc39.es/ecma262/#agent) 프로그램이 통신할 수 있는 새로운 [메모리 모델](https://tc39.es/ecma262/#sec-memory-model)을 도입한다. 또한 오브젝트에 대한 새로운 정적 메서드도 포함되었습니다. Object.values, Object.entries 및 Object.getOwnPropertyDescriptors.
-

ECMAScript 2018 introduced support for asynchronous iteration via the AsyncIterator protocol and async generators. It also included four new regular expression features: the **`dotAll`** flag, named capture groups, Unicode property escapes, and look-behind assertions. Lastly it included object rest and spread properties.

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
- ECMAScript 2018은 AsyncIterator 프로토콜과 비동기 생성기를 통한 비동기 반복 지원을 도입하였다. 또한 dotAll 플래그, 명명된 캡처 그룹, 유니코드 속성 이스케이프 및 look-behind assertions의 네 가지 새로운 정규 표현 기능을 포함했습니다. 마지막으로 객체 rest과 spread 속성을 포함했습니다.
- ECMAScript 2019는 널리 구현되었지만 표준이 아닌 String.protype에 대한 더 나은 이름으로 Object.entries의 반환 값을 직접 새로운 개체로 바꾸기 위한 Object.fromEntries, trimStart 및 trimEndonString.protype 등 몇 가지 새로운 내장 기능을 도입했다.**`trimLeft`**및 트림 **`trimRight`**내장. 또한 구문과 의미론에 대한 몇 가지 사소한 업데이트도 포함되어 있었다. 업데이트된 구문에는 선택적 캐치 바인딩 매개 변수가 포함되어 있으며 문자열 리터럴의 U+2028(라인 구분자) 및 U+2029(문단 구분자)가 JSON과 정렬할 수 있습니다. 다른 업데이트에는 해당 Array.protype이 필요합니다.정렬은 안정적인 정렬이어야 하며, JSON.stringify가 입력에 관계없이 잘 형성된 UTF-8을 반환하도록 요구하고, Function.protype.toString이 해당 원본 텍스트 또는 표준 자리 표시자를 반환하도록 요구하여 명확화해야 합니다.
- 11번째 에디션인 ECMAScript 2020은 글로벌 정규식에 의해 생성된 모든 매치 객체에 대한 반복기, 동적 지정자를 가진 모듈을 비동기적으로 가져오기 위한 구문인 import(), 임의의 정밀 정수로 작업하기 위한 새로운 숫자 원시값 BigInt, Promise를 생성하기 위해 matchAll 메서드를 도입하였다.단락되지 않는 새로운 약속 조합인 **`Promise.allSettled`**; 글로벌이 값은 글로벌하게 이 값에 액세스하는 일반적인 방법입니다. **`export * as ns from 'module`** 문법 전용은 모듈 내에서 사용할 수 있습니다. **for-in**은 입력 순서로 열거합니다. **`import.meta`** 는 모듈들의 모듈 정보를 포함합니다. 두 가지 새로운 구문 기능을 추가하여 "nullish" 값**`null`** or **`undefined`**)으로 작업 개선해서 nullish를 병합해서 값 선택연산자를 향상 시켰습니다. 그리고 함수호출 연산자에 엑세스/호출값 값이 null인 경우 단락시킵니다.
- 12번째 에디션인 ECMA스크립트 2021은 문자열에 대한 replaceAll 방법을 도입했습니다. **Promise.any는** 입력값이 충족되었을때 종료됩니다. **AggregateError**는 새로운 에러 타입으로 멀티플 에러 종류중 하나입니다. 논리 연산자(**`??=`** , **`&&=`** , **`||=`** ) WeakRef는 가비지 수집에서 대상 개체를 보존하지 않고 참조하기 위한 것이며, FinalizationRegistry는 대상 개체가 가비지 수집될 때 수행되는 정리 작업의 등록 및 등록 취소 관리를 위한 것입니다. 숫자 리터럴의 구분 기호(1_000); 그리고 Array.prototype.sort가 더 정확해져서 구현에서 정의한 정렬 순서([implementation-defined](https://tc39.es/ecma262/#implementation-defined)  [sort order](https://tc39.es/ecma262/#sort-order).)를 초래하는 경우의 수를 줄였습니다.
- 13번째 에디션인 ECMAScript 2022는 최상위 수준의 모듈에서 키워드를 사용할 수 있도록 하는 최상위 수준 **await**을 \***\*도입했습니다. 새로운 클래스 요소: 공개 및 비공개 인스턴스 필드, 공개 및 비공개 정적 필드, 비공개 인스턴스 메서드 및 접근자, 비공개 정적 메서드 및 접근자 클래스 내부의 정적 블록, 클래스별로 평가 초기화 수행합니다. **#x in obj\*\* 문법은 개체에 일치하는 하위 문자열에 대한 시작 및 끝 인덱스를 제공하는 /d 플래그를 통한 정규 표현식 일치 인덱스 개인 필드가 있는지 테스트합니다, 이유는 오류 개체 속성에서 오류의 인과 관계를 기록하는 데 사용할 수 있습니다. 상대 인덱싱을 허용하는 Strings, Arrays 및 TypedArrays용 메서드 및 개체.hasOwn은 Object.protype.hasOwnProperty의 편리한 대안입니다.
- 많은 조직을 대표하는 수십 명의 개인들이 Ecma TC39 내에서 이 판의 개발과 이전 판에 매우 중요한 기여를 했다. 또한 TC39의 ECMA스크립트 노력을 지원하는 활기찬 커뮤니티가 등장했다. 이 커뮤니티는 수많은 초안을 검토하고, 수천 개의 버그 보고서를 제출했으며, 구현 실험을 수행했으며, 테스트 케이스에 기여했으며, ECMAScript에 대해 전 세계 개발자 커뮤니티에 교육했습니다. 불행하게도, 이 노력에 기여한 모든 사람과 단체를 확인하고 인정하는 것은 불가능하다.
- Allen Wirfs-Brock
  ECMA-262, Project Editor, 6th Edition
- Brian Terlson
  ECMA-262, Project Editor, 7th through 10th Editions
- Jordan Harband
  ECMA-262, Project Editor, 10th through 12th Editions

# 1 범위(**Scope**)

- 이 표준은 ECMA스크립트 2023 범용 프로그래밍 언어를 정의한다.

# 2 적합성(**Conformance)**

- ECMAScript의 적합한 구현은 이 명세서에 설명된 모든 types, values, objects, properties, functions 및 프로그램 문법과 의미론(semantics described)을 제공하고 지원해야 한다.
- ECMA스크립트의 구현은 최신 버전의 유니코드 표준과 ISO/IEC 10646에 따라 소스 텍스트 입력을 해석해야 한다.
- 서로 다른 인간 언어와 국가가 사용하는 언어 및 문화 관습에 적응해야 하는 프로그램을 지원하는 애플리케이션 프로그래밍 인터페이스(API)를 제공하는 ECMA 스크립트의 적합성 구현은 이 규격과 호환되는 최신 버전의 ECMA-402에 의해 정의된 인터페이스를 구현해야 한다.
- ECMAScript의 적합한 구현은 본 명세서에 설명된 것 이상의 추가적인 types, values, objects, properties 및 functions을 제공할 수 있다. 특히 ECMA스크립트의 적합한 구현은 본 명세서에서 설명되지 않은 특성 및 본 명세서에서 설명되는 객체에 대한 이러한 특성 값을 제공할 수 있다.
- ECMAScript의 적합한 구현은 본 명세서에서 설명되지 않은 프로그램 및 정규 표현 구문을 지원할 수 있다. 특히 ECMA스크립트의 적합성 구현은 이 규격의 하위 절 [12.7.2](https://tc39.es/ecma262/#sec-keywords-and-reserved-words)에 명시된 "미래 예약 단어(future [reserved words](https://tc39.es/ecma262/#sec-keywords-and-reserved-words))"를 사용하는 프로그램 구문을 지원할 수 있다.
- ECMA스크립트의 적합 구현은 하위조항 [17.1](https://tc39.es/ecma262/#sec-forbidden-extensions)에 금지된 확장으로 나열된 확장을 구현해서는 안 된다.
- ECMAScript의 적합한 구현은 구현 정의([implementation-defined](https://tc39.es/ecma262/#implementation-defined)), 구현 근사([implementation-approximated](https://tc39.es/ecma262/#implementation-approximated)) 또는 호스트 정의([host-defined](https://tc39.es/ecma262/#host-defined))되지 않은 모든 기능을 재정의해서는 안 됩니다.
- ECMA 스크립트의 적합한 구현은 규범적 선택적 하위 조항(Normative Optional subclauses)의 구현 여부를 선택할 수 있다. 표준 선택(Normative Optional) 동작이 구현되는 경우, 포함된 표준 선택 조항의 모든 동작이 구현되어야 합니다. 본 명세서에서 표준 선택 조항은 아래와 같이 색상 상자에 "표준 선택(Normative Optional)"이라는 단어로 표시된다.

> [NORMATIVE OPTIONAL](https://tc39.es/ecma262/#sec-conformance)(규범적 선택)
> 2.1 규범적 선택 조항 표제 예
> 예시 조항 내용

- ECMA스크립트의 적합한 구현은 표준 선택(Normative Optional) 사항으로 표시되지 않는 한 레거시(Legacy) 하위 절을 구현해야 합니다. 레거시 하위 조항에 지정된 모든 언어 특징 및 동작은 하나 이상의 바람직하지 않은 특성을 갖는다. 그러나 기존 응용 프로그램에서 계속 사용되므로 이 규격에서 제거할 수 없습니다. 이러한 기능은 핵심 ECMA스크립트 언어의 일부로 간주되지 않습니다. 프로그래머는 새로운 ECMA스크립트 코드를 작성할 때 이러한 특징과 동작이 존재한다고 가정하거나 사용해서는 안 된다.

> [LEGACY](https://tc39.es/ecma262/#sec-conformance)
> 2.2 레거시 조항 제목의 예

> [NORMATIVE OPTIONAL](https://tc39.es/ecma262/#sec-conformance), [LEGACY](https://tc39.es/ecma262/#sec-conformance)(규범적 선택, 레거시)
> 2.3 레거시 규범적 선택적 조항 표제 예

# 3 규범적 참조(**Normative References)**

- 다음 참조 문서는 이 문서의 적용에 필수적이다. 날짜가 적힌 참고문헌의 경우 인용된 판만 적용된다. 날짜가 없는 참조의 경우 참조 문서의 최신판(수정사항 포함)이 적용된다.
- ISO/IEC 10646 정보 기술 — Universal Multiple-Octet Coded Character Set(UCS) + 수정판 1:2005, 수정판 2:2006, 수정판 3:2008 및 수정판 4:2008 및 추가 수정판 및 수정판 또는 후속판
- ECMA-402, _ECMAScript 2015 국제화 API 사양._
  [https://ecma-international.org/publications/standards/Ecma-402.htm](https://ecma-international.org/publications/standards/Ecma-402.htm)
- ECMA-404, JSON 데이터 교환 형식.
  \*\*[https://ecma-international.org/publications/standards/Ecma-404.htm](https://ecma-international.org/publications/standards/Ecma-404.htm)

# 4 개요

- 이 섹션에는 ECMAScript 언어에 대한 비표준 개요가 포함되어 있다.
- ECMAScript는 호스트 환경([host environment](https://tc39.es/ecma262/#host-environment)) 내에서 계산을 수행하고 계산 객체를 조작하기 위한 객체 지향(object-oriented) 프로그래밍 언어이다. 여기에 정의된 ECMA스크립트는 계산상 자급자족할 수 있도록 의도된 것이 아니다. 실제로 이 규격에는 외부 데이터의 입력이나 계산 결과의 출력에 대한 조항이 없다. 대신, ECMAScript 프로그램의 계산 환경은 이 사양에 설명된 객체 및 기타 기능뿐만 아니라 설명과 동작이 액세스할 수 있는 특정 속성과 ECMAScript 프로그램에서 호출할 수 있는 특정 기능을 제공할 수 있다.
- ECMA스크립트는 원래 스크립팅 언어로 사용하도록 설계되었지만 범용 프로그래밍 언어로 널리 사용되고 있다. 스크립트 언어는 기존 시스템의 기능을 조작, 사용자 지정 및 자동화하는 데 사용되는 프로그래밍 언어입니다. 이러한 시스템에서 유용한 기능은 이미 사용자 인터페이스를 통해 사용할 수 있으며 스크립트 언어는 프로그램 제어에 해당 기능을 노출시키는 메커니즘(사물의 작용 원리·구조)이다. 이와 같이 기존 시스템은 객체와 설비의 호스트 환경([host environment](https://tc39.es/ecma262/#host-environment))을 제공하여 스크립트 언어의 기능을 완성한다고 한다. 스크립트 언어는 전문 프로그래머와 비전문 프로그래머가 모두 사용할 수 있도록 고안되었다.
- ECMA스크립트는 원래 웹 스크립팅 언어로 설계되었으며 웹 기반 클라이언트 서버 아키텍처(시스템구성)의 일부로 웹 페이지를 활성화하고 서버 계산을 수행할 수 있는 메커니즘을 제공합니다. ECMA스크립트는 이제 다양한 호스트 환경에 핵심 스크립팅 기능을 제공하는 데 사용됩니다. 따라서 핵심 언어는 특정 호스트 환경과 별개로 이 문서에 명시되어 있습니다.
- ECMA스크립트 사용은 단순한 스크립팅을 넘어섰고 이제는 다양한 환경과 규모의 모든 프로그래밍 작업에 사용된다. ECMA스크립트의 사용이 확대됨에 따라, ECMA스크립트가 제공하는 기능과 기능도 확장되었습니다. ECMA스크립트는 이제 완전한 기능을 갖춘 범용 프로그래밍 언어이다.

## 4.1 웹 스크립팅

- 웹 브라우저는 예를 들어 창, 메뉴, 팝업, 대화 상자, 텍스트 영역, 앵커, 프레임, 히스토리, 쿠키 및 입출력을 나타내는 객체를 포함하여 클라이언트 측 계산을 위한 ECMA스크립트 호스트 환경을 제공한다. 또한 호스트 환경은 초점 변경, 페이지 및 이미지 로드, 언로드, 오류 및 중단, 선택, 양식 제출 및 마우스 동작과 같은 이벤트에 스크립트 코드를 첨부할 수 있는 수단을 제공합니다. 스크립팅 코드는 HTML 내에 나타나고 표시된 페이지는 사용자 인터페이스 요소와 고정 및 계산된 텍스트 및 이미지의 조합이다. 스크립팅 코드는 사용자 상호작용(interaction)에 반응하고, 별도의 메인 프로그램이 필요하지 않다.
- 웹 서버는 요청, 클라이언트 및 파일을 나타내는 개체와 데이터를 잠그고 공유하는 메커니즘을 포함하여 서버 측 계산을 위한 다른 호스트 환경을 제공한다. 브라우저 측과 서버 측 스크립트를 함께 사용함으로써 웹 기반 애플리케이션을 위한 사용자 인터페이스를 제공하는 동시에 클라이언트와 서버 간에 계산을 분산시킬 수 있다.
- ECMAScript를 지원하는 각 웹 브라우저와 서버는 자체 호스트 환경을 제공하여 ECMAScript 실행 환경을 완성한다.

## 4.2 호스트 및 구현(Hosts and Implementations)

- ECMAScript를 호스트 환경에 통합하는 것을 돕기 위해 이 사양은 전체 또는 부분적으로 특정 기능(예: 추상 작업 e.g., [abstract operations](https://tc39.es/ecma262/#sec-algorithm-conventions-abstract-operations))에 대한 정의를 이 사양 외부의 소스로 미루고 있다. 편집상 이 사양은 다음과 같은 종류의 연기를 구분한다.
- 구현은 부록 [D](https://tc39.es/ecma262/#sec-host-layering-points)에 열거된 시설이나 구현 정의([implementation-defined](https://tc39.es/ecma262/#implementation-defined)) 또는 구현 근사치([implementation-approximated](https://tc39.es/ecma262/#implementation-approximated))로 표시된 시설을 추가로 정의하는 외부 소스이다. 비공식적인 사용에서 구현은 특정 웹 브라우저와 같은 구체적인 인위구조(concrete artefact,)를 의미한다.
- 구현 정의 기능(implementation-defined)은 추가 자격 요건 없이 외부 소스에 대한 정의를 연기하는 기능이다. 이 규격은 특정 동작에 대한 권장 사항을 제공하지 않으며, 적합한 구현은 이 사양에서 제시된 제약 조건 내에서 동작을 자유롭게 선택할 수 있다.
- 구현 근사 기능(implementation-approximated)은 이상적인 행동을 권장하면서 외부 소스에 대한 정의를 연기하는 기능이다. 적합한 구현은 본 명세서에 의해 제시된 제약 조건 내에서 어떤 행동도 자유롭게 선택할 수 있지만, 이상에 근접하기 위해 노력하는 것이 권장된다. [Math.exp](https://tc39.es/ecma262/#sec-math.exp)와 같은 일부 수학적 연산은 구현에 근사적이다([implementation-approximated](https://tc39.es/ecma262/#implementation-approximated)).
- 호스트는 부록 D에 나열된 기능을 추가로 정의하지만 다른 구현 정의([implementation-defined](https://tc39.es/ecma262/#implementation-defined)) 또는 구현 근사 기능([implementation-approximated](https://tc39.es/ecma262/#implementation-approximated))을 추가로 정의하지는 않는 외부 소스이다. 비공식적인 사용에서 호스트([host](https://tc39.es/ecma262/#host))는 부록 [D](https://tc39.es/ecma262/#sec-host-layering-points)를 통해 동일한 방식으로 이 사양과 인터페이스하는 모든 웹 브라우저의 집합과 같은 모든 구현의 집합을 의미한다. 호스트([host-defined](https://tc39.es/ecma262/#host-defined))는 종종 WHATWG HTML([https://html.spec.whatwg.org/](https://html.spec.whatwg.org/))과 같은 외부 사양이다. 즉, 호스트 정의 설비는 종종 외부 사양에서 추가로 정의된다.
- 호스트 후크는 외부 소스에 의해 전체 또는 부분적으로 정의되는 추상 작업이다. 모든 호스트 후크([host hooks](https://tc39.es/ecma262/#host-hook))는 부록 [D](https://tc39.es/ecma262/#sec-host-layering-points)에 나열되어야 한다. 호스트 후크는 최소한 다음 요구 사항을 준수해야 한다.
  - 일반 완료([normal completion](https://tc39.es/ecma262/#sec-completion-record-specification-type)) 또는 throw 완료([hrow completion](https://tc39.es/ecma262/#sec-completion-record-specification-type))를 반환해야 한다.
- 호스트 정의([host-defined](https://tc39.es/ecma262/#host-defined)) 기능은 추가 자격 없이 외부 소스에 대한 정의를 연기하는 기능이며 부록 D에 열거되어 있다. 호스트가 아닌 구현에서도 호스트 정의 기능에 대한 정의를 제공할 수도 있다.
- 호스트 환경은 모든 호스트 정의 기능에 대한 특정 정의 선택 항목이다. 호스트 환경은 일반적으로 입력을 얻고 출력을 전역 객체(global object)의 호스트 정의 속성으로 제공할 수 있는 객체(object) 또는 함수(function) 기능이 포함한다.
- 이 사양은 항상 가장 구체적인 용어를 사용하는 편집 규칙을 따른다. 예를 들어, 기능이 호스트 정의([host-defined](https://tc39.es/ecma262/#host-defined))인 경우 구현 정의([implementation-defined](https://tc39.es/ecma262/#implementation-defined))로 지칭해서는 안 됩니다.
- 호스트([hosts](https://tc39.es/ecma262/#host)) 및 구현체 모두 본 명세서에 정의된 언어(language) 유형, 사양(specification) 유형, 추상 연산([abstract operations](https://tc39.es/ecma262/#sec-algorithm-conventions-abstract-operations)), 문법 생성(grammar productions), 고유 객체(intrinsic objects) 및 고유 기호(intrinsic symbols)를 통해 본 명세서와 인터페이스할 수 있다.

## 4.3 ECMAScript 개요

- 다음은 ECMA스크립트의 비공식적인 개요이다. 언어의 모든 부분이 설명되지않는다. 이 개요는 표준 사양의 일부가 아니다.
- ECMAScript는 객체 기반이다. 기본 언어와 호스트 기능은 객체에 의해 제공되며 ECMAScript 프로그램은 통신 객체의 클러스터(무리, 떼)이다. ECMAScript에서 개체는 각 속성을 사용할 수 있는 방법을 결정하는 속성을 가진 0개 또는 이상의 속성(property) 집합이다. 예를 들어 속성에 대한 쓰기 가능 속성(Writable attribute)이 false로 설정되면, 실행된 ECMAScript 코드가 속성에 다른 값을 할당하려고 하면 실패한다. 속성(Properties)은 다른 개체, 기본(primitive) 값 또는 함수를 포함하는 컨테이너이다. 기본(primitive) 값은 다음 내장 유형 중 하나이다. Undefined, Null, Boolean, Number, BigInt, String 및 \*\*\*\*Symbol. 객체는 기본 제공 유형의 객체(Object)이고 함수로 호출 가능한 객체이다. 속성을 통해 객체와 연관된 함수를 메서드라고 한다.
- ECMAScript는 ECMAScript 엔티티의 정의를 완성하는 내장 객체 모음을 정의한다. 이러한 내장 객체에는 전역 객체(global object)가 포함한다. Object, Function, Boolean, Symbol 및 다양한 Error 객체를 포함하여 언어의 런타임 의미론(runtime semantics)에 기본이 되는 객체; Math, Number 및 Date를 포함한 숫자 값을 나타내고 조작하는 객체; 텍스트 처리 객체 String 및 RegExp; 모든 요소에 특정 숫자 데이터 표현이 있는 Array 및 9가지 다른 종류의 Typed Array를 포함한 값의 인덱스 컬렉션인 객체; Map 및 Set 개체를 포함한 키 모음; JSON 객체, ArrayBuffer, SharedArrayBuffer 및 DataView를 포함한 구조화된 데이터를 지원하는 객체; 제너레이터 함수 및 Promise 객체를 포함한 제어 추상화를 지원하는 객체; Proxy 및 Reflect를 포함한 반사 객체.
- ECMAScript는 또한 기본 제공 연산자 집합을 정의한다. ECMA스크립트 연산자에는 다양한 단항(unary) 연산자, 곱셈(multiplicative) 연산자, 덧셉(additive) 연산자, 비트 이동(bitwise shift) 연산자, 관계(relational) 연산자, 등호(equality) 연산자, 이진 비트(binary bitwise) 연산자, 이진 논리(binary logical) 연산자, 할당(assignment) 연산자, 쉼표(comma) 연산자가 포함된다.
- 거대한 ECMA스크립트 프로그램은 프로그램이 여러 개의 문과 선언 시퀀스로 분할될 수 있도록 하는 모듈에 의해 지원한다. 각 모듈은 다른 모듈에서 제공해야 하는 선언과 다른 모듈에서 사용할 수 있는 선언을 명시적으로 식별한다.
- ECMA스크립트 문법은 의도적으로 자바 문법과 유사하게 만들었다. ECMA스크립트 구문은 사용하기 쉬운 스크립트 언어 역할을 할 수 있도록 하기위해서다. 예를 들어, 변수는 어떤 타입을 선언하거나 속성과 관련된 타입이 필요하지 않으며, 정의된 함수는 변수로 의한 호출 전에 함수 선언이 텍스트로 표시할 필요가 없다.

### 4.3.1 객체 (Objects)

- ECMAScript는 클래스 정의에 대한 구문을 포함하지만 ECMAScript 객체는 C++, Smalltalk 또는 Java와 같이 기본적으로 클래스 기반은 아니다. 대신 오브젝트는 리터럴 표기법이나 오브젝트를 만든 다음 초기값을 속성에 할당하여 오브젝트의 전부 또는 일부를 초기화하는 코드를 실행하는 생성자(_[constructors](https://tc39.es/ecma262/#constructor)_)를 통해 다양한 방법으로 생성될 수 있다. 각 생성자는 프로토타입 기반 상속 및 공유 속성을 구현하는 데 사용되는 **"prototype"** 이라는 속성을 가진 함수이다. 개체는 **새**(**new) 표현**에서 생성자를 사용하여 작성된다. 예를 들어, **`new Date(2009, 11)`**는 새 날짜 개체를 작성한다. new를 사용하지 않고 생성자를 호출하면 생성자에 따라 결과가 달라진다. 예를 들어, **`Date()`**는 개체가 아닌 현재 날짜와 시간을 나타내는 문자열을 생성한다.
- 생성자에 의해 생성된 모든 객체는 생성자의 "prototype” 속성의 값에 대한 암묵적인 참조(객체의 프로토타입이라고 함)를 갖는다. 게다가, 프로토타입은 그 프로토타입에 대해 Null이 아닌 암묵적인 참조 등을 가질 수 있다. 이것을 **prototype chain**이라고 한다. 개체에서 속성을 참조할 때 해당 이름의 속성을 포함하는 프로토타입 체인의 첫 번째 개체에 있는 해당 이름의 속성을 참조한다. 다시 말해, 먼저 직접 언급된 객체가 그러한 속성에 대해 조사한다. 해당 객체가 명명된 속성을 포함하는 경우 참조가 참조하는 속성이다. 해당 객체에 명명된 속성이 포함하지 않으면 해당 객체의 프로토타입이 다음에 검사된다.
  ![image](https://user-images.githubusercontent.com/83447120/192537705-4c326378-d012-410c-89f6-54d59a0b8062.png)

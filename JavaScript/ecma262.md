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
- 클래스 기반 객체 지향 언어에서 일반적으로 상태는 인스턴스에 의해 전달되고 메서드는 클래스에 의해 전달되며 상속은 구조와 동작에만 있다. ECMA스크립트에서 상태와 메서드는 객체에 의해 전달되는 반면 구조, 동작 및 상태는 모두 상속된다.
- 프로토타입에 포함된 특정 속성을 직접 포함하지 않는 모든 객체는 해당 속성과 값을 공유한다. 그림 1(Figure 1)은 이를 보여준다.
- CF는 생성자(물체)이기도 하다. cf1, cf2, cf3, cf4 및 cf5의 새 표현식을 사용하여 5개의 객체가 생성되었다. 각 개체에는 "q1" 및 "q2"라는 속성이 포함되어 있다. 예를 들어, cf3의 원형은 CFp이다. 생성자인 CF는 "P1"과 "P2"라는 두 가지 속성을 가지고 있는데, CFp, cf1, cf2, cf3, cf4 또는 cf5에는 보이지 않는다. CFp에서 "CFP1"이라는 이름은 cf1, cf2, cf3, cf4 및 cf5에 의해 공유되며(CF에서는 공유되지 않음), "q1", "q2" 또는 "CFP1"로 명명되지 않은 CFp의 암시적 프로토타입 사슬에서 발견되는 모든 특성도 공유된다. CF와 CFP 사이에는 암시적인 프로토타입 링크가 없다.
- 대부분의 클래스 기반 객체 언어와 달리 속성은 객체에 값을 할당하여 객체에 동적으로 추가할 수 있다. 즉, 생성자는 생성된 개체의 속성 전부 또는 일부에 이름을 지정하거나 값을 할당할 필요가 없다. 위의 그림1에서 CFp의 속성에 새 값을 할당하여 cf1, cf2, cf3, cf4 및 cf5에 대한 새 공유 속성을 추가할 수 있다.
- ECMA스크립트 객체는 본질적으로 클래스 기반은 아니지만 생성자 함수, 프로토타입 객체 및 메서드의 공통 패턴을 기반으로 클래스 유사 추상화를 정의하는 것이 편리한 경우가 많다. ECMAScript 내장 개체 자체는 이러한 클래스와 유사한 패턴을 따른다. ECMAScript 2015부터 ECMAScript 언어는 프로그래머가 동일한 클래스 같은 추상화 패턴을 간결하게 객체를 정의할 수 있도록하는 클래스 정의 문법을 포함한다.

### 4.3.2 **ECMA스크립트의 엄격한 변형** (**The Strict Variant of ECMAScript**)

- ECMA스크립트 언어는 일부 사용자가 언어에서 사용할 수 있는 일부 기능 사용을 제한 할 수 있다고 인식한다. 보안을 위해, 오류가 발생하기 쉬운 기능을 회피하거나, 오류 검사를 강화하거나, 선택한 다른 이유로 그렇게 할 수 있다. 이 가능성을 뒷받침하기 위해 ECMA스크립트는 언어의 엄격한 변형을 정의한다. 언어의 엄격한 변형은 일반 ECMA스크립트 언어의 일부 특정한 구문 및 의미적 기능을 배제하고 일부 기능의 세부 의미를 수정한다. 엄격한 변형은 또한 언어의 엄격하지 않은 언어 형식에서 오류로 지정되지 않은 상황에서 오류 예외를 발생시켜 보고해야 하는 추가 오류 조건을 명시한다.
- ECMA스크립트의 엄격한 변형은 일반적으로 언어의 엄격한 모드(_strict mode_)라고 불린다. ECMA스크립트의 엄격한 모드(strict mode) 문법 및 의미체계의 사용은 [11.2.2](https://tc39.es/ecma262/#sec-strict-mode-code)에 설명된 개별 [ECMAScript source text](https://tc39.es/ecma262/#sec-source-text) 단위 수준에서 명시적으로 이루어진다. 엄밀한 모드는 문법 소스 텍스트 단위 수준에서 선택되기 때문에 엄밀한 모드는 그러한 소스 텍스트 단위 내에서 로컬 효과가 있는 제한만 부과한다. 엄격한 모드는 여러 소스 텍스트 단위에서 일관되게 작동해야 하는 ECMA스크립트 의미체계의 어떤 측면도 제한하거나 수정하지 않는다. 완전한 ECMA스크립트 프로그램은 엄격한 모드와 비 엄격한 모드 [ECMAScript source text](https://tc39.es/ecma262/#sec-source-text)단위로 구성될 수 있다. 이 경우 엄격한 모드는 엄격한 모드 소스 텍스트 단위 내에 정의된 코드를 실제로 실행할 때만 적용된다.
- 이 사양을 준수하기 위해 ECMA스크립트 구현은 제한되지 않는 전체 ECMA스크립트 언어와 이 사양에 정의된 ECMA스크립트 언어의 엄격한 변형을 모두 구현해야 한다. 또한, 구현은 제한되지 않는 모드와 엄격한 모드의 소스 텍스트 단위를 단일 복합 프로그램(single composite program)으로 결합하는 것을 지원해야 한다.

## 4.4 용어 및 정의 (Terms and Definitions)

- 이 문서의 목적상 다음 용어와 정의가 적용된다.

### 4.4.1 구현 근사 (implementation-approximated)

- 구현 근사([implementation-approximated](https://tc39.es/ecma262/#implementation-approximated)) 기능은 외부 소스에 의해 전체 또는 부분적으로 정의되지만 이 규격에서 권장되는 이상적인 동작을 가지고 있다.

### 4.4.2 구현 정의 (**implementation-defined)**

- 구현 정의 기능([implementation-defined](https://tc39.es/ecma262/#implementation-defined))은 이 규격의 외부 소스에 의해 전체 또는 부분적으로 정의된다.

### 4.4.3 호스트 정의 (host-defined)

- **구현 정의(**[implementation-defined](https://tc39.es/ecma262/#implementation-defined)**)와 동일**

> 편집상 [4.2](https://tc39.es/ecma262/#sec-hosts-and-implementations)항에 해당

### 4.4.4 타입 (Type)

- [6](https://tc39.es/ecma262/#sec-ecmascript-data-types-and-values)항에 정의된 데이터 값 집합

### 4.4.5 원시값 (**primitive value)**

- [6](https://tc39.es/ecma262/#sec-ecmascript-data-types-and-values)항에서 정의된 Undefined, Null, Boolean, Number, BigInt, Symbol 또는 String 유형 중 하나의 멤버

> 원시 값은 언어 구현의 가장 낮은 수준에서 직접 표현되는 기준이다.

### 4.4.6 객체 (Object)

- 객체 유형의 멤버

> 객체는 속성의 집합이며 단일 프로토타입 객체를 가지고 있다. 프로토타입이 null일 수 있다.

### 4.4.7 생성자 (constructor)

- 객체를 생성하고 초기화하는 함수 객체([function object](https://tc39.es/ecma262/#function-object))

> 생성자의 "prototype" 속성 값은 상속 및 공유 속성을 구현하는 데 사용되는 프로토타입 개체이다.

### 4.4.8 프로토타입 (**prototype**)

- **다른 객체에 대한 공유 속성을 제공하는 객체**

> 생성자가 객체를 만들 때 해당 개체는 속성 참조를 해결하기 위해 생성자의 "prototype" 속성을 암묵적으로 참조한다. 생성자의 "protype" 속성은 프로그램 표현식 constructor.protype에 의해 참조될 수 있으며 객체의 프로토타입에 추가된 속성은 상속을 통해 프로토타입을 공유하는 모든 객체에 의해 공유된다. 또는 Object.create 내장 함수를 사용하여 명시적으로 지정된 프로토타입으로 새 객체를 만들 수 있다.

### 4.4.9 보통 객체 (**ordinary object**)

- 모든 객체가 지원해야 하는 필수 내부 메서드에 대한 기본 동작을 갖는 객체

### 4.4.10 예외적인 객체 (exotic object)

- 하나 이상의 필수 내부 메소드에 대한 기본 동작이 없는 객체

> 보통 객체([ordinary object](https://tc39.es/ecma262/#ordinary-object))가 아니면 이국적인 객체([exotic object](https://tc39.es/ecma262/#exotic-object))이다.

### 4.4.11 기준 객체 (standard object)

- **이 규격에 의해 의미론(semantics)이 정의된 객체**

### 4.4.12 내장 객체 (built-in object)

- ECMA스크립트 구현에 지정되고 제공된 객체

> 표준 내장 객체는 이 규격에 정의되어 있다. ECMA스크립트 구현은 추가적인 종류의 내장 객체를 지정하고 제공할 수 있다. 기본 생성자(_[constructor](https://tc39.es/ecma262/#constructor)_)는 생성자(_[constructor](https://tc39.es/ecma262/#constructor)_)인 내장 객체입니다.

### 4.4.13 정의되지 않은 값 (**undefined value)**

- 변수에 값이 할당되지 않을 때 사용되는 원시 값

### 4.4.14 정의되지 않은 타입 (Undefined type)

- 유일한 값이 정의되지 않은 값인 타입

### 4.4.15 빈 값 (null value)

- 객체 값을 의도적으로 없음(null)을 나타내는 원시 값

### 4.4.16 빈 타입 (**Null type)**

- 유일한 값이 null 값인 타입

### 4.4.17 불린 값 (**Boolean value**)

- 불린 타입([Boolean type](https://tc39.es/ecma262/#sec-ecmascript-language-types-boolean-type))의 종류

> 불린 값은 true와 false 두 개뿐이다.

### 4.4.19 불린 객체 (**Boolean object)**

- 표준 내장 불린 생성자([constructor](https://tc39.es/ecma262/#constructor))의 사례에 객체 타입의 종류다

> 불린 객체는 불린 값을 인수(argument)로 제공하여 새 표현식에서 불린 생성자를 사용하여 생성한다. 결과 객체에 불린 값의 내부 슬롯이 있다. 불린 객체는 불린 값으로 강제변환 할 수 있다.

### 4.4.20 문자열 값 (String value)

- 0 또는 그 이상의 16비트 부호 없는 정수([integer](https://tc39.es/ecma262/#integer)) 값의 유한한([finite](https://tc39.es/ecma262/#finite)) 순서 시퀀스인 원시 값

> String 값은 String 타입([String type](https://tc39.es/ecma262/#sec-ecmascript-language-types-string-type))의 멤버입니다. 시퀀스의 각 정수 값은 일반적으로 UTF-16 텍스트의 단일 16비트 단위를 나타낸다. 그러나 ECMAScript는 값이 16비트 부호 없는 정수여야 한다는 점을 제외하고는 값에 제한이나 요구 사항을 두지 않는다.

### 4.4.21 문자열 타입 (**String type)**

- **가능한 모든 문자열 값 집합**

### 4.4.22 문자열 객체 (**String object)**

- 표준 내장 String 생성자([constructor](https://tc39.es/ecma262/#constructor))의 사례인 Object 타입의 멤버

> String 객체는 String 값을 인수(argument)로 제공하여 새 표현식에서 String 생성자를 사용하여 생성한다. 결과 객체에는 값이 문자열 값인 내부 슬롯이 있다. String 객체는 String 생성자를 함수로 호출하여 String 값으로 강제 변환할 수 있습니다([22.1.1.1](https://tc39.es/ecma262/#sec-string-constructor-string-value))

### 4.4.23 숫자 값 (**Number value)**

- 배정밀도(double-precision) 64비트 이진 형식[IEEE 754-2019](https://tc39.es/ecma262/#sec-bibliography) 값에 해당하는 기본 값

### 4.4.24 숫자 타입 (Number type)

- 특별한 "Not-a-Number"(NaN) 값, 양의 무한대 및 음의 무한대를 포함한 모든 숫자 값의 집합

### 4.4.25 숫자 객체 (**Number object)**

- 표준 내장 Number 생성자([constructor](https://tc39.es/ecma262/#constructor))의 인스턴스(instance 사례, 예)인 Object 타입의 멤버

> Number 객체는 새 표현식에서 Number 생성자를 사용하여 생성되고 Number 값을 인수로 제공한다. 결과 개체에는 값이 숫자 값인 내부 슬롯이 있다. Number 객체는 Number 생성자를 함수로 호출하여 Number 값으로 강제 변환할 수 있다([21.1.1.1](https://tc39.es/ecma262/#sec-number-constructor-number-value))

### 4.4.26 무한대 (**Infinity)**

- 양의 무한 숫자 값인 숫자 값

### 4.4.27 숫자가 아닌 (NaN = Not-a-Number)

- [IEEE 754-2019](https://tc39.es/ecma262/#sec-bibliography) "Not-a-Number" 값인 숫자 값

### 4.4.28 큰 수 값(BigInt value)

- 임의의 추출한 정수([integer](https://tc39.es/ecma262/#integer)) 값에 해당하는 기본 값

### 4.4.29 큰 수 타입 (BigInt type)

- 가능한 모든 BigInt 값의 집합

### 4.4.30 큰 수 객체 (**BigInt object**)

- 표준 내장 BigInt 생성자([constructor](https://tc39.es/ecma262/#constructor))의 인스턴스(사례,예)인 Object 유형의 멤버

### 4.4.31 기호 값 (**Symbol value)**

- 고유한 비 문자열 객체 속성 키([property key](https://tc39.es/ecma262/#sec-object-type))를 나타내는 기본 값

### 4.4.32 기호 타입 (**Symbol type)**

- **가능한 모든 기호 값 집합**

### 4.4.33 기호 객체 (**Symbol object)**

- 표준 내장 Symbol 생성자의 인스턴스(사례,예)인 Object 유형의 멤버

### 4.4.34 함수 (**function**)

- 서브루틴으로 호출될 수 있는 Object 유형의 멤버

> 함수에는 속성(properties) 외에도 호출될 때 동작하는 방식을 결정하는 실행 코드와 상태가 포함되어 있다. 함수의 코드는 ECMAScript로 작성되거나 작성되지 않을 수 있다.

### 4.4.35 내장 함수 (**built-in function**)

- 함수인 내장 객체

> 내장 함수의 예로는 parseInt 및 Math.exp가 있다. 호스트([host](https://tc39.es/ecma262/#host)) 또는 구현은 이 명세서에 설명되지 않은 추가 내장 기능을 제공할 수 있다.

### 4.4.36 속성 (property)

- : HTML DOM트리안의 Attribute표현
    <div class =”divClassName”> → className 의 property는 divClassName 라는 attribute 값을 가진다.

- 키(문자열 값 또는 기호 값)나 값을 연결하는 객체의 일부

> 속성의 형식에 따라 값은 데이터 값(기본값, 객체 또는 함수 객체([function object](https://tc39.es/ecma262/#function-object)))으로 직접 표시되거나 한 쌍의 접근자 함수에 의해 간접적으로 표시될 수 있다.

### 4.4.37 메서드 (**method)**

- 속성의 값인 함수

> 함수가 객체의 메소드(method)로 호출되면 객체는 this 값으로 함수에 전달된다.

### 4.4.38 내장 메서드 (**built-in method)**

- 내장 함수인 메소드

> 표준 내장 메소드는 이 명세서에 정의되어 있다. 호스트 또는 구현([host](https://tc39.es/ecma262/#host))은 이 명세서에 설명되지 않은 추가 내장 메서드를 제공할 수 있다.

### 4.4.39 속성 (**attribute**)

- : HTML 요소의 추가적인 정보
    <div class =”divClassName”> → class라는 attribute는 값이 divClassName이다.

- 속성(property)의 어떤 특성을 정의하는 내부 값

### 4.4.40 주? 자체? 속성 (**own property**)

- 객체에 직접 포함된 속성

### 4.4.41 상속 속성 (inherited property)

- 자체(own) 속성은 아니지만 객체 프로토타입의 속성(소유(own) 또는 상속(inherited)됨)인 객체의 속성

## 4.5 이 사양의 구성 (**Organization of This Specification)**

- 이 사양의 나머지 부분은 다음과 같이 구성 :
  - [5](https://tc39.es/ecma262/#sec-notational-conventions)절은 명세서 전체에서 사용되는 표기법을 정의한다.
  - [6](https://tc39.es/ecma262/#sec-ecmascript-data-types-and-values)~[10](https://tc39.es/ecma262/#sec-ordinary-and-exotic-objects-behaviours)절은 ECMAScript 프로그램이 작동하는 실행 환경을 정의한다.
  - [11](https://tc39.es/ecma262/#sec-ecmascript-language-source-code)~[17](https://tc39.es/ecma262/#sec-error-handling-and-language-extensions)절은 문법 인코딩과 모든 언어 기능의 실행 의미를 포함하여 실제 ECMAScript 프로그래밍 언어를 정의한다.
  - [18](https://tc39.es/ecma262/#sec-ecmascript-standard-built-in-objects)~[28](https://tc39.es/ecma262/#sec-reflection)절은 ECMAScript 표준 라이브러리를 정의한다. 여기에는 ECMAScript 프로그램이 실행될 때 사용할 수 있는 모든 표준 객체의 정의가 포함된다.
  - [29](https://tc39.es/ecma262/#sec-memory-model)절은 Atomics(원자) 객체의 SharedArrayBuffer(공유 배열 버퍼) 지원 메모리와 메서드에 대한 액세스의 메모리 일관성 모델을 설명한다.

# 5. 표기법 (Notational Conventions)

## 5.1 구문 및 어휘 문법 (**Syntactic and Lexical Grammars**)

### 5.1.1 문맥 없는 문법 (**Context-Free Grammars**)

- 문맥이 없는 문법은 다수의 제품으로 구성된다. 각 제품은 비단말기라는 추상(abstract) 기호를 왼쪽에 갖고 오른쪽에는 0개 이상의 비단말기와 터미널 기호가 순서대로(sequence)를 있다. 각 문법은 터미널 기호는 지정된 알파벳에서 가져온다(drawn).
  - [https://en.wikipedia.org/wiki/Terminal_and_nonterminal_symbols](https://en.wikipedia.org/wiki/Terminal_and_nonterminal_symbols)
- 체인 제품(chain production)은 0개 이상의 터미널 기호와 함께 오른쪽에 정확히 하나의 비단말 기호가 있는 제품이다.
- 목표 기호라고 하는 하나의 구별되는 비단말로 구성된 문장에서 시작하여, 주어진 문맥 자유 구문(context-free grammar)은 언어, 즉, 시퀀스(sequences)에서 비단말기를 제품의 오른쪽 면으로 반복적으로 대체함으로써 발생할 수 있는 가능한 (아마도 무한한) 일련의 터미널 기호를 명시한다. 비단자는 왼쪽이다.

### 5.1.2 어휘 및 비정규식표현 구문 (**The Lexical and RegExp Grammars**)

- ECMAScript에 대한 어휘 문법은 [12](https://tc39.es/ecma262/#sec-ecmascript-language-lexical-grammar)절에 나와 있다. 이 문법은 터미널 기호로 [11.1](https://tc39.es/ecma262/#sec-source-text)에 정의된 SourceCharacter에 대한 규칙을 준수하는 유니코드 코드 포인트를 갖는다. 목표 기호([goal symbol](https://tc39.es/ecma262/#sec-context-free-grammars)) [InputElementDiv](https://tc39.es/ecma262/#prod-InputElementDiv), [InputElementTemplateTail](https://tc39.es/ecma262/#prod-InputElementTemplateTail),  [InputElementRegExp](https://tc39.es/ecma262/#prod-InputElementRegExp), [InputElementRegExpOrTemplateTail](https://tc39.es/ecma262/#prod-InputElementRegExpOrTemplateTail) 또는 [InputElementHashbangOrRegExp](https://tc39.es/ecma262/#prod-InputElementHashbangOrRegExp)에서 시작하여 이러한 코드 포인트의 시퀀스가 입력 요소의 시퀀스로 변환되는 방법을 설명하는 일련의 프로덕션을 정의한다.
- 공백(white space) 및 주석(comments form) 이외의 입력 요소는 ECMAScript의 구문 문법에 대한 터미널 기호를 형성하며 ECMAScript 토큰이라고 한다. 토큰은 ECMAScript 언어의 예약어([reserved words](https://tc39.es/ecma262/#sec-keywords-and-reserved-words)), 식별자(identifiers), 리터럴(literals) 및 구두점(punctuators)이다. 또한 줄 종결자(line terminators)는 토큰으로 간주되지는 않지만 입력 요소 스트림의 일부가 되어 자동 세미콜론을 삽입 프로세스를 안내한다([12.10](https://tc39.es/ecma262/#sec-automatic-semicolon-insertion)). 단순한 공백과 한 줄 주석은 무시되고 구문 문법에 대한 입력 요소의 스트림에 나타나지 않는다. [MultiLineComment](https://tc39.es/ecma262/#prod-MultiLineComment)(즉, 한 줄 이상에 걸쳐 있는지 여부에 관계없이 /**...**/ 형식의 주석)는 줄 종결자가 포함되어 있지 않으면 마찬가지로 간단히 무시된다. 그러나 [MultiLineComment](https://tc39.es/ecma262/#prod-MultiLineComment)에 하나 이상의 줄 종결자가 포함된 경우 단일 줄 종결자로 대체되어 구문 문법에 대한 입력 요소 스트림의 일부가 된다.
- ECMAScript에 대한 RegExp(정규표현식) 문법은 [22.2.1](https://tc39.es/ecma262/#sec-patterns)에 나와 있다. 이 문법은 또한 [SourceCharacter](https://tc39.es/ecma262/#prod-SourceCharacter)에 의해 정의된 코드 포인트를 터미널 기호로 가지고 있다. 코드 포인트 시퀀스가 정규식 패턴(regular expression patterns)으로 변환되는 방법을 설명하는 목표 기호([goal symbol](https://tc39.es/ecma262/#sec-context-free-grammars)) 패턴(*[Pattern](https://tc39.es/ecma262/#prod-Pattern))*에서 시작하는 일련의 프로덕션을 정의한다.
- 어휘(lexical) 및 RegExp 문법의 생성은 구두점(punctuation)을 구분하는 두 개의 콜론 "::"을 사용하여 구별한다. 어휘 및 RegExp 문법은 일부 프로덕션을 공유한다.

* 구두점 : 글의 뜻을 분명히 하기 위하여 찍는 쉼표와 마침표. 머무름표. 정류부

### 5.1.3 숫자 문자열 문법 (The Numeric String Grammar)

- 숫자 문자열 문법은 [7.1.4.1](https://tc39.es/ecma262/#sec-tonumber-applied-to-the-string-type)에 나와있다. 터미널 기호로 [SourceCharacter](https://tc39.es/ecma262/#prod-SourceCharacter)를 가지며 목표 기호([goal symbol](https://tc39.es/ecma262/#sec-context-free-grammars)) [StringNumericLiteral](https://tc39.es/ecma262/#prod-StringNumericLiteral)(숫자 리터럴([lexical grammar for numeric literals](https://tc39.es/ecma262/#sec-literals-numeric-literals))에 대한 어휘 문법과 유사하지만 구별됨)에서 시작하여 문자열을 숫자 값으로 변환하는 데 사용된다.
- 숫자 문자열 문법의 생성은 세 개의 콜론 ":::"을 구두점으로 사용하여 구별되며 소스 텍스트를 구문 분석하는 데 사용되지 않는다.

### 5.1.4 구문 문법 (**The Syntactic Grammar)**

- ECMAScript의 구문 문법은 13~16절에 나와 있다. 이 문법에는 어휘 문법에 의해 터미널 기호로 정의된 ECMAScript 토큰이 있다(5.1.2). 토큰 시퀀스가 ECMAScript 프로그램의 구문적으로 올바른 독립 구성 요소를 형성하는 방법을 설명하는 두 개의 대체 목표 기호 Script 및 Module에서 시작하는 일련의 프로덕션을 정의합니다.
- 코드 포인트 스트림이 ECMAScript 스크립트 ([Script](https://tc39.es/ecma262/#prod-Script))또는 모듈([Module](https://tc39.es/ecma262/#prod-Module))로 구문 분석(lexical grammar)될 때 먼저 어휘 문법을 반복적으로 적용하여 입력 요소 스트림으로 변환된다. 이 입력 요소 스트림은 구문 문법의 단일 응용 프로그램(single application)에 의해 구문 분석된다. 입력 요소 스트림의 토큰을 토큰이 남지 않고 목표 비터미널(([Script](https://tc39.es/ecma262/#prod-Script) or [Module](https://tc39.es/ecma262/#prod-Module))의 단일 인스턴스로 구문 분석할 수 없는 경우 입력 스트림은 구문적으로 오류가 있습니다.
- 구문 분석이 성공하면 각 노드가 구문 분석 노드인 루트 트리 구조인 구문 분석 트리를 구성한다. 각 구문 분석 노드는 문법에서 기호의 인스턴스이다. 해당 기호에서 파생될 수 있는 소스 텍스트의 범위를 나타낸다. 전체 소스 텍스트를 나타내는 구문 분석 트리의 루트 노드는 구문 분석의 목표 기호([goal symbol](https://tc39.es/ecma262/#sec-context-free-grammars))의 인스턴스이다. Parse Node가 nonterminal의 인스턴스일 때, 그 노드는 상위 노드의 왼쪽에 있는 프로덕션의 인스턴스이다. 또한, 프로덕션 오른쪽에 있는 각 기호마다 0개 또는 0개 이상의 하위 항목을 가지고 있다: 각 자식은 해당 기호의 인스턴스인 구문 분석 노드이다.

* nonterminal node 비단말 노드 : 선형궂에서 자식 노드가 없음

* [instance 인스턴스](https://terms.naver.com/entry.naver?docId=856428&cid=42346&categoryId=42346) : 객체지향프로그래밍에서 객체를 메모리에 할당 했을 때

- 새 구문 분석 노드는 구문 분석기의 각 호출에 대해 인스턴스화되며 동일한 소스 텍스트의 경우에도 구문 분석 간에 재사용되지 않는다. 구문 분석 노드는 소스 텍스트의 동일한 범위를 나타내고 동일한 문법 기호의 인스턴스이며 동일한 구문 분석기 호출의 결과인 경우에만 동일한 구문 분석 노드로 간주된다.

> 동일한 문자열을 여러 번 구문 분석하면 다른 구문 분석 노드가 생성됩니다. 예를 들어 다음을 고려한다.

```jsx
let str = "1 + 1;";
eval(str); // 문자로 표현된 JS코드를 실행하는 함수
eval(str); // 사용을 권하지 않는다
```

> eval에 대한 각 호출은 str의 값을 ECMAScript 소스 텍스트([ECMAScript source text](https://tc39.es/ecma262/#sec-source-text))로 변환하고 Parse Nodes의 개별 트리를 만드는 독립적인 파스를 수행한다. 각 구문 분석이 동일한 문자열 값에서 파생된 소스 텍스트에 대해 작동하더라도 트리는 구별된다.

> Parse Nodes는 사양 아티팩트이며 유사한 데이터 구조를 사용하기 위해 구현이 필요하지 않는다.

- 구문 문법의 생성은 구두점으로 콜론 ":"이 하나만 있는 것으로 구별한다.
- 13절에서 16절에 제시된 구문 문법은 올바른 ECMAScript 스크립트([Script](https://tc39.es/ecma262/#prod-Script)) 또는 모듈([Module](https://tc39.es/ecma262/#prod-Module))로 허용되는 토큰 시퀀스에 대한 완전한 설명이 아니다. 특정 추가 토큰 시퀀스도 허용된다. 즉, 특정 위치(예: 줄 종결자 문자 앞)의 시퀀스에 세미콜론만 추가된 경우 문법으로 설명되는 토큰 시퀀스도 허용된다. 더욱이, 문법에 의해 설명된 특정 토큰 시퀀스는 라인 종결 문자가 특정 "불편한" 위치에 나타나는 경우 허용되는 것으로 간주하지 않는다.

* [sequence](<https://ko.wikipedia.org/wiki/%EB%A6%AC%EC%8A%A4%ED%8A%B8_(%EC%BB%B4%ED%93%A8%ED%8C%85)>) 시퀀스 : [컴퓨터 과학](https://ko.wikipedia.org/wiki/%EC%BB%B4%ED%93%A8%ED%84%B0_%EA%B3%BC%ED%95%99)에서 같은 값이 한 번 이상 존재할 수 있는 일련의 [값](<https://ko.wikipedia.org/wiki/%EA%B0%92_(%EC%BB%B4%ED%93%A8%ED%84%B0_%EA%B3%BC%ED%95%99)>)이 모여있는 [추상적 자료형](https://ko.wikipedia.org/wiki/%EC%B6%94%EC%83%81%EC%A0%81_%EC%9E%90%EB%A3%8C%ED%98%95) ??

- 어떤 경우에는 모호성을 피하기 위해 구문 문법은 유효한 ECMAScript 스크립트([Script](https://tc39.es/ecma262/#prod-Script))나 모듈([Module](https://tc39.es/ecma262/#prod-Module))을 형성하지 않는 토큰 시퀀스를 허용하는 일반화된 생성을 사용한다. 예를 들어, 이 기술은 객체 리터럴 및 객체 구조 해제 패턴에 사용됩니다. 이러한 경우 허용되는 토큰 시퀀스를 더욱 제한하는 것보다 제한적인 보충 문법이 제공된다. 일반적으로 초기 오류([early error](https://tc39.es/ecma262/#early-error)) 규칙은 특정 컨텍스트(문맥)에서 "P는 N을 포함해야 한다"라고 명시한다. 여기서 P는 구문 분석 노드(일반화된 생성의 인스턴스)이고 N은 보충 문법의 비단말입니다. 이것은 다음을 의미한다 :
  1. 원래 P와 일치하는 토큰 시퀀스는 N을 목표 기호([goal symbol](https://tc39.es/ecma262/#sec-context-free-grammars))로 사용하여 다시 구문 분석된다. N이 문법적 매개변수를 취하면 P가 원래 구문 분석될 때 사용된 것과 동일한 값으로 설정된다.
  2. 토큰 시퀀스가 토큰이 남지 않고 N의 단일 인스턴스로 구문 분석될 수 있는 경우:
     1. 우리는 N의 인스턴스(주어진 P에 대해 고유한 구문 분석 노드)를 "P에 의해 커버되는 N"이라고 참조한다.
     2. N에 대한 모든 초기 오류 규칙 및 파생된 생산물은 P가 다루는 N에도 적용된다.
  3. 그렇지 않으면(구문 분석이 실패하면) 초기 구문 오류이다.

## 5.1.5 문법 표기법 (**Grammar Notation)**

### 5.1.5.1 터미널 기호 (**Terminal Symbols)**

- ECMAScript 문법에서 일부 터미널 기호는 고정 너비(fixed-width) 글꼴로 표시된다. 터미널 기호는 작성된 그대로 원본 텍스트에 표시되어야한다. 이 방법으로 지정된 모든 터미널 기호 코드 포인트는 다른 유니코드 범위에서 유사하게 보이는 코드 포인트와 달리 기본 라틴 블록의 적절한 유니코드 코드 포인트로 보아야 한다. 터미널 기호의 코드 포인트는`\` [UnicodeEscapeSequence](https://tc39.es/ecma262/#prod-UnicodeEscapeSequence)로 표현할 수 없다.

- 터미널 기호가 개별 유니코드 코드 포인트인 문법(즉, 어휘, RegExp 및 숫자 문자열 문법)에서 프로덕션에 나타나는 여러 고정 너비 코드 포인트의 연속 실행은 연속된 실행은 독립 실행형 터미널 기호로 작성된 동일한 코드 포인트 시퀀스의 간단한 축약형이다.
  - 예를 들어, 프로덕션:
    16진수 정수 리터럴 :: 0x 16진수 ([HexIntegerLiteral](https://tc39.es/ecma262/#prod-grammar-notation-HexIntegerLiteral) :: 0x [HexDigits](https://tc39.es/ecma262/#prod-HexDigits))
  - 위는 다음을 가리키는 말이다.
    16진수 정수 리터럴 :: 0 x 16진수 **(**[HexIntegerLiteral](https://tc39.es/ecma262/#prod-grammar-notation-HexIntegerLiteral) :: 0 x [HexDigits](https://tc39.es/ecma262/#prod-HexDigits)**)**
- 대조적으로, 구문 문법에서 고정 너비 코드 포인트의 연속 실행은 단일 터미널 기호이다.
- 터미널 기호는 두 가지 다른 형태로 제공된다:
  - 어휘 및 RegExp 문법에서 일반적인 인쇄 표현이 없는 유니코드 코드 포인트는 대신 "<ABBREV>" 형식으로 표시된다. 여기서 "ABBREV"는 코드 포인트 또는 코드 포인트 집합에 대한 기억을 돕는다(mnemonic). 이러한 형식은 유니코드 형식 제어 문자([Unicode Format-Control Characters](https://tc39.es/ecma262/#sec-unicode-format-control-characters)), 공백 및 줄 종결자([Line Terminators](https://tc39.es/ecma262/#sec-line-terminators))로 정의된다.
  - 구문 문법에서 특정 터미널 기호(예: [IdentifierName](https://tc39.es/ecma262/#prod-IdentifierName) 및 [RegularExpressionLiteral](https://tc39.es/ecma262/#prod-RegularExpressionLiteral))는 어휘 문법에서 동일한 이름의 비터미널을 참조하므로 이탤릭체로 표시된다.

### 5.1.5.2 비단말 기호 및 프로덕션 (Nonterminal Symbols and Productions)

- 비단말 기호는 이탤릭체로 표시된다. 비단말기("프로덕션"이라고도 함)의 정의는 정의되는 비단말기의 이름 뒤에 하나 이상의 콜론이 붙는 방식으로 도입된다. (콜론의 수는 생성이 속한 문법을 나타낸다.) 비터미널에 대한 하나 이상의 대안적인 오른쪽으로 다음 줄에 이어진다. 예를 들어 구문 정의는 다음과 같다.
  - WhileStatement :
    - while ( Expression ) Statement \* Expression : 식 , \* Statement : 문
- 비터미널 while문([WhileStatement](https://tc39.es/ecma262/#prod-grammar-notation-WhileStatement))는 토큰 while, 왼쪽 괄호 토큰, [Expression](https://tc39.es/ecma262/#prod-Expression), 오른쪽 괄호 토큰, [Statement](https://tc39.es/ecma262/#prod-Statement)를 나타낸다. [Expression](https://tc39.es/ecma262/#prod-Expression) 및 [Statement](https://tc39.es/ecma262/#prod-Statement)의 발생 자체는 비단말적이다. 또 다른 예로서 구문 정의는 다음과 같다.
  - [ArgumentList](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList):
    - [AssignmentExpression](https://tc39.es/ecma262/#prod-AssignmentExpression)
    - [ArgumentList](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList), [AssignmentExpression](https://tc39.es/ecma262/#prod-AssignmentExpression)
    * [ArgumentList](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList) 인수목록
    * [AssignmentExpression](https://tc39.es/ecma262/#prod-AssignmentExpression) 할당식
- [ArgumentList](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList)는 단일 [AssignmentExpression](https://tc39.es/ecma262/#prod-AssignmentExpression) 또는 `ArgumentList`, `AssignmentExpression` 중 하나를 나타낼 수 있다. ArgumentList의 이 정의는 재귀적이다. 즉, 자체적으로 정의된다. 결과적으로 ArgumentList는 쉼표로 구분된 양수 인수를 포함할 수 있으며 각 인수 표현식은 AssignmentExpression이다. 이러한 비터미널의 재귀적 정의는 일반적이다.

### 5.1.5.3 선택적 기호 (Optional Symbols)

- 첨자 접미사 "opt"는 터미널(terminal) 또는 비터미널(nonterminal) 뒤에 나타날 수 있으며 선택 기호를 나타낸다. 선택적 기호를 포함하는 대안은 실제로 두 개의 오른쪽면을 지정한다. 하나는 선택적 요소를 생략하고 다른 하나는 선택적 요소를 포함한다. 이는 다음을 의미한다.
  - [VariableDeclaration](https://tc39.es/ecma262/#prod-grammar-notation-VariableDeclaration) :
    - [BindingIdentifier](https://tc39.es/ecma262/#prod-BindingIdentifier) [Initializer](https://tc39.es/ecma262/#prod-Initializer)opt
      *변수선언
      *바인딩 식별자 이니셜라이저opt
- 다음은 편리한 약어
  - [VariableDeclaration](https://tc39.es/ecma262/#prod-grammar-notation-VariableDeclaration) :
    - [BindingIdentifier](https://tc39.es/ecma262/#prod-BindingIdentifier)
    - [BindingIdentifier](https://tc39.es/ecma262/#prod-BindingIdentifier) [Initializer](https://tc39.es/ecma262/#prod-Initializer)
- 그리고
  - [ForStatement](https://tc39.es/ecma262/#prod-grammar-notation-ForStatement) :
    - for ([LexicalDeclaration](https://tc39.es/ecma262/#prod-LexicalDeclaration) [Expression](https://tc39.es/ecma262/#prod-Expression) opt ; [Expression](https://tc39.es/ecma262/#prod-Expression) opt)
    - [Statement](https://tc39.es/ecma262/#prod-Statement)
    * for문
    * 어휘선언 opt ; 표현옵션 opt
    * 문(성명서, 기재, 이야기)
- 편리한 약어
  - [ForStatement](https://tc39.es/ecma262/#prod-grammar-notation-ForStatement) :
    - for ([LexicalDeclaration](https://tc39.es/ecma262/#prod-LexicalDeclaration) ;[Expression](https://tc39.es/ecma262/#prod-Expression) opt ) [Statement](https://tc39.es/ecma262/#prod-Statement)
    - for ([LexicalDeclaration](https://tc39.es/ecma262/#prod-LexicalDeclaration) [Expression](https://tc39.es/ecma262/#prod-Expression) ; [Expression](https://tc39.es/ecma262/#prod-Expression) opt ) [Statement](https://tc39.es/ecma262/#prod-Statement)
- 약어로하면
  - [ForStatement](https://tc39.es/ecma262/#prod-grammar-notation-ForStatement) :
    - for ([LexicalDeclaration](https://tc39.es/ecma262/#prod-LexicalDeclaration) ) [Statement](https://tc39.es/ecma262/#prod-Statement)
    - for ([LexicalDeclaration](https://tc39.es/ecma262/#prod-LexicalDeclaration) ; [Expression](https://tc39.es/ecma262/#prod-Expression)) [Statement](https://tc39.es/ecma262/#prod-Statement)
    - for ([LexicalDeclaration](https://tc39.es/ecma262/#prod-LexicalDeclaration) [Expression](https://tc39.es/ecma262/#prod-Expression) ; ) [Statement](https://tc39.es/ecma262/#prod-Statement)
    - for ([LexicalDeclaration](https://tc39.es/ecma262/#prod-LexicalDeclaration) [Expression](https://tc39.es/ecma262/#prod-Expression) ; [Expression](https://tc39.es/ecma262/#prod-Expression) ) [Statement](https://tc39.es/ecma262/#prod-Statement)
- 따라서 이 예에서 비터미널 [ForStatement](https://tc39.es/ecma262/#prod-grammar-notation-ForStatement)에는 실제로 4개의 대체 오른쪽이 있다.

### 5.1.5.4 문법적 매개변수 (Grammatical Parameters)

- 프로덕션은 "[parameters]" 형식의 아래 첨자 주석으로 매개변수화될 수 있으며, 이는 프로덕션에 의해 정의된 비터미널 기호에 대한 접미사로 나타날 수 있다. "parameters"는 단일 이름이거나 쉼표로 구분된 이름 목록일 수 있다. 매개변수화된 프로덕션은 매개변수화된 비터미널 기호에 추가된 밑줄이 앞에 오는 매개변수 이름의 모든 조합을 정의하는 프로덕션 세트의 약칭이다. 이는 다음을 의미한다.
  - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList) [Return] :
    - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
    - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
    * 문 목록 (반환)
    * 반환문
    * 표현문
- 다음의 편리한 약어이다.
  - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList):
    - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
    - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
  - [StatementList_Return](https://tc39.es/ecma262/#prod-grammar-notation-StatementList_Return):
    - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
    - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
- 그리고
  - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList) [Return, In] :
    - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
    - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
- 다음은 약어다.
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
    - [StatementList_Return](https://tc39.es/ecma262/#prod-grammar-notation-StatementList_Return):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
    - [StatementList_In](https://tc39.es/ecma262/#prod-grammar-notation-StatementList_In):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
    - [StatementList_Return_In](https://tc39.es/ecma262/#prod-grammar-notation-StatementList_Return_In):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
- 여러 매개변수는 조합 수의 생산물을 생성하며, 전체 문법에서 반드시 모든 것이 참조되는 것은 아니다. 프로덕션의 오른쪽에 있는 비터미널에 대한 참조도 매개변수화할 수 있다. 예를 들어:
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)[+In]
- 다음과 같다
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - ExpressionStatement_In
- 그리고
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)[~In]
- 다음과 같다
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
- 비터미널 참조는 매개변수 목록과 "opt" 접미사를 모두 가질 수 있다. 예를 들어:
    - [VariableDeclaration](https://tc39.es/ecma262/#prod-grammar-notation-VariableDeclaration):
        - [BindingIdentifier](https://tc39.es/ecma262/#prod-BindingIdentifier)
        - [Initializer](https://tc39.es/ecma262/#prod-Initializer)[+In]opt
        *변수선언
- 다음은 약어다.
    - [VariableDeclaration](https://tc39.es/ecma262/#prod-grammar-notation-VariableDeclaration):
        - [BindingIdentifier](https://tc39.es/ecma262/#prod-BindingIdentifier)
        - [BindingIdentifier](https://tc39.es/ecma262/#prod-BindingIdentifier) Initializer_In
- 매개변수 이름에 "?" 접두사 추가 오른쪽 비터미널 참조에서 해당 매개변수 값은 현재 프로덕션의 왼쪽 기호에 대한 참조에서 매개변수 이름의 발생에 따라 달라진다. 예를 들어:
    - [VariableDeclaration](https://tc39.es/ecma262/#prod-grammar-notation-VariableDeclaration)[In] :
        - [BindingIdentifier](https://tc39.es/ecma262/#prod-BindingIdentifier) [Initializer](https://tc39.es/ecma262/#prod-Initializer)[?In]
- 오른쪽 대안에 "[+parameter]"가 접두사로 붙는 경우 해당 대안은 명명된 매개변수가 프로덕션의 비터미널 기호를 참조하는 데 사용된 경우에만 사용할 수 있다. 오른쪽 대안이 "[~parameter]" 접두사로 붙는 경우 해당 대안은 명명된 매개변수가 프로덕션의 비터미널 기호를 참조하는 데 사용되지 않은 경우에만 사용할 수 있다. 이는 다음을 의미한다.
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList) [Return] :
        - [+Return] [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
             *표현문
- 축약하면
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList):
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
    - [StatementList_Return](https://tc39.es/ecma262/#prod-grammar-notation-StatementList_Return):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
- 그리고
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList) [Return] :
        - [~Return] [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
- 축약하면
    - [StatementList](https://tc39.es/ecma262/#prod-grammar-notation-StatementList):
        - [ReturnStatement](https://tc39.es/ecma262/#prod-ReturnStatement)
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)
    - [StatementList_Return](https://tc39.es/ecma262/#prod-grammar-notation-StatementList_Return):
        - [ExpressionStatement](https://tc39.es/ecma262/#prod-ExpressionStatement)

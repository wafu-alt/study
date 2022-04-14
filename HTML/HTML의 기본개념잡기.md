## HTML의 기본개념잡기

Hyper Text Markup Language 마크업 언어

마크업 - 목업, 레이아웃으로 나누는 것 (header, main) 

저장되는 형식 : 원하는이름`.html`

### HTML기본 구조

```jsx
<!DOCTYPE html>
<html>
  <head>
		문서의 보이지않는 내용이 들어감
  </head>

  <body>
    내용
  </body>
</html>
```

`<!DOCTYPE html>`  HTML의 문서 선언 : 없어도 에러 없음

### 태그

```jsx
<h1>Hello, World Wide Web</h1>
<여는태그> 컨텐츠 </닫는태그>
<img src="이미지경로" alt="이미지 못 불러왔을 때의 설명"/>
```

`Hello, World Wide Web` 컨텐츠(contents) : 태그 사이 내용물

`<h1>` 태그(tag) or 요소(element)(꼭 닫아주기`</h1>`)  , 대소문자 구분하지 않음

`<img />` 단일태그는 열고 바로 닫을 수 있고 단일 태그 아니더라도 태그사이에 컨텐츠가 없다면 바로 닫을 수 있다.(img, meta, br, hr , link, input 등)(바로 닫기 : <div /> - 공간 만들기 용)

```jsx
<div *style*="color: red">Web</div>
<태그 속성 = "속성값"> 
```

*`style`* 속성(attribute)명

`color: red` 속성값(arguments)

### HTML 일반적인 구조

```jsx
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document Title</title>
  </head>
  <body>
		주요 내용
	</body>
</html>
```

`<html lang="en">`*lang*="en"은 스크린 리더가 인식함 , 시각장애인을 위한 보조 공학, 스크린 리더가 언어를 인식하여 자동으로 음성을 변환하거나 언어에 적합한 발음을 제공

`<meta charset="UTF-8" />`메타는 내장되어 있는 정보

인코딩언어. 언어 세팅(서버관련) 주로 utf-8(글로벌사이트), euc-kr(국내사이트) -서버설정과 맞춰야함

`<meta http-equiv="X-UA-Compatible" content="IE=edge" />` 브라우저 설정 , IE = edge가 같은 브라우저임

`<meta name="viewport" content="width=device-width, initial-scale=1.0" />` 기기에 대한 화면 최적화. `@media` 미디어쿼리와 관련 됨 

`<title>Document Title</title>` html의 페이지(page) 혹은 문서(document) 제목

## HTML으로 구조 잡기
![Untitled](https://user-images.githubusercontent.com/83447120/163348028-cd4a6f59-b6cc-4ca8-bd71-6b99734fe160.png)
![Untitled 1](https://user-images.githubusercontent.com/83447120/163348033-d1910017-41b7-4d73-a3d7-0341822d18dc.png)

`header` (header) 웹사이트의 머리글을 의미

 `nav` (navigation) 주로 메뉴버튼을 의미

`aside` 옆에 따라다니면서 있는 메뉴바

`mian` body내의 주요 컨텐츠를 의미

`section` `mian`내의 영역 분할

`article` 사이트 내 독립적인 구분을 의미(ex.블로그글, 뉴스기사) 

- h1이 항상 필수

`footer` 웹사이트의 맨 하단을 의미, 주로 주소,연락처,하단로고,저작권,sns,개인정보처리방침,이용약관,이메일무단수집거부 등의 정보를 적음

## 태그의 종류

### 태그 참조

w3school : [https://www.w3schools.com/tags/tag_a.asp](https://www.w3schools.com/tags/tag_a.asp)

MDN : [https://developer.mozilla.org/ko/docs/Web/HTML/Element/a](https://developer.mozilla.org/ko/docs/Web/HTML/Element/a)

### inline과 block 차이

웹 개발자도구에서 아래 아이콘을 클릭하고 각 해당하는 영역에 가져다 되면 각 태그의 영역을 알 수 있다
![Untitled 2](https://user-images.githubusercontent.com/83447120/163348061-fc64d88e-20f1-445d-9d03-bfcab755a9d9.png)
![Untitled 3](https://user-images.githubusercontent.com/83447120/163348066-a4471135-4218-4cfb-97a5-14b4e3c1b335.png)


     block : 한줄 차지 `div` 태그가 영역나눌때 사용

inline : 포함된 내용만(컨텐츠) `span` 태그가 영역 나눌때 사용

### 각 종류별 태그

주석

- `<!-- 내용 -->`

글자 관련 태그

- `공백spacebar`은 한칸만 인식하고 그외에는 인식하지 못한다. 그래서 엔티티코드(Entity Code)를 사용하는데  `&nbsp;` 공백한칸 의미. spacebar와 같이 쓰면 공백1칸만 인정됨
- `<br>` 줄바꿈 하고싶을때
- `<p></p>` 단락으로 묶고싶을때 출력 상태로 보면  `<br>`과 같아 보이는데 한 단락으로 묶냐 안 묶냐 차이
- `<em>`글자 기울임`</em>` = `<i></i>` 같은 효과 내지만 강조효과가 다른데 강조라는것은 시각장애인이  "스크린리더"로 읽을때 강조일때는 소리가 더 크게 남 이러한 것을→ 시맨틱Semantic태그 = 의미 담은 태그
- `<strong>`글자 강조`</strong>` (시맨틱태그)= `<b></b>`
- `<h1>`제목`</h1>` h1~h6까지 있음 글자 크기 굵기가 다르고 위아래 자동 줄바꿈 됨
문서당 h1은 한개만 씀. 두개 이상 되면 seo에 검색이 잘 안됨

목록 관련 태그

- Ordered list 숫자로 표현 (순서형)

```jsx
<ol type="(A,a,i 이런것들 있음 )"> 
	<li>내용 </li>
	<li>내용 </li>
	<li>내용 </li>
	<li>내용 </li>
</ol> , ol은 혼자서 못씀. li와 같이 씀 그래서 ol는 부모, li는 자식 태그임
```

- Unordered List (bulleted list. ) 블릿기호 (비순서형)

```jsx
<ul type="(circle, square 이런것들 있음)"> 
	<li>내용</li>
	<li>내용</li>
	<li>내용</li>
	<li>내용</li>
</ul>
```

- Description list (정의형 목록)

```jsx
<dl> 
	<dt>제목</dt>
	<dd>설명</dd>
	<dt>제목</dt>
	<dd>설명</dd>
	<dd>설명</dd>
</dl>
```

표 관련 태그

- 열(column) , 행(row) , 칸(cell)

```jsx
 <table border="1"(선1픽셀 줌, 기본값0) cellspacing="0"(칸외곽 표의 외각 공간 없애줌. 2줄에서 1줄로 바꿈) 
  cellpadding="10"(칸안에서 10픽셀만큼 공간주는것) align="center"(화면 비율로 표를 중앙에 둠) 
  width="50"(칸 가로크기 50픽셀 줌 50%하면 화면크기 비율로 50%만큼 가로크기) >
    <tr> 1행을 늘려줌 table row
      <td>내용</td> <th>표안에서 제목에 해당</th> 1행 1열과 2열 생성
    </tr>
    <tr>
      <th colspan="2"(옆 두칸만큼 길이 늘어남)>제목</th> <td rowspan="2"(아래 두칸만큼길이 늘어남)>내용</td>
    </tr>
  </table>

표제목 <table> <caption>제목</caption> </table>

<table border="1" cellspacing="0" cellpadding="10" align="center" width="50">
  <tr>
    <th>이름</th> <th>생년월일</th> <th rowspan="2">기타사항</th> <th>참여여부</th>
  </tr>
	<tr>
		<td></td> 		<td></td>		<td></td>		<td></td>
	</tr>
  <tr>
    <td>내용</td> <td>내용</td> <td colspan="2">내용</td> <td>내용</td>
  </tr>
</table>
```

기타 태그

- 이미지 태그

```jsx
<img src="logo.jpg"  alt="로고">
img가 기본이고 src 속성이 붙고 속성값에 경로가 들어간다
<img src="이미지 경로" alt="이미지 설명"/>
alt경우는 시각장애인한테 alt 속성값을 읽어준다 또는 이미지 불러오기 실패했을 때 어떤 이미지인지 설명해준다.
```

경로 : 

- 절대 경로(주소줄 경로)
C:\Program Files\Google\images\logo.jpg
- 상대 경로
내가 작업하고 있는 html파일 기준으로 이미지 파일을 찾음
같은 폴더 위치 : logo.jpg
하위 폴더 위치 : images/logo.jpg
상위 폴더 위치 : ../logo.jpg
- 하이퍼링크 태그

```jsx
a는 anchor의 약자다
<a href="경로와 파일명" target="(_self, _blank)">
target속성값에는 _self와 _blank가 있고 보는 창에서 열것인지 새 창에서 열것인지 선택할 수 있다.

<a href="home.html">홈</a>
<a href="#">홈</a>  : 빈 값을 넣고 싶을때
```

- 구분선 태그 `<hr>`(horizontal rule)
- 동영상,맵 공유 태그 `<iframe>`

```jsx
유튜브 영상 
<iframe width="560" height="315" src="https://www.youtube.com/embed/v-vo_G7FZlk" title="YouTube video player"

frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"

allowfullscreen></iframe>
구글 맵
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3261.096182419837!2d129.0730083155213!3d35.17915521494972!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x356893547acb7d77%3A0x47b8fdf24219a59a!2z67aA7IKw6rSR7Jet7Iuc7LKt!5e0!3m2!1sko!2skr!4v1622164709895!5m2!1sko!2skr"

width="100%" height="700" style="border:0;" allowfullscreen="" loading="lazy"></iframe>

기본 형식
<iframe src="경로"></iframe>
```

- 오디오,비디오 태그 `<audio>` , `<video>`

```jsx
<audio src="data/music.mp3" controls="controls"></audio>
확장자 : mp3, ogg 등등

기본 형식
<audio src="경로" controls="controls"></audio>
controls="controls(생략되도 상관없음)" 컨트롤 박스는 브라우저마다 지원하는 모양이 다르다

<video src="data/Seoul.mp4" controls="controls" poster="data/seoul_poster.jpg"></video>
확장자 : mp4, wmv, avi 등등

기본 형식
<video src="경로" controls="controls"></video>
컨트롤 박스 없으면 이미지처럼 보여진다. 
재생 전 이미지 설정 속성 poster="경로"
브라우저마다 지원 안하는 형식 있으며, 그 형식을 다 적어줘야한다.
-> 유튜브 영상을 끌어다가 연결하는 것이 사이트에 올리는 것보다 빠르다
```

- 공간분할

```jsx
<span></span> p태그와 비슷하지만 의미없는 태그, 문자열 묶는 느낌
<div></div> display : block으로 공간 분할
```

- 폼 태그 `<form>`  + `<input>` + `<textarea>` + `<select>`

```jsx
<form name="join" method="POST" action="join.html">
    <fieldset>
    <!-- 그룹할 수 있음 -->
      <legend>input 관련 요소</legend> <!-- 그룹명 지어줄수있음. -->
        1. 텍스트 input <br>
        <input type="text" size="50" maxlength="5"> <br>
        <!-- size=영문 50자 , maxlength최대글자 수 제한 -->

        2. 비밀번호 input <br> <label for="pw">비밀번호</label>
        <!-- label은 시각장애인이 읽을 수 있게 해주기위해 만듦 -->
        <input type="password" id="pw"> <br>
        <!-- 글자 모양이 비공개가 된다. -->

        3. 파일 선택 input <br>
        <input type="file"> <br>

        4. 이미지 (손모양으로 변함) input <br>
        <input type="image" src="images/search.gif" alt="검색"> <br>

        5. 선택모양 라디오 input <br>
        <input type="radio" name="gender" id="m">남자
        <input type="radio" name="gender" id="w">여자<br>
        <!-- radio 속성쓸 때는 name과 id속성을 기입해야함
            name값은 동일하고 id값은 다르게 입력해야한다.-->

        6. 다중선택가능하게하는 체크박스 input <br>
        <input type="checkbox">댄스
        <!-- name, id가 있어야하지만 일단 생략 -->
        <input type="checkbox">독서
        <input type="checkbox">잠
        <input type="checkbox">뛰기 <br>

        7. 제출할 수 있는 input <br>
        <input type="submit" value="제출. 확인"> <br><!-- 브라우저마다 모습이 다를 수 있음 ,값으로 이름 바꿀 수 도 있음-->

        8. 취소 버튼 input <br>
        <input type="reset" value="초기화. 취소"> <br>

        9. 범용버튼 input <br>
        <input type="button" value="빈칸.우편번호"> <br>

        10. 브라우저에 표시 되지않음 input <br>
        <input type="hidden"> <br>
        <!-- 회원가입할 경우 그 날짜를 전송함, 알고보면 여러가지 전송할수도 -->
	</fieldset>

	<fieldset>
        11. 텍스트 구역 textarea <br>
        <textarea cols="30" rows="10">기본내용 저장할 수 있음</textarea> <br>
        <!-- cols열 30자, rows행 10자 기본형식으로 잡아줌-->

        12. select <br>
        <select name="" id="">
            <option value="">010</option>
            <option value="">011</option>
            <option value="">016</option>
            <option value="">017</option>
            <option value="">018</option>
        </select> <!-- 아래로 선택할 수 있게 됨 -->
  </fieldset> 

</form>
```

html구조와 종합 사용

```jsx
<head>
    <meta charset="utf-8">
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>제목</title>
		
</head>

<!-- 위의 내용 종합 -->
<body>
	<header>
		<h1><a href="#">문서 제목 및 로고<img src="로고경로" alt="대표로고"></a></h1>
      <nav>
        <ul>
          <li><a href="#">메뉴1</a></li>
          <li><a href="#">메뉴2</a></li>
          <li><a href="#">메뉴3</a></li>
        </ul>
      </nav>
	</header>

	<main>
		<article>
      <h1></h1>
      <p></p>
      <ul>
        <li></li>
        <li></li>
        <li></li>
      </ul>
    </article>		
	
		<section>
	    <br> <p>내용</p> <strong>내용</strong> <em>내용</em>
	    <h2~6>제목</h2~6> 
	    <!-- 목록 -->
	    <ol>
	        <li>내용</li>
	    </ol>
	    <ul>
	        <li>내용</li>
	    </ul>
	    <dl>
	        <dt>제목</dt>
	        <dd>내용</dd>
	    </dl>
		
	    <!-- 표 -->
	    <table border="1" cellspacing="0" cellpadding="5" width="">
	        <caption>제목</caption>
	        <tr>
	            <th colspan="2" rowspan="2">제목</th> <td>내용</td>
	        </tr>
	    </table>
	    <!-- 이미지 -->
	    <img src="경로와 파일명.확장자" alt="이미지">
	    <!-- 하이퍼링크 -->
	    <a href="경로와 파일명" target="_self,_blank" title="툴팁같은 대체 텍스트">내용</a>
	    <!-- 아이프레인(구글지도,유튜브영상) -->
	    <iframe src="" width="" height=""></iframe> 
	    <!-- 비디오 mp4 -->
	    <video src="" controls="controls" muted autoplay></video>
	     <!-- mutede 자동 음소거/ autoplay 자동재생-->
	    <!-- 오비오 mp3 -->
	    <audio src=""></audio>
	    <!-- 폼태그 -->
	    <form action="">
	        <fieldset>
	            <legend>제목</legend>
	            <input type="text">
	            <input type="password">
	            <input type="file">
	            <input type="image">
	            <input type="radio">
	            <input type="checkbox">
	            <input type="submit">
	            <input type="reset">
	            <input type="button">
	            <input type="hidden">
	            <textarea name="" id="" cols="30" rows="10"></textarea>
	            <select name="" id="">
	                <option value=""></option>
	            </select>
	        </fieldset>
	    </form>
		</section>
	</main>
	<footer>
    <ul class="footer_link">
        <li><a href="#">서비스이용약관</a></li>
        <li><a href="#">개인정보처리방침</a></li>
        <li><a href="#">이메일집단수집거부</a></li>
        <li><a href="#">오시는길</a></li>
    </ul>

    <address>
        ( 16229 ) 경기도 수원시 영통구 광료로 107 경기도경제과학진흥원
    </address>
    <p class="copy">Copyright &copy; 2018 GBSA.or.kr All Rights Reserved.</p>
  </footer>
</body>
```

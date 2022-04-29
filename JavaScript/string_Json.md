## String, JSON
출처 : 엘리스 SW엔지니어 트랙
- 문자열 원시 타입의 래퍼 객체.
- 문자열을 조작하기 위한 여러 메서드를 포함
- JSON - JSON객체와 관련된 매서드를 담은 객체

```jsx
function toUserList(users) {
	return users
						.filter((user) => !user.incluedes("Admin"))
						.map((user) => user.tirm().toUpperCase())
						.map((user) => `<lis>${user}</li>`)
						.join("");
}

console.log(toUserList(["Daniel", "Tom", "Johnny", "Admin"]));
// <li>DIANIEL</li> <li>TOM</li> <li>JOHNNY</li>

/*
.tirm() 빈공간 제거
.toUpperCase() 소문자 대문자로
.incluedes() 문자열 검색에 성공시 true, 실패시 false리턴
*/

"Daniel, Kim, SW".split(",")//["Daniel", "Kim", "SW"]
"Daniel, Kim, SW".replace(",", " ")// "Daniel Kim SW"
"Daniel, Kim, SW".includes("Kim")// true
"Daniel, Kim, SW    ".trim() // "Daniel,Kim,SW"
"Daniel, Kim, SW".indexOf("kim") // 7
/*
.split() 주어진 문자열에 따라 타겟 문자열을 나눈다
.replace() 주어진 문자열을 검색하여 타겟 문자열로 변환한다
.indexOf() 특정 문자열을 검색하여 시작점의 인덱스를 반환한다. 없을 -1을 리턴
*/

```

```jsx
JSON.stringify({ name: "Daniel", age: 12});
//'{"name": "Daniel", "age": 12}'
//주어진 객체를 JSON문자열로 만든다

JSON.parse('{"name": "Daniel", "age": 12}');
// {name: "Daniel", age: 12}
//주어진 JSON문자열을 자바스크립트에 맞는 결과객체로 만든다
```

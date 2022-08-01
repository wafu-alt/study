출처 : 엘리스 sw 트랙
## **Interface**

### **1. Interface란?**

인터페이스(Interface)란 코드 내 계약(약속, 규칙)을 정의하는 강력한 방법입니다. 인터페이스는 일반적으로 변수, 함수, 클래스의 타입을 체크하기 위해 사용됩니다. 예를 들면 아래 **`elice`** 변수는 **`Person`** 인터페이스의 계약을 준수해야만 합니다.

```
interface Person {
  name: string,
  age: number
}

let elice: Person = {name: "rabbit", age: 13};

```

앞서 살펴보았던 타입을 정의하는 type alias에 대해 기억하시나요?

```
type Human = {
  name: string;
  age: number;
};

```

type alias는 인터페이스와 비슷한 역할을 하지만, type alias는 확장(**`extends`**)가 불가능하고 인터페이스는 확장이 가능합니다. 따라서 웬만하면 인터페이스를 사용하는 것이 좋습니다. 인터페이스의 확장에 대해서는 뒤에서 학습할 예정입니다.

인터페이스는 객체나 함수의 스펙, 배열의 접근 방식, 클래스 같은 범주에 대해 계약을 정의할 수 있습니다. 예를 들어 아래와 같은 인터페이스가 있다고 가정할 때 각각의 인터페이스 사용 예시를 살펴보세요.

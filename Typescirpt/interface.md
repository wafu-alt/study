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
```
interface Person {
    name: string
}

```
- 변수
    
    ```
    let elice: Person = {name: "rabbit"};
    
    ```
    
- 함수
    
    ```
    function greeting(person: Person): void {
        console.log(`Hello ${person.name}`);
    }
    
    ```
    
- 클래스
    
    ```
    class Member implements Person {
        constructor (
            public name: string
        ) { }
    }
    
    ```
    
- 배열의 경우 아래와 같이 인터페이스를 이용할 수 있습니다.
    
    ```
    interface Person {
        [index: number]: string;
    }
    let people: Person = ["rabbit", "cheshire", "queen"];
    
    ```
    

> 추상 클래스 vs 인터페이스추상 클래스는 일반 클래스와 달리 추상 메소드가 포함된 클래스로 일반 메소드를 포함할 수 있습니다. 반면 인터페이스는 모든 메소드가 추상 메소드여야 하는 차이가 있습니다.추상 클래스는 상속을 통해 추상 메소드의 구현을 강제하여 자식 클래스에서 일부 동작을 구현하도록 만든 것입니다. 인터페이스는 모든 구현에 대한 계약을 작성해둔 것입니다. 추상 클래스는 프로그램의 전체 구조를 잡기 위해 사용하고, 인터페이스는 기본적인 설계도로써 개발 협업에서 사용하기 용이합니다.
>
### **2. Properties**

타입스크립트의 컴파일러는 객체 프로퍼티의 두 가지 요소를 검사하는데 바로 프로퍼티의 타입과 필수 요소 유무입니다.

필수 요소 유무를 컨트롤하기 위해서 Optional 프로퍼티인 **`?`**을 이용할 수 있습니다. 프로퍼티 선언 시 이름의 끝에 **`?`**를 붙여서 표시합니다. **`?`**를 이용해 인터페이스에 속하지 않는 프로퍼티의 사용은 방지할 수 있습니다. 이는 객체 안의 몇 개의 프로퍼티만 채워서 사용하는 함수에 유용합니다. (이를 "option bags" 패턴이라고 부릅니다.)

```
interface SquareConfig {
  color?: string
  width?: number
}

```

또한 객체가 처음 생성될 때 값 설정이 가능하고, 이후 수정이 불가능하도록 설정하는 **`readonly`** 프로퍼티도 있습니다. 앞서 클래스 속성의 **`readonly`**와 동일합니다. 마찬가지로 역할도 **`const`**와 유사하며, 사용되는 위치가 다릅니다.

```
interface Point {
  readonly x: number
  readonly y: number
}

```
### **3. interface types**

앞서 살펴보았듯이 타입스크립트에서 인터페이스는 함수와 클래스에서 사용이 가능합니다.

- 함수: 인터페이스를 이용해 함수의 타입, 인자의 타입, 반환 값의 타입을 정의할 수 있습니다. 위에서 보았던 예시는 인자의 타입을 **`Person`**으로 정의하고 있습니다.
    
    ```
    function greeting(person: Person): void {
        ...
    }
    
    ```
    
- 클래스 : 클래스가 특정 계약(통신 프로토콜)을 충족하도록 명시적으로 강제합니다. 선언한 인터페이스를 클래스 뒤에 **`implements`**하여 사용하며, 클래스는 인터페이스에 명시된 메소드를 반드시 구현해야 합니다. 위에서 보았던 예시는 **`Member`** 클래스가 **`Person`** 인터페이스를 **`implements`**하고 있는 것이며, 만약 **`Person`** 인터페이스에 추상 메소드가 있었다면 **`Member`** 클래스에서 구현해야 합니다.
    
    ```
    class Member implements Person {
        ...
    }
    
    ```
    
- 인터페이스 확장 : 클래스와 마찬가지로 인터페이스도 인터페이스 간의 확장이 가능합니다. 확장을 위해서는 **`extends`** 키워드를 사용합니다. **`Dog`** 인터페이스에서 **`Animal`** 인터페이스를 확장하고 있습니다.
    
    ```
    interface Animal {
        makeSound(): void
    }
    interface Dog extends Animal {
        speed: number
    }
    
    ```

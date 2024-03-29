출처 : 엘리스 sw 트랙

### **1. Generic이란?**

앞서 유틸리티 타입을 다룰 때 잠깐 살펴보았던 제네릭을 자세히 다뤄봅시다. 제네릭(Generic)이란 어떤 함수나 클래스가 사용할 타입을 생성 단계가 아닌 사용 단계에서 정의하는 프로그래밍 기법입니다. 즉, 타입을 명시할 때 선언 시점이 아닌 생성 시점에 명시하여 하나의 타입으로만 사용하지 않고 다양한 타입을 사용할 수 있습니다. 일반적인 정적 타입 언어는 함수나 클래스를 정의할 때 타입을 선언해야 하지만, 제네릭을 이용해 코드가 수행될 때 타입이 명시되도록 하는 것입니다.

예를 들어 문자를 그대로 반환하는 함수에 아래와 같이 제네릭을 적용할 수 있습니다.

```
function echo<T>(text: T): T {
  return text;
}
console.log(echo<string>("hi"));
console.log(echo<number>(10));
console.log(echo<boolean>(true));

```

여기서 식별자 T는 Type의 약자로, 추가될 때마다 U, V, … 순으로 추가하는 것이 일반적입니다. 하지만 어떤 식별자도 상관이 없어, 필드 이름의 첫 글자를 사용하기도 합니다.
   
**제네릭을 사용하는 이유**

- 제네릭을 사용하면 재사용성이 높은 함수나 클래스를 생성할 수 있습니다. 위의 **`echo`** 함수에서 제네릭을 사용하지 못했다면 타입별로 하나의 함수를 만들어야 할 것입니다. 제네릭을 사용하면 하나만 선언해도 여러 타입에서 동작이 가능합니다.
- 제네릭을 사용하면 중복되는 코드가 줄어들고 반환되는 타입을 명시하기 때문에 코드의 가독성이 좋아집니다.
- 만약 제네릭이 없다면 아래와 같이 **`any`** 타입을 이용해야 합니다.
    
    ```
    function echo2(text: any): any {
        return text;
    }
    
    ```
    
    - 하지만 **`any`** 타입은 컴파일 시 타입을 체크하지 않기 때문에 입력된 타입에 대한 메소드의 힌트를 사용할 수 없고, 컴파일 시 발견되는 에러를 발견할 수 없게됩니다.
 ### **2. Generic으로 함수와 클래스 만들기**

- **제네릭을 이용한 함수 생성**앞서 살펴보았듯 꺽쇠(**`<>`**)와 식별자를 입력해 제네릭을 만들 수 있습니다. 다른 예시로 배열을 입력 받아 정렬 후 반환하는 제네릭을 만든다면, 아래와 같이 만들고 사용할 수 있습니다.

```
function sort<T>(items: T[]): T[] {
  return items.sort();
}
const nums: number[] = [1, 2, 3, 4];
const chars: string[] = ["a", "b", "c", "d"];
sort<number>(nums);
sort<string>(chars);

```
- **제네릭을 사용한 클래스 생성**클래스에서는 제네릭을 어떻게 사용하는지 간단한 큐를 구현해보며 살펴보겠습니다. 마찬가지로 클래스 옆에 **`<T>`**를 작성하며, 필드나 메소드에 해당 식별자를 타입으로 명시해주면 됩니다.**`pop()`** 메소드에 있는 **`|`**는 유니온 타입을 사용하기 위한 연산자입니다. 유니온 타입은 명시된 타입 중 하나가 올 수 있다는 것을 나타냅니다. 여기서는 T 타입이 반환되거나, 배열이 빈 경우 undefined가 반환되기 때문에 두 가지를 명시하였습니다.

```
class Queue<T> {

  protected data: Array<T> = [];

  push(item: T) {
    this.data.push(item);
  }

  pop(): T | undefined {
    return this.data.shift();
  }
}

```
### **3. Union type**

유니온(Union) 타입은 어떤 타입이 올 지 경우의 수를 고려하여 타입을 명시하는 것으로 **`|`**를 이용해 선언합니다. 제네릭과 마찬가지로 유니온 타입을 이용하여 여러 가지 타입을 다룰 수 있습니다.

하지만 유니온 타입의 리턴 값은 사용된 하나의 타입이 아니라 선언된 전체 유니온 타입으로 지정이 되며, 유니온 타입에서 선언한 타입들의 공통된 메소드만 사용할 수 있습니다. 예를 들어, **`printMessage`**의 경우, string과 number를 포함한 유니온 타입이기 때문에 string에서만 사용 가능한 **`length`** 메소드를 사용할 수 없습니다.

```
const printMessage = (message: string | number) => {
  return message;
}
const message1 = printMessage(1234);
const message2 = printMessage("hello world!");

message2.length;

```
### **4. 제약조건 (Constraints / keyof)**

제네릭에서 원하지 않는 속성에 접근하는 것을 막기 위해 **`extends`** 키워드를 이용해 제약조건(Constraints)을 사용할 수 있습니다. 아래의 경우 **`printMessage`**의 제네릭 타입으로 string, number 외의 타입이 오는 경우 에러가 발생하게 됩니다.

```
const printMessage = <T extends string | number>(message: T): T => {
  return message;
}

```

**keyof`keyof`**를 이용하면 객체의 키에 제약 조건을 걸 수 있습니다. 아래의 경우 U 타입에 들어오는 값이 T 타입의 키에 포함되어 있지 않다면 에러가 발생하게 됩니다.

```
const getProperty = <T extends object, U extends keyof T>(obj: T, key: U) => {
  return obj[key]
}

```


# Type(자료형) 고급

* ### TypeAlias : Swift에서 제공하는 기본 타입, 사용자가 정의한 타입 등 이미 존재하는 타입에 대하여 임의로 다른 이름을 지정할 수 있는 것이다.
    > 별칭을 사용하여 코드를 쉽고 명확하게 작성할 수 있다

    ```Swift
    typealias Str = String
    typealias Char = Character

    let hello: Str = "Hello"
    let world: Str = "World"
    let exclamation: Char = "!"

    "\(hello) \(world)\(exclamation)" // Hello World!
    ```

* ### Tuple : ```지정된 데이터들의 묶음``` 이라고 표현 가능하며, 튜플에 포함될 데이터는 사용자가 마음대로 지정할 수 있다. 선언된 튜플의 항목을 추가하거나 제거할 수 없으며 크기가 고정되어 있다. 
    > 튜플 내의 값은 바꿀 수 있지만, 값의 유형은 변경할 수 없다

    ```Swift
    // typealias를 통한 튜플 선언
    typealias PersonTuple = (firstName: String, lastName: String, age: Int)

    var person: (firstName: String, lastName: String, age: Int) = ("길동", "홍", 19)

    // typealias로 선언한 튜플 사용
    var winter: PersonTuple = ("민정", "김", 23)

    // 인덱스를 통해 값에 접근
    print("이름 : \(person.0), 성 : \(person.1), 나이 : \(person.2)")

    // 미리 지정한 이름을 통해 값에 접근
    print("이름 : \(person.firstName), 성 : \(person.lastName), 나이 : \(person.age)")
    ```
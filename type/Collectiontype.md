# Collection Type(컬렉션 타입)

연속되는 값을 저장하기 위하여 Swift에서는 ```array```, ```set```, ```dictionary``` 총 3개의 Primitive Collection Type을 제공한다. 이는 가변적(mutable)이며, ```let```으로 선언한 Collection Type은 immutable이며, 크기와 내부의 값을 변경할 수 없다.

* ### Array : 순서대로 같은 타입의 값을 저장한다. 배열 내에 중복된 값이 존재할 수 있다.
    > Type Annotation 사용 시 ```Array<Type>``` 또는 축약형인 ```[Type]```로 나타낼 수 있다

    ```Swift
    // 타입 추론 사용 [Int]
    var nums = [1, 2, 3, 4, 5]
    // 타입 어노테이션 사용    
    var eng: [Character] = ["a", "b", "c", "d"]

    eng[0] // a
    eng[1] // b
    eng[2] // c

    // 요소를 추가하거나 제거하는 등의 프로퍼티를 기본적으로 제공한다
    eng.insert("e")
    eng.remove("e")

    type(of: nums) // Array<Int>.Type

    // 자료형이 혼합된 배열 선언 시
    // 반드시 타입 어노테이션으로 [Any] 명시해주어야 함
    var arr = [1, 2, "a", "b"]

    type(of: arr) // Array<Any>.Type
    ```
    > 배열을 선언하는 여러가지 방법
    ```Swift
    var arr1 = [String]()
    ```
    ```Swift
    var arr1:[String] = []
    ```

    > ```+```연산자를 사용하여 배열 간의 요소를 더할 수 있고, ```+=```를 사용하여 배열 간의 요소를 더한 후 할당할 수도 있다

* ### Set : 순서를 중요시 하지 않으며 배열 내에 중복된 값을 허용하지 않는다.
    > 데이터의 순서를 지정하지 않기 때문에 인덱싱으로 값을 찾을 수 없습니다.

    > 중복 데이터를 삽입하려 시도하면 중복으로 삽입한 항목은 무시된다

    > Type Annotation사용 시 ```Set<Type>```을 사용할 수 있으며 ```Array```와 다르게 축약형이 없다.
    ```Swift
    // set을 선언하는 두가지 방법
    let exSet1: Set = []
    let exSet2: Set = Set()

    var animal: Set<String> = ["Lion", "Tiger", "Cat"]

    // 요소를 추가하거나 제거하는 등의 프로퍼티를 기본적으로 제공한다
    animal.insert("Dog")

    animal // [Lion, Tiger, Cat, Dog]

    animal.remove("Dog")
    
    animal // [Lion, Tiger, Cat]
    ```
    > 중복된 값이 필요치 않고, 빠른 검색을 해야할 경우에 ```Set```이 적절하다

* ### Dictionary : 순서 없이 ```Key```, ```Value```쌍으로 구성되는 Collection Type이다. 인덱스로 항목을 찾아오는 것이 아닌 사용자가 직접 지정할 수 있는 ```Key```를 사용하여 찾아올 수 있다. Dictionary에서 Key는 유일해야하며, Value는 유일하지 않아도 된다
    > ```Set```과 마찬가지로 순서가 존재하지 않기 때문에 빠른 검색을 위하여 최적화 후 저장한다

    > Type Annotation 사용 시 ```Dictionary<Key, Value>``` 또는 축약형인 ```[Key:Value]```로 나타낼 수 있다 

    ```Swift
    // Dictionary를 선언하는 방법
    var emptyDictionary1: [String:Int] = [String:Int]()
    var emptyDictionary2: Dictionary<String, Int> = Dictionary<String, Int>()

    var credit = ["홍길동":5, "김태오":4]
    var position = ["홍길동":"사원", "김태오":"사장"]

    credit["홍길동"] // 5
    position["김태오"] // 사장

    // 저장되지 않은 key로 읽으려 하면 nil을 반환
    credit["박주홍"] // nil

    // nil을 반환하지 않도록 하려면
    // default를 사용한 기본값 설정
    credit["박주홍", default: "Unit"]

    // removeValue(forKey:) 프로퍼티를 사용해 Dictionary에서 값을 제거할 수 있다
    credit // ["홍길동":5, "김태오":4]
    credit.removeValue(forKey:"김태오")
    credit // ["홍길동":5]
    ```
# Enum(열거형)

연관된 항목들을 묶어서 표현할 수 있는 타입, 프로그래머가 정의한 항목 이외에서는 추가 수정이 불가하다

> 열거형의 각 항목들이 ```원시 값```이라는 형태로 실제 값을 가질 수도 있거나, ```연관 값```을 사용하여 다른 언어에서 공용체라 불리는 값의 묶음도 구현할 수 있다.

> Swift의 주요 기능인 Optional은 ```enum```으로 구현되어 있다.

```Swift
enum Status {
    case approved
    case pending
    case banned
}
// 만약에 나열할 데이터가 많다면
// 다음과 같은 방식으로 선언해도 된다
enum Animal {
    case dog, cat, lion, tiger
}

// 변수 선언 방법
var status1 = Status.approved
var status2: Status = .pending
var status3: Status = Status.banned

// 변수 값 변경 방법
status1 = .pending
```

### Enum associated values(연관 값)
Enum 타입 내의 case들이 자신을 더 자세히 설명하기 위해 연관된 값을 가질 수 있는 것을 의미한다

```Swift
enum Status {
    case approved(sequence: Int)
    case pending
    case banned(reason: String)
}
```
이와 같은 형식으로 열거형에 추가 정보를 첨부하여 세부적인 데이터를 나타낼 수 있다

```Swift
enum Reason {
    case rash
    case abnormal
    case disallowed
}

enum Status {
    case approved(sequence: Int)
    case pending
    case banned(reason: Reason)
}

var status: Status = .banned(reason: .abnormal)
```
다음과 같은 방법으로 응용도 가능하다


### Enum raw values(원시 값)
값을 열거형의 case 전체에 할당해야 하는 경우가 있다

```Swift
enum Status: Int {
    case approved
    case pending
    case banned
}

let banned = Status(rawValue: 2) // Status.banned를 가져와 할당
```

```Swift
// 하나의 case에 값 할당 시 Swift가 자동으로 나머지 생성
enum Status: Int {
    case approved // 0 자동으로 할당
    case pending = 2
    case banned // 3 자동으로 할당
}

let pending = Status(rawValue: 2) // Status.pending을 가져와 할당
```

### 항목 순회
열거형의 모든 케이스에 대해 순회하기 위해서는 열거형에서 ```CaseIterable```프로토콜 채택 후 ```allCases``` 타입 프로퍼티를 사용
```Swift
enum Status: CaseIterable {
    case approved
    case pending
    case banned
}

let allCases: [Status] = Status.allCases
```
> 원시값을 가지는 열거형이라면 원시값 다음에 쉼표 후 ```CaseIterable``` 채택

### 열거형 비교
```Comparable``` 프로토콜을 채택하여 각 case들을 비교하는 것이 가능하다. case 순서대로 값의 크기가 정해진다
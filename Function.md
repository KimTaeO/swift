# Function(함수)

독립된 기능을 수행하는 단위이다. 함수 안에는 메서드를 포함한다
함수와 메서드는 기본적으로 같으나, 상황이나 위치에 따라 다르게 부르는 것이다.
* 구조체, 클래스, 열거형 등 특정 타입에 연관되어 사용되는 함수를 메서드라 한다
* 모든 모듈에서 전역적으로 사용될 수 있는 것을 함수라고 한다.

Swift의 함수는 오버라이드와 오버라이딩을 지원한다

```func```키워드를 사용해 함수를 선언할 수 있으며, 
```Swift
func 함수이름(매개변수: 매개변수타입) -> 반환값 { }

// 매개변수에 값을 넘기지 않았을 경우에 지정될 기본값을 = 을 통해 설정할 수 있다
func 함수이름(매개변수1: 매개변수타입 = 기본값) -> 반환값 { }
```
### 전달 인자 레이블
함수를 호출할 때 매개변수 이름을 사용하는 것이 아닌 ```전달 인자 레이블```을 사용하여 매개변수를 전달할 수 있다

- 예시
    ```Swift
    func sum(first a: Int, second b: Int) -> {
        print(a + b)
    }

    sum(first: 1, second: 2) // 3
    ```
    > 전달 인자 레이블을 사용하고 싶지 않다면 언더스코어(_)를 사용하면 된다

### 가변 매개변수
매개변수의 값의 개수를 지정할 수 없을떄 가변 매개변수를 사용할 수 있다```...``` 키워드를 사용하여 가변 매개변수를 정의할 수 있다

    ```Swift
    func printStr(strings: String...) {
        for str in strings {
            str
        }
    }

    printStr(strings: "안녕", "하세요")
    printStr(strings: "안녕히", "가세요", "손님")
    ```
> 함수에서 가변 매개변수는 함수당 한개만 가질 수 있다

### 중첩 함수
Swift는 데이터 간의 중첩이 자유로워 enum 안에 enum, class 안에 class가 가능하다

```Swift
func function() {
    func nestedFunction() {

    }
}
```

### 종료되지 않는 함수
정상적으로 끝낼 수 없는 함수를 ```NonReturning Function```이라 한다. ```Never``` 키워드를 사용하여 구현할 수 있으며, 이 함수를 실행하면 프로세스는 종료된다. 주로 에러를 throw할 때 사용한다

### 반환값이 없는 함수
함수의 반환값을 사용하지 않으면 Swift 컴파일러가 경고를 띄우게 된다. 이를 해결하기 위해 @disCardableResult 어노테이션을 ```func``` 키워드 앞에 사용해 해당 함수의 반환값을 사용하지 된다고 알릴 수 있다.

### 데이터 타입으로 사용하는 함수
Swift에서 함수는 일급 객체이므로 반환 타입으로도 사용할 수 있다. 함수를 나타내는 방법은 ```(매개변수 타입) -> 반환 타입```과 같은 형식으로 나타낼 수 있다
```Swift
func plusOne(_ number: Int) -> Int {
    return number + 1
}

var intFunction: (Int) -> Int = plusOne(number: 2)
```

> 함수에서 값을 반환하지 않으려면 반환 타입을 ```Void```로 지정하거나 ```-> 반환 타입```을 생략하는 것으로 반환하지 않을 수 있다.
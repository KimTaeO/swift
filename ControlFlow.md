# Control Flow(흐름 제어)

## 조건문
* ### If
    다른 언어들과 같이 ```if```, ```if else```, ```else```문이 존재하며 조건이 true라면 ```지정한 코드를 실행한다```

    ```Swift
    let randomInt = Int.Random(in: 0...100)

    // 조건식에 소괄호를 생략해도 된다
    if randomInt > 50 {

    } else if randomInt < 50 { 

    } else {

    }   
    ```

> 다른 타입과 비교를 하려 하면 당연히 오류가 발생한다

* ### Switch
    ```If```문과 같이 소괄호를 생략하는 것이 가능하며 ```case``` 조건에 다양한 값이 들어갈 수 있다
    > 단 입력 값과 비교 값의 타입은 같아야 한다
    
    비교될 값이 한정적이지 않다면 ```default```(else와 같은 역할)를 사용해 주어야 한다

    ```Swift
    val randomInt = Int.Random(in: 0...100)

    switch randomInt {
        // break 문 없이도 해당 케이스 내의 코드 실행 시 자동으로 종료
        case 0..<50:

        case 50..<100:
        // 해당 case 내의 코드를 실행하더라도 종료하고 싶지 않다면 해당 키워드 사용
        fallthrough 

        case 100:
        break // switch문 종료

        default: // else와 같은 역할
    }

    enum Animal {
        case cat
        case dog
        case lion
        case rabbit
    }

    let cat: Animal = .cat
    switch cat {
        case .cat:
        case .dog:
        case .lion:
        case .rabbit:
        // 열거형에 새로운 case가 추가될 경우에 대한 처리를 위한 논리적 오류를 발생시키는
        @unknown case _:
    }
    ```

## 반복문
* ### For
    배열과 범위를 반복하고 루프할 떄마다 하나의 항목을 꺼내 상수에 할당한다

    ```Swift
    let langauges = ["java", "c", "kotlin", "go"]

    for lang in langauges {
        lang
    } // java c kotlin go

    let range = 1...5

    // for문이 제공하는 상수 
    for _ in range {
        "play"
    }
    ```

* ### While
    다른 언어들과 비슷하게 조건식을 만족할 때까지 순회한다. 식에 괄호를 쓰는것 제외하고는 다른 언어들과 동일하다
    > 다른 언어들에서는 ```do-while```이라고 불리는 문을 사용하려면 다음과 같이 사용해야 한다

    ```Swift
        repeat {
            print("false")
        } while false
    ```
> 모든 반복문에는 반복문을 탈출하거나 반복문을 건너뛰는 문법이 존재한다.```break``` 키워드를 사용하여 언제든 루프를 탈출할 수 있으며, ```continue```를 사용하여 현재 루프를 끝내고 다음 루프로 넘어갈 수 있다.
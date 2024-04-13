# Operator(연산자)

* ### 비교 연산자
    비교를 수행하는 여러 연산자가 존재한다. 비교 연산자는 기본적으로 ```Boolean```타입의 값을 반환한다.

|연산자|설명|
|:-:|:-:|
|A == B|A와 B가같은 값인지 비교|
|A >= B|A보다 B가 크거나 같은 값인지 비교|
|A <= B|A보다 B가 작거나 같은 값인지 비교|
|A > B|A보다 B가 큰 값인지 비교|
|A < B|A보다 B가 작은 값인지 비교|
|A != B|A와 B가 다른 값인지 비교|
|A === B|A와 B가 참조 타입일 경우 같은 인스턴스를 가리키는지 비교|
|A !== B|A와 B가 참조 타입일 경우 같은 않은 인스턴스를 가리키는지 비교|
|A ~= B|A와 B의 패턴이 매치되는치 확인|

* ### 범위 연산자

    값의 범위를 나타낼 떄 사용한다

|연산자|설명|
|:-:|:-:|
|A...B|A부터 B까지|
|A..<B|A부터 B-1까지|
|...B|B까지|
|A...|A부터 마지막까지|
|..<B|B-1까지|

* ### 오버플로 연산자
자료형의 범위를 넘어선 연산을 할 경우에 런타임 에러가 발생하는 것을 방지하기 위한 연산자이다

|연산자|설명|
|:-:|:-:|
|&+|오버플로를 대비하는 덧셈 연산|
|&-|오버플로를 대비하는 뺄셈 연산|
|&*|오버플로를 대비하는 곱셈 연산|

* ### 기타 연산자
|연산자|설명|
|:-:|:-:|
|A ?? B|A가 nil이 아니라면 A, nil이라면 B 반환|
|O!|Optional의 값을 강제로 추출|
|V?|옵셔널 값을 안전하게 추출하거나 타입(V)이 옵셔널임을 표현|
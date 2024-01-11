<h2>Comparing time complexity(시간 복잡도 비교.)</h2>

1부터 n까지의 숫자들의 합을 구하는 다음과 같은 코드를 작성했다고 가정해봅시다.<br>

```swift
func sumFromOne(upto n: Int) -> Int {
    var result = 0
    for i in 1...n {
        result += i
    }
    return result
}

sumFromOne(upto: 10000)
```

이 코드는 10000번 반복하여 50005000을 반환합니다.<br>
이것은 O(n)이며, 루프를 통해 결과를 계산하고 출력하는 데 잠시 시간이 걸릴 것 입니다.<br>
<br>
다른 버전의 코드를 작성할 수도 있습니다:<br>
```swift
func sumFromOne(upto n: Int) -> Int {
    (1...n).reduce(0, +)
}
sumFromOne(upto: 10000)
```

플레이그라운데에서 이 코드는 표준 라이브러리의 컴파일된 코드를 호출하기 때문에 더 빠르게 실행됩니다.<br>
그러나 `'reduce'`의 시간 복잡도를 찾아보면, 이것도 O(n)임을 알 수 있습니다.<br>
왜냐하면, `'+'` 메소드를 n번 호출하기 때문입니다.<br>
같은 Big O이지만, 컴파일된 코드이기 때문에 상수가 더 작습니다.<br>
<br>
마지막으로, 다음과 같이 작성할 수 있습니다:<br>
```swift
func sumFromOne(upto n: Int) -> Int {
    (n + 1) * n / 2
}
sumFromOne(upto: 10000)
```

이 버전의 함수는 프레드릭 가우스가 초등학교 때 발견한 트릭을 사용합니다.<br>
즉, 단순한 산술을 사용하여 합을 계산할 수 있습니다.<br>
이 최종 버전의 알고리즘은 O(1)이며 이길 수 없습니다.<br>
상수 시간 알고리즘은 항상 선호됩니다.<br>
이 버전을 루프에 넣어도 여전히 선형 시간이 걸립니다.<br>
이전의 O(n) 버전들은 느린 이차 시간으로부터 단 하나의 외부 루프만 떨어져 있습니다.<br>

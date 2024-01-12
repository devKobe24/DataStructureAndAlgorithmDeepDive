<h1>Space complexity(공간 복잡도)</h1>
<p>
    알고리즘의 시간 복잡도는 확장성을 예측하는 데 도움이 될 수 있지만, 유일한 척도는 아닙니다.<br>
    <strong>공간 복잡도는 알고리즘이 실행되기 위해 필요한 자원을 측정하는 것입니다.</strong><br>
    <strong>알고리즘에 대한 자원은 메모리입니다.</strong><br>
    다음 코드를 고려해보세요:<br>
</p>

```swift
func printSorted(_ array: [Int]) {
    let sorted = array.sorted()
    for element in sorted {
        print(element)
    }
}
```
<p>
    위 함수는 배열의 정렬된 복사본을 생성하고 배열을 출력합니다.<br>
    공간 복잡도를 계산하기 위해, 함수의 메모리 할당을 분석합니다.<br>
</p><br>

<p>
    <strong>'array.sorted()'</strong>가 동일한 크기의 새로운 <strong>배열을</strong> 생성하기 때문에, <strong>'printSorted'</strong> 함수의 공간 복잡도는 O(n)입니다.<br>
    이 함수는 간단하고 우아하지만, 가능한 한 적은 메모리를 할당하고 싶은 상황이 있을 수 있습니다.<br>
    <br>
    위 함수를 다음과 같이 수정할 수 있습니다:
</p>

```swift
func printSorted(_ array: [Int]) {
    // 1
    guard !array.isEmpty else { return }
    
    // 2
    var currentCount = 0
    var minValue = Int.min
    
    // 3
    for value in array {
        if value == minValue {
            print(vale)
            currentCount += 1
        }
    }
    
    while currentCount < array.count {
        
        // 4
        var currentValue = array.max()!
        
        for value in array {
            if value < currentValue && value > minValue {
                currentValue = value
            }
        }
        
        // 5
        for value in array {
            if value == currentValue {
                print(value)
                currentCount += 1
            }
        }
        
        // 6
        minValue = currentValue
    }
}
```

<p>
    이 구현은 공간 제약을 존중합니다.<br>
    전체 목표는 배열을 여러 번 반복하여 각 반복마다 다음으로 작은 값을 출력하는 것입니다.<br>
    <br>
    이 알고리즘이 수행하는 작업은 다음과 같습니다:<br>  
</p>

1. 배열이 비어 있는 경우를 확인합니다. 비어 있다면 출력할 것이 없습니다.
2. currentCount는 출력된 print 문의 수를 추적합니다. minValue는 마지막으로 출력된 값을 저장합니다.
3. 알고리즘은 minValue와 일치하는 모든 값을 출력하고, 출력된 print 문의 수에 따라 currentCount를 업데이트 합니다.
4. while 루프를 사용하여, 알고리즘은 minValue보다 큰 최소값을 찾아 currentValue에 저장합니다.
5. 알고리즘은 currentValue에 해당하는 배열 내의 모든 값을 출력하면서 currentCount를 업데이트합니다.
6. 다음 반복에서 다음 최소값을 찾기 위해 minValue를 currentValue로 설정합니다.

<p>
    위 알고리즘은 몇 개의 변수를 추적하기 위해 메모리를 할당하기 때문에 공간 복잡도는 O(1)입니다.<br>
    이는 이전 함수와 대조적으로, 원본 배열의 정렬된 표현을 생성하기 위해 전체 배열을 할당합니다.
</p>

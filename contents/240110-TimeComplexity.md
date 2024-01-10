<h1>Time complexity(시간 복잡성)</h1>

소량의 데이터에 대해서는 현대 하드웨어의 속도 덕분에 가장 비싼 알고리즘이라도 빠르게 보일 수 있습니다.<br>
그러나 데이터가 증가함에 따라, 비싼 알고리즘의 비용이 점점 더 명확해집니다.<br>
시간 복잡도는 입력 크기가 증가함에 따라 알고리즘을 실행하는 데 필요한 시간을 측정합니다.<br>
Time complexity 섹션에서는 가장 흔한 시간 복잡도를 살펴보고 이를 식별하는 방법을 배울 것 입니다.<br>

<h2>Constant time(상수 시간)</h2>

입력 크기와 상관없이 동일한 실행 시간을 가지는 알고리즘을 <strong>상수 시간 알고리즘</strong>이라고 합니다.<br>
다음을 고려해보세요:

<pre><code>
func checkFirst(names: [String]) {
    if let first = names.first {
        print(first)
    } else {
        print("no name")
    }
}
</code></pre>

이 함수의 실행 시간에는 <strong>'names'</strong> 배열의 크기가 영향을 미치지 않습니다.<br>
입력에 항목이 열 개이든 천만 개이든, 이 함수는 첫 번째 요소만 확인합니다.<br>

다음은 시간 복잡도를 시간 대 데이터 크기의 그래프로 시각화한 것입니다:
<img src="https://github.com/devKobe24/images/blob/main/2024-01-10-constant-time.png?raw=true"><br>

입력 데이터가 증가해도 알고리즘이 걸리는 시간은 변하지 않습니다.<br>

간결함을 위해, 프로그래머들은 다양한 시간 복잡도의 크기를 나타내기 위해 <strong>'빅-오 표기법'</strong>이라는 표기법을 사용합니다.<br>
상수 시간의 빅-오 표기법은 O(1)입니다.<br>

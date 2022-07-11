<ol>
<h5><a href="#zero"><li>동적 계획법(DP, Dynamic Programming)에 대해 설명해주세요.</li></a></h5>
<h5><a href="#one"><li>버블 정렬(Bubble Sort)에 대해 설명해주세요.</li></a></h5>
<h5><a href="#two"><li>선택 정렬(Selection Sort)에 대해 설명해주세요.</li></a></h5>
</ol>


<hr>
<a name="zero"><b>0. 동적 계획법(DP, Dynamic Programming)에 대해 설명해주세요.</b></a>
<hr>
<h5>동적계획법이란</h5>
<p>
주어진 문제를 풀기 위해, 문제를 여러 개의 하위 문제로 나누어 푸는 방법을 말합니다.<br>
동적 계획법에서는 어떤 부분 문제가 다른 문제들을 해결하는데 사용될 수 있어, 답을 여러 번 계산하는 대신 한 번만 계산하고 <br>
그 결과를 재활용하는 메모이제이션(Memoization)기법으로 속도를 향상시킬 수 있습니다.<br>
<h6>※ 메모이제이션 : 동일한 계산을 반복해야 할 때, 이전에 계산한 값을 재사용함으로써 동일한 계산의 반복 수행을 제거하여 프로그램 실행 속도를 빠르게 하는 기술</h6>
</p>

<h5>동적 계획법(DP, Dynamic Programming)이 갖는 2가지 조건은 무엇인가요?</h5>
<p>
<b>1. 중복되는 부분(작은) 문제</b><br>
중복되는 부분 문제는 나눠진 부분 문제가 중복되는 경우로, 메모이제이션 기법을 사용해 중복 계산을 없앱니다.<br>
<b>2. 최적 부분 구조</b><br>
최적 부분 구조를 가진다는 것은 전체 문제의 최적해가 부분 문제의 최적해들로써 구성된다는 것입니다.<br>
</p>

<hr>
<a name="one"><b>1. 버블 정렬(Bubble Sort)에 대해 설명해주세요.</b></a>
<hr>
<p>
버블 정렬는 서로 인접한 두 원소를 비교하여 정렬하는 알고리즘입니다. <br>
0번 인덱스부터 n-1번 인덱스까지 n번까지의 모든 인덱스를 비교하며 정렬합니다. 시간 복잡도는 O(n^2)(n제곱)입니다.
</p>
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdF7CXf%2FbtrunN5i9wZ%2FwDQ3px86zQFffgoq8X6jk0%2Fimg.png">


<hr>
<a name="two"><b>2. 선택 정렬(Selection Sort)에 대해 설명해주세요.</b></a>
<hr>
<p>
선택 정렬은 첫 번째 값을 두번째 부터 마지막 값까지 차례대로 비교하여 최솟값을 찾아 첫 번째에 놓고, 
두 번째 값을 세 번째 부터 마지막 값까지 비교하여 최솟값을 찾아 두 번째 위치에 놓는 과정을 반복하며 정렬하는 알고리즘입니다. 시간복잡도는 O(n^2)입니다.
</p>
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FQ4cCJ%2FbtrugRai7Eu%2FRRRuKTk5SmtWwwHtukI321%2Fimg.png">


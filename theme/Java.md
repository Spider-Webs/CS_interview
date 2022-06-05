<h2>자바 기술 면접</h2>
<b>1. 컴파일</b><br>
<hr>
<h4>컴파일 과정</h4>
<ul>
  <li>개발자가 .java파일을 생성하고</li>
  <li>build를 합니다</li>
  <li>java compiler의 javac의 명령어를 통해 바이트코드(.class)를 생성하고</li>
  <li>Class Loader를 통해 JVM메모리 내로 로드합니다 이후</li>
  <li>실행엔진을 통해 컴퓨터가 읽을 수 있는 기계어로 해석된다(각 운영체제에 부합하는 기계어)</li>
</ul>
<h5>빌드란?</h5>
<pre>
소스코드 파일을 실행가능한 소프트웨어 결과물로 만드는 일련의 과정
빌드의 단계 중 컴파일이 포함되어있고
빌드 과정을 도와주는 도구를 빌드 툴이라 합니다
빌드 툴이 제공해주는 기능으로는 다음과 같은 기능이 있습니다
<ul>
<li>전처리</li>
<li>컴파일</li>
<li>패키징</li>
<li>테스팅</li>
<li>배포</li>
빌드 툴로는 Ant, Maven, Gradle 등이 있습니다.
</ul>
</pre>

<h5>컴파일이란?</h5>
<pre>
컴퓨터가 이해할 수 있는 기계어로 변환하는 작업입니다. 이러한 작업을 해주는 프로그램을 가르켜 컴파일러(Compiler)라 합니다.
자바의 경우, 자바가상머신(JVM)에서 실행가능한 바이트코드 형태의 클래스파일이 생성이 됩니다.
</pre>
<strong>Tip.</strong>
<h5>Compiler vs Interpreter</h5>
🤚<br>
컴파일러는 전체 소스코드를 보고 명령어를 수집하고 재구성하지만
인터프리터는 소스코드의 각 행을 연속적으로 분석하며 실행합니다.
<br>
🤚 <br>
인터프리터는 고레벨 언어를 바로 기계어로 번역하지 않고 중간 형태로 변환시킨 후 실행합니다.
반면 컴파일러는 고레벨 언어를 바로 기계어로 변환합니다.
<hr>
<b>2. String, StringBuffer, StringBuilder의 차이 </b>
<hr>
<ul>
  <li>String은 불변속성이지만, StringBuffer와 StringBuilder는 가변의 속성을 가집니다</li>
  <li>StringBuffer는 동기화를 지원하여 멀티쓰레드 환경에서 주로 사용합니다</li>
  <li>StringBuilder는 동기화를 지원하지 않아 싱글 쓰레드 환경에서 주로 사용합니다</li>
</ul>
<pre>
String 클래스는 불변하기 때문에 문자열을 수정하는 시점에 <b>새로운 String 인스턴스</b>가 생성됩니다<br>
수정하기 이전 문자열의 경우 할당 되어 있던 메모리영역은 Garbage로 남아 있다가 GC(garbage collection)에 의해 사라집니다
그러므로 변하지 않는 문자열의 경우 String을 사용하면 좋은 성능을 발휘 하지만 추가 삭제 수정등 연산이 빈번할 경우 String 클래스는 힙 메모리에 많은 Garbage가 생성되어 메모리 부족이 발생 됩니다<br>
이를 해결하기 위해 가변성을 가지는 StringBuffer / StringBuilder 클래스가 도입되었으며, 
두 클래스의 가장 큰 차이점은 동기화 유무 입니다. StringBuffer는 동기화를 지원하여 멀티쓰레드 환경에서 안전하며
(String 또한 불변이기에 여러개의 thread가 불변객체에 접근해서 수정하려해도 수정이 불가능하기때문에 멀티쓰레드 환경에서 안정성이 있습니다)
StringBuilder는 동기화를 지원하지않아 멀티쓰레드 환경에서는 적합하지 않지만, 단일쓰레드에서의 성능은 StringBuffer보다 뛰어납니다
</pre>


<hr>
<h2>참조</h2>
<h3><a href="https://dev-coco.tistory.com/">슬기로운 개발 생활</a></h3>

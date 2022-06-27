<h2>데이터베이스 기술 면접</h2>
<hr>
<ol>
  <h5><a href="#zero"><li>데이터베이스 풀 에대해 설명해주세요</li></a></h5>
  <h5><a href="#one"><li>트리거에 </li></a></h5>
</ol>

<br><br>

<hr>
<a name="zero"><b>0. 데이터베이스 풀 에대해 설명해주세요.</b></a>
<hr>
<ul>
  <li>
    <h5>Connection Pool</h5>
    <ul>
      <li>클라이언트의 요청에 따라 각 어플리케이션의 스레드에서 데이터베이스에 접근하기 위해서는 Connection이 필요하다.</li>
      <li>데이터베이스와 Connection한 객체들을 미리 생성해 Pool에 저장해두었다가, 클라이언트의 요청이 들어올 때마다 사용/반환하는 방식</li>
    </ul>
  </li>  
  <li>
    DB에 접근하는 단계
    <ol>
      <li>웹 컨테이너가 실행되면서 DB와 연결된 Connection 객체들을 미리 생성하여 pool에 저장한다.</li>
      <li>DB에 요청 시, pool에서 Connection 객체를 가져와 DB에 접근한다.</li>
      <li>처리가 끝나면 다시 pool에 반환한다.</li>
    </ol>  
  </li>
  <li>
     Connection이 부족할 경우
    <ul>
      <li> 모든 Connection이 요청을 처리 중일 때, 해당 클라이언트의 요청을 대기 상태로 전환</li>
      <li>  Pool에 Connection 객체가 반환되면 순차적으로 요청을 처리</li>
    </ul>  
  </li>
  
  <li>
    장점
    <ul>
      <li>매 연결마다 Connection 객체를 생성/제거하는 비용 감소</li>
      <li>미리 생성된 Connection 객체를 사용하므로 데이터베이스 접근 시간 단축</li>
      <li>Connection 수를 제한해 부하 조정</li>
    </ul>  
  </li>
  
  <li>
    단점
    <ul>
      <li>Connection 또한 객체이므로 메모리 차지</li>
      <li>Connection 개수를 잘 못 설정할 경우, 쓸모없는 Connection이 발생할 수 있음</li>
    </ul>  
  </li>
  
  <li>
    Thread Pool
    <ul>
      <li>비슷한 맥락으로 Thread pool이라는 개념도 있다.</li>
      <li>이 역시 매 요청마다 요청을 처리할 Thread를 만드는것이 아닌, 미리 생성한 pool 내의 Thread를 소멸시키지 않고 재사용하여 효율적으로 자원을 활용하는 기법.</li>
    </ul>
  </li>
  
  <li>
    Thread Pool과 Connection pool
    <ul>
      <li>WAS에서 Thread pool과 Connection pool내의 Thread와 Connection의 수는 직접적으로 메모리와 관련이 있기 때문에, 많이 사용하면 할 수록 메모리를 많이 점유하게 된다. 그렇다고 반대로 메모리를 위해 적게 지정한다면, 서버에서는 많은 요청을 처리하지 못하고 대기 할 수 밖에 없다.</li>
      <li>보통 WAS의 Thread의 수가 Conncetion의 수보다 많은 것이 좋은데, 그 이유는 모든 요청이 DB에 접근하는 작업이 아니기 때문이다.</li>
    </ul>  
  </li>
  
</ul>  

<hr>
<a name="one"><b>1. 트리거(Trigger)에 대해 설명해주세요.</b></a>
<hr>
<ul>
  <li>트리거는 특정 테이블에 대한 이벤트에 반응해 INSERT, DELETE, UPDATE 같은 DML 문이 수행되었을 때, 데이터베이스에서 자동으로 동작하도록 작성된 프로그램입니다.</li>
  <li>사용자가 직접 호출하는 것이 아닌, 데이터베이스에서 자동적으로 호출한다는 것이 가장 큰 특징입니다.</li>
</ul>  

<hr>
<h2>참조</h2>
<h3><a href="https://www.youtube.com/channel/UCHFz--glnVVP1xBLA-8kltg">인큐티비 - 유튜브</a>
<h3><a href="https://dev-coco.tistory.com">슬기로운 개발 생활 - 블로그</a></h3>
<h3><a href="https://dheldh77.tistory.com/entry/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4-%ED%92%80Database-Pool">테리의 일상 - 블로그</a></h3>

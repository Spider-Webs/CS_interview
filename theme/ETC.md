
<ol>
<h5><a href="#zero"><li> Local Cache vs Global Cache 에대해 설명해주세요 </li></a></h5>
<h5><a href="#one"><li> Redis vs Memcached 에대해 설명해주세요 </li></a></h5>
</ol>


<hr>
<a name="zero"><b>0. Local Cache vs Global Cache 에대해 설명해주세요 </b></a>
<hr>
<ul>
  <li>
    <h4>캐싱이란?</h4>
    <ul>
      <li>캐싱(Caching)은 애플리케이션의 처리 속도를 높여준다. 이미 가져온 데이터나 계산된 결과값의 복사본을 저장함으로써 처리 속도를 향상시키며, 이를 통해 향후 요청을 더 빠르게 처리할 수 있다. 대부분의 프로그램이 동일한 데이터나 명령어에 반복해서 엑세스하기 때문에 캐싱은 효율적인 아키텍처 패턴이다.</li>
    </ul>
  </li>
  <br>
  <li>
    <h4>캐시를 적용하기에 적합한 데이터</h4>
    <ul>
      <li>반복적이고 동일한 결과가 나오는 기능의 반환값</li>
      <li>업데이트가 자주 발생하지 않는 데이터</li>
      <li>자주 조회되는 데이터</li>
      <li>입력값과 출력값이 일정한 데이터</li>
      <li>캐싱된 데이터는 데이터 갱신으로 인해 DB와 불일치가 발생할 수 있다. 그렇기 때문에 데이터 Update가 잦게 일어나거나 데이터 불일치시 비즈니스 로직 상 문제가 발생할 수있는 기능은 캐싱 대상으로 적합하지 않다.</li>
    </ul>  
  </li>
  <br>
  <li>
    <h4>Local Cache vs Global Cache</h4>
    <ul>
      <li>
        <h5>Local Cache</h5>
        <ul>
          <li>Local 장비 내에서만 사용 되는 캐시</li>
          <li>Local 장비의 Resource를 이용한다 (Memory, Disk)</li>
          <li>Local에서 작동 되기 때문에 속도가 빠르다.</li>
          <li>Local에서만 작동되기 때문에 다른 서버와 데이터 공유가 어렵다</li>
        </ul>  
      </li>
    <br>
      <li>
        <h5>Global Cache</h5>
        <ul>
          <li>여러 서버에서 Cache Server에 접근하여 사용하는 캐시</li>
          <li>데이터를 분산하여 저장 할 수 있다</li>
          <li>Local Cache에 비해 상대적으로 느리다 (네트워크 트래픽)</li>
          <li>별도의 Cache Server를 이용하기 때문에 서버 간 데이터 공유가 쉽다.</li>
        </ul>  
      </li>
    </ul>
  </li>
</ul>

<hr>
<a name="one"><b>1. Redis vs Memcached 에대해 설명해주세요  </b></a>
<hr>
<h3><a href="https://chrisjune-13837.medium.com/redis-vs-memcached-10e796ddd717"> Redis vs Memcached</a>


  
  
  
  
  
  
  
<hr>
<h2>참조</h2>
<h3><a href="https://dev-jj.tistory.com/">제제의 개발 발자취 - 블로그</a>
<h3><a href="https://velog.io/@whitebear/%EC%BF%A0%ED%82%A4-%EC%84%B8%EC%85%98-%ED%86%A0%ED%81%B0JWT-%ED%99%95%EC%8B%A4%ED%9E%88-%EC%95%8C%EA%B3%A0-%EA%B0%80%EA%B8%B0">whitebear - 블로그</a>

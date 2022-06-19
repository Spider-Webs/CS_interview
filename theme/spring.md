<h2>스프링 기술 면접</h2>
<hr>
<ol>
  <h5><a href="#zero"><li>Spring Framework에 대해 설명해주세요.</li></a></h5>
  <h5><a href="#one"><li> Spring Boot와 Spring Framework의 차이점을 설명해주세요.</li></a></h5>
  <h5><a href="#two"><li> Spring MVC에 대해 설명해주세요.</li></a></h5>
  <h5><a href="#three"><li> MVC는 어떠한 흐름으로 요청을 처리하는지 설명해주세요.</li></a></h5>
  <h5><a href="#four"><li> 제어의 역전(IoC)에 대해 설명해주세요.</li></a></h5>
</ol>

<br><br>

<hr>
<a name="zero"><b>0. Spring Framework에 대해 설명해주세요.</b></a>
<hr>
<p> 스프링 프레임워크는 자바 개발을 편리하게 해주는 오픈소스 프레임워크 입니다.</p>
<ul>
  <li>
    경량 컨테이너로서 자바 객체를 직접 관리
      <ul>
        <li>각각의 객체 생성, 소멸과 같은 라이프 사이클을 관리하며 스프링으로부터 필요한 객체를 얻어올 수 있습니다.</li>
     </ul>
  </li>

  <li>
    제어의 역전(IoC)이라는 기술을 통해 어플리케이션의 느슨한 결합을 도모
     <ul>
        <li>컨트롤의 제어권이 사용자가 아닌 프레임워크에 있어서 필요에 따라 스프링에서 사용자의 코드를 호출합니다</li>
     </ul>
  </li>
  <li>
    의존성 주입(DI, Dependency Injection)을 지원
     <ul>
        <li>각각의 계층이나 서비스들 간에 의존성이 존재할 경우 프레임워크가 서로 연결시켜줍니다.</li>
     </ul>
  </li>
  <li>
    관점 지향 프로그래밍(AOP, Aspect-Oriented Programming)을 지원
     <ul>
        <li>트랜잭션이나 로깅, 보안과 같이 여러 모듈에서 공통적으로 사용하는 기능의 경우 해당 기능을 분리하여 관리할 수 있습니다.</li>
     </ul>
  </li>
</ul>

<hr>
<a name="one"><b>1. Spring Boot와 Spring Framework의 차이점을 설명해주세요.</b></a>
<hr>
<pre>
가장 큰 차이점은 Auto Configuration의 차이인 것 같습니다. Spring은 프로젝트 초기에 다양한 환경설정을 해야 하지만, 
Spring Boot는 설정의 많은 부분을 자동화하여 사용자가 편하게 스프링을 활용할 수 있도록 돕습니다.
spring boot starter dependency만 추가해주면 설정은 끝나고, 내장된 톰캣을 제공해 서버를 바로 실행할 수 있습니다.
</pre>

<hr>
<a name="two"><b>2. Spring MVC에 대해 설명해주세요.</b></a>
<hr>
<ul>
  <li>MVC는 Model, View, Controller의 약자이며, 각  기능을 구분하는데 중점을 둔 디자인 패턴입니다.</li>
  <li>Model은 데이터 관리 및 비즈니스 로직을 처리하는 부분이며, (DAO, DTO, Service 등)</li>
  <li>View는 비즈니스 로직의 처리 결과를 통해 유저 인터페이스가 표현되는 구간입니다. 
    <br>(html, jsp, tymeleaf, mustache 등 화면을 구성하기도 하고, Rest API로 서버가 구현된다면 json 응답으로 구성되기도 한다.)</li>
  <li>Controller는 사용자의 요청을 처리하고 Model과 View를 중개하는 역할을 합니다. 
    <br>Model과 View는 서로 연결되어 있지 않기 때문에 Controller가 사이에서 통신 매체가 되어줍니다.
</li>
</ul> 

<hr>
<a name="three"><b>3.  MVC는 어떠한 흐름으로 요청을 처리하는지 설명해주세요.</b></a>
<hr>
<img src="https://user-images.githubusercontent.com/105139722/174419404-a99d8876-6b6a-4f70-a3c1-01b7803da10e.png">
<b>DispatcherServlet</b> : 클라이언트에게 요청을 받아 응답까지의 MVC 처리과정을 통제한다.<br>
<b>HandlerMapping</b> : 클라이언트의 요청 URL을 어떤 Controller가 처리할지 결정한다.<br>
<b>HandlerAdapter</b> : HandlerMapping에서 결정된 핸들러 정보로 해당 메소드를 직접 호출해주는 역할을 한다.<br>
<b>ViewResolver</b> : Controller의 처리 결과(데이터)를 생성할 view를 결정한다.<br>
<br>

<ol>
  <li>클라이언트는 URL을 통해 요청을 전송한다.</li>
  <li>디스패처 서블릿은 핸들러 매핑을 통해 해당 요청이 어느 컨트롤러에게 온 요청인지 찾는다.</li>
  <li>디스패처 서블릿은 핸들러 어댑터에게 요청의 전달을 맡긴다.</li>
  <li>핸들러 어댑터는 해당 컨트롤러에 요청을 전달한다.</li>
  <li>컨트롤러는 비즈니스 로직을 처리한 후에 반환할 뷰의 이름을 반환한다.</li>
  <li> 디스패처 서블릿은 뷰 리졸버를 통해 반환할 뷰를 찾는다.</li>
  <li>디스패처 서블릿은 컨트롤러에서 뷰에 전달할 데이터를 추가한다</li>
  <li>데이터가 추가된 뷰를 반환한다.</li>
</ol>  

<hr>
<a name="four"><b>4. 제어의 역전(IoC)에 대해 설명해주세요.</b></a>
<hr>
<ul>
  <li>
    <h5>IoC(제어의 역전)란</h5>
    <ul>
      <li>
        객체의 생성에서부터 생명주기의 관리까지 모든 객체에 대한 제어권이 바뀌는 것을 의미합니다
      </li>
      <li>
        컴포넌트 의존관계 설정(Component dependency resoulution), 설정(Configuration) 및 생명주기(LifeCycle)을 
        해결하기 위한 디자인 패턴(Design Pattern)입니다.
      </li>
    </ul>
  </li>
  <li>
    <h5>Spring에서의 IoC</h5>
    <pre>
    스프링 프레임워크도 객체를 생성하고 관리하고 책임지고 의존성을 관리해주는 컨테이너가 있는데,
    바로 IoC 컨테이너(=스프링 컨테이너) 입니다.
    <b>
    <ul>
      <li>인스턴스 생성부터 소멸까지의 인스턴스 생명주기 관리를 개발자가 아닌 컨테이너가 대신 해줍니다.</li>
      <li>객체관리 주체가 프레임워크(Container)가 되기 때문에 개발자는 로직에 집중할 수 있는 장점이 있습니다.</li>
      <li>POJO(Plain Old Java Object)의 생성, 초기화, 서비스, 소멸에 대한 권한을 가집니다</li>
    </ul>
    </b>
    </pre>
  </li>
  <li>
    IoC의 분류
    <p>
      <b>DL(Dependency Lookup) 과 DI (Dependency Injection)</b>
    </p>
       <ul>
         <li>
           <b>DL : </b>저장소에 저장되어 있는 Bean에 접근하기 위해 컨테이너가 제공하는 API를 이용하여 Bean을 Lookup하는 것 입니다
         </li>
         <li>
           <b>DI : </b>각 클래스간의 의존관계를 빈 설정(Bean Definition) 정보를 바탕으로 컨테이너가 자동으로 연결해주는 것 입니다
           <p>DI의 방법으로는</p>
            <ul>
              <li>
                수정자 주입(Setter Injection)
              </li>
              <li>
               생성자 주입(Constructor Injection)
              </li>
              <li>
                필드 주입(Field Injection)
              </li>
            </ul>
         </li>
      </ul>
  </li>
</ul>





<hr>
<h2>참조</h2>
<h3><a href="https://www.youtube.com/channel/UCHFz--glnVVP1xBLA-8kltg">인큐티비 - 유튜브</a>
<h3><a href="https://dev-coco.tistory.com">슬기로운 개발 생활 - 블로그</a></h3>
<h3><a href="https://velog.io/@sungsuzi/oop%EC%9D%98-4%EA%B0%80%EC%A7%80-%ED%8A%B9%EC%A7%95">suzi_911.log - 블로그</a></h3>
<h3><a href="https://jackjeong.tistory.com/">잭코딩 - 블로그</a></h3>
<h3><a href="https://webclub.tistory.com/">webclub - 블로그</a></h3>

<h2>스프링 기술 면접</h2>
<hr>
<ol>
  <h5><a href="#zero"><li>Spring Framework에 대해 설명해주세요.</li></a></h5>
  <h5><a href="#one"><li> Spring Boot와 Spring Framework의 차이점을 설명해주세요.</li></a></h5>
  <h5><a href="#two"><li> Spring MVC에 대해 설명해주세요.</li></a></h5>
  <h5><a href="#three"><li> MVC는 어떠한 흐름으로 요청을 처리하는지 설명해주세요.</li></a></h5>
  <h5><a href="#four"><li> 제어의 역전(IoC)에 대해 설명해주세요.</li></a></h5>
  <h5><a href="#five"><li> 의존성 주입(DI, Dependency Injection)에 대해 설명해주세요.</li></a></h5>
  <h5><a href="#six"><li> DAO와 DTO의 차이에 대해 설명해주세요</li></a></h5>
  <h5><a href="#seven"><li> AOP(관점지향프로그래밍)에대해 설명해주세요</li></a></h5>
  <h5><a href="#eight"><li> 스프링에서 빈(Bean)을 등록하는 방법에 대해 말해보세요</li></a></h5>
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
        컴포넌트 의존관계 설정(Component dependency resoulution)과 설정(Configuration) 및 생명주기(LifeCycle)을 
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
<p>
POJO(Plain Old Java Object)란? 
주로 특정 자바 모델이나 기능, 프레임워크를 따르지 않는 Java Object를 지칭한다.
Java Bean 객체가 대표적이다.
간단하게 getter / setter 입니다.
</p>
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
<a name="five"><b>5.  의존성 주입(DI, Dependency Injection)에 대해 설명해주세요.</b></a>
<hr>
<pre>
의존성 주입은 필요한 객체를 직접 생성하는 것이 아닌 외부로부터 객체를 받아서 사용하는 것입니다.
이를 통해 객체간의 결합도를 줄이고 코드의 재사용성을 높일 수 있습니다.
<br>

<ul>
특징으로는
  <li>‘new’ 키워드를 사용해 모듈 내에서 다른 모듈을 초기화하지 않으려면 객체 생성은 다른 곳에서 하고, 생성된 객체를 참조하면 됩니다.</li>
  <li>의존성 주입은 IoC 개념을 바탕으로 하며, 클래스가 외부로부터 의존성을 가져야 합니다.</li>
</ul>
의존성 주입은 생성자 주입, 필드 주입, 세터 주입의 3 가지 방법이 있습니다.
이 중 Spring에서 가장 권장하는 의존성 주입 방법은 생성자를 통한 주입 방법입니다.
그 이유는 1. 순환 참조를 방지 2. 불변성을 가짐 3. 테스트에 용이하기 때문입니다.
<br>
💡
순환참조 문제란 A 클래스가 B 클래스의 Bean 을 주입받고, B 클래스가 A 클래스의 Bean 을 주입받는 상황처럼 
서로 순환되어 참조할 경우 발생하는 문제를 의미한다.
</pre>

<hr>
<a name="six"><b>6. DAO와 DTO의 차이에 대해 설명해주세요</b></a>
<hr>
<ul>
  <li>
    <b>DAO(Data Access Object)란</b>
    <ul>
      <li>
        DB의 데이터를 조회하거나 조작하는 기능을 전담하도록 만든 객체를 말합니다
      </li>
        <li>
          DB에 접근을 하기위한 로직과 비즈니스 로직을 분리하기 위해서 사용 합니다
      </li>
    </ul>
  </li>
  
  <li>
    <b>DTO(Data Transfer Object)란</b>
    <ul>
      <li>
        계층간 데이터 교환을 위한 자바빈즈를 말합니다.
      </li>
        <li>
          일반적인 DTO는 로직을 갖고 있지 않는 순수한 데이터 객체이며, 속성과 그 속성에 접근하기 위한 getter, setter 메소드만 가진 클래스입니다
      </li>
    </ul>
  </li>  
  <li>
    <b>VO (Value Object)란</b>
      <ul>
        <li>
        실제 데이터만을 저장하는 객체를 말합니다.
        </li>
        <li>
         오직 read만 가능하며 getter만 가능해야 합니다.
        </li>
      </ul>
  </li> 
</ul>

<hr>
<a name="seven"><b>7. AOP(관점지향프로그래밍)에대해 설명해주세요</b></a>
<hr>
<h5>AOP란?</h5>
<pre>
AOP는 OOP(Object Oriented Programming, 객체지향 프로그래밍)를 돕는 보조적인 기술로,
관심사의 분리(기능의 분리)의 문제를 해결하기 위해 만들어진 프로그래밍 패러다임 입니다.
AOP는 기능을 핵심 관심 사항(Core Concern)과 공통 관심 사항(Cross-Cutting Concern)으로 분리시키고
 각각을 모듈화 하는 것을 의미합니다.
</pre>
<ul>
  <li>업무 로직을 포함하는 기능을 핵심 기능(Core Concern)이라하며,</li>
  <li>핵심 기능을 도와주는 부가적인 기능을 부가 기능(Cross-Cutting Concern) 이라고 부릅니다.</li>
  <li>AOP는 부가 기능을 애스펙트(Aspect)로 정의하여, 핵심 기능에서 부가 기능을 분리함으로써 핵심 기능을 설계하고 구현할 때 객체지향적인 가치를 지킬 수 있게 도와주는 개념입니다.</li>
</ul>

<h4>AOP의 목적</h4>
<ul>
  <li>소스 코드에서 여러 번 반복해서 쓰는 코드(= 흩어진 관심사, Concern)를 Aspect로 모듈화하여 핵심 로직에서 분리 및 재사용</li>
  <li>개발자가 핵심 로직에 집중할 수 있게 하기 위함</li>
  <li>주로 부가 기능을 모듈화</li>
</ul>  

<h4>AOP의 특징</h4>
<pre>
<h5>프록시 패턴 기반</h5>- Spring은 타겟(Target) 객체에 대한 프록시를 만들어서 제공한다.
- 타겟을 감싸는 프록시는 실행시간(RunTime)에 생성된다.
- 프록시는 어드바이스(Advice)를 타겟 객체에 적용하면서 생성되는 객체
- 프록시 객체를 쓰는 이유는 접근 제어 및 부가기능을 추가하기 위함이다.

<h5>프록시가 호출을 가로챔(Intercept)</h5>- 프록시는 타겟 객체에 대한 호출을 가로챈 다음 Advice의 부가기능 로직을 수행하고난 후에 타겟의 핵심기능 로직을 호출한다.
(전처리 어드바이스)
- 타겟의 핵심기능 로직 메소드를 호출한 후에 부가기능을 수행하는 경우도 있다.
(후처리 어드바이스)

<h5>메소드 JoinPoint만 지원한다.</h5>- Spring은 동적 프록시를 기반으로 AOP를 구현하므로 메소드 조인 포인트만 지원
- 핵심기능(타겟)의 메소드가 호출되는 런타임 시점에만 부가기능(어드바이스)를 적용할 수 있음
- 반면에 AseptJ같은 고급 AOP 프레임워크를 사용하면 객체의 생성, 필드값의 조회와 조작, static 메소드 호출 및 동기화 등의 
다양한 작업에 부가기능을 적용할 수 있다.
</pre>

<h4>AOP의 주요 용어</h4>
<pre>

<h5>Aspect</h5>흩어진 관심사를 모듈화 한 것
Advice + PointCut

<h5>Target</h5>Aspect를 적용하는 곳(클래스, 메소드 등)

<h5>Advice</h5>실질적으로 수행해야 하는 기능을 담은 구현체

<h5>JoinPoint</h5>Advice가 적용될 위치
끼어들 수 있는 지점
ex. 메소드 진입 시, 생성자 호출 시, 필드에서 값 꺼낼 때 등

<h5>PointCut</h5>JoinPoint의 상세 스펙 정의
더욱 구체적으로 Advice가 실행될 지점 지정

<h5>Weaving</h5>PointCut에 의해 결정된 Target의 JoinPoint에 Advice를 삽입하는 과정
</pre>


<hr>
<a name="eight"><b>9. 스프링에서 빈(Bean)을 등록하는 방법에 대해 말해보세요.</b></a>
<hr>
<pre>
<b>스프링 컨테이너에 등록한 객체들을 '빈'이라고 합니다.</b>
스프링 컨테이너에 Bean을 등록하는 방법은 두가지가 있습니다.
<ol>
  <li>첫번째는 컴포넌트 스캔과 자동 의존관계 설정입니다</li>
  <li>두번째는 자바코드로 직접 스프링 빈 등록 입니다</li>
</ol>
<h5>컴포넌트 스캔과 자동 의존관계 설정의 경우</h5>스프링 부트에서 사용자가 클래스를 스프링 빈으로 등록하는 가장 쉬운 방법은 클래스 선언부 위에 @Component 어노테이션을 사용하는 것입니다. 
@Controller, @Service, @Repository는 모두 @Component를 포함하고 있으며 
해당 어노테이션으로 등록된 클래스들은 스프링 컨테이너에 의해 자동으로 생성되어 스프링 빈으로 등록됩니다.
<br>
<b>자바 코드로 직접 스프링 빈 등록</b>의 경우는 수동으로 등록하는 방법입니다. 
수동으로 스프링 빈을 등록하려면 자바 설정 클래스를 만들어 사용 해야 합니다. 
XML로 스프링 빈을 등록하는 방법도 있지만, 최근에는 거의 사용하지 않습니다.
<br> 
설정 클래스를 만들고  @Configuration 어노테이션을 클래스 선언부 위에 추가하면 됩니다. 
그리고 특정 타입을 리턴하는 메소드를 만들고, @Bean 어노테이션을 붙여주면 자동으로 해당 타입의 빈 객체가 생성됩니다. 

</pre>

<hr>
<h2>참조</h2>
<h3><a href="https://www.youtube.com/channel/UCHFz--glnVVP1xBLA-8kltg">인큐티비 - 유튜브</a>
<h3><a href="https://dev-coco.tistory.com">슬기로운 개발 생활 - 블로그</a></h3>
<h3><a href="https://velog.io/@sungsuzi/oop%EC%9D%98-4%EA%B0%80%EC%A7%80-%ED%8A%B9%EC%A7%95">suzi_911.log - 블로그</a></h3>
<h3><a href="https://jackjeong.tistory.com/">잭코딩 - 블로그</a></h3>
<h3><a href="https://webclub.tistory.com/">webclub - 블로그</a></h3>

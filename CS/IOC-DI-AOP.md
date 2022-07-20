IoC란?
=====
* ### IoC(제어 반전/역전, Inversion Of Control)
* 객체의 생성, 생명주기의 관리까지 모든 객체에 대한 제어권이 바뀐 것을 의미
* 컴포넌트 의존관계 설정, 설정 및 생명주기를 해결하기 위한 디자인 패턴

IoC Container
---------
▶ **스프링 프레임워크에서 객체를 생성·의존성관리를 해주는 컨테이너**


 * ###### 컨테이너란? 
   ###### ▶ 객체의 생명주기를 관리, 생성된 인스턴스들에게 추가적인 기능을 제공하도록 하는것
 

### 장점(목적)
* 개발자는 비즈니스 로직에 집중
* 객체 생성코드가 없어 TDD가 용이
* 작업을 구현하는 방식과 작업 수행을 분리
* 모듈을 바꾸어도 다른 시스템에 부작용을 일으키지 않음
* 다른 시스템이 어떻게 동작할지에 대해 고민없이 미리 정해진 협약대로만 동작

<hr/>

DI란?
====

* ### DI(의존관계 주입, Dependency Injection)
* 외부에서 두 객체 간의 관계를 결정해주는 디자인 패턴
* 인터페이스 사이에서 클래스 레벨에서의 의존관계가 고정되지 않도록 함
* 런타임시에 동적으로 주입하여 유연성 확보·결합도↓

###### 의존관계(Dependency란)?
###### ▶ 의존대상B가 변하면, 그것이 A에 영향이 미친다. 즉, B의 기능이 추가·변경되거나 형식이 바뀌면 A에 영향이 미친다.

### 장점(목적)
* 두 객체 간의 관계라는 관심사 분리
* 두 객체 간의 결합도↓
* 객체의 유연성·재사용성↑
* 테스트 작성 용이
* 코드 단순화(종속적이던 코드의 수 감소)

<hr/>

AOP란?
=====
* ### AOP(관점 지향 프로그래밍, Aspect Oriented Programming)
* 흩어진 Aspect를 모듈화 할 수 있는 프로그래밍 기법
* 어떤 로직을 기준으로 핵심적인 관점, 부가적인 관점으로 나누어서 보고 그 관점을 기준으로 각각 모듈화하는 기법

AOP의 주요 개념
-------------
* ### Aspect
   ▶ 흩어진 관심사(Crosscutting concerns)를 모듈화 한 것 (Advice와 Point Cut이 들어감)
* ### Target
  ▶ Aspect가 가지고 있는 Advice가 적용되는 대상(클래스,메서드 등)
* ### Advice
    ▶ 어떤 일을 해야할 지에 대한 것, 실질적인 부가기능을 담은 구현체
* ### Join Point
  ▶ 메서드 실행 시점(Advice가 적용될 위치, 끼어들 수 있는 지점, 생성자 호출 시점, 필드에서 값을 호출 했을 때 등에 적용)
* ### Point Cut
  ▶ Joint Point의 상세한 스펙을 정의한 것 ('A란 메서드의 진입 시점에 호출할 것' 같은 구체적인 Advice 실행 지점 정의)

<br/>

### 구현방법
  1. SpringAOP를 활용
  2. 프록시를 사용함으로써 부가기능을 실행
  3. AspectJ를 사용

### 특징
* 프록시 패턴 기반의 AOP 구현체(프록시 객체를 쓰는 이유는 접근 제어 및 부가기능을 추가하기 위함)
* 스프링 빈에만 AOP를 적용 가능
* 모든 AOP기능을 제공하는 것이 목적이 아닌 IoC와 연동하여 엔터프라이즈 애플리케이션에서 가장 흔한 문제에 대한 솔루션 제공을 목적으로 함

###### 패턴을 사용하는 이유?
###### ▶ 기존 코드의 변경 없이 접근 제어 또는 부가 기능을 추가하기 위함


<hr/>

참고자료
* #### OSI
  * [슬기로운 개발 생활](https://dev-coco.tistory.com/80)
  * [Jang](https://medium.com/@jang.wangsu/di-inversion-of-control-container-%EB%9E%80-12ecd70ac7ea)

* #### DI
  * [mangkyu](https://mangkyu.tistory.com/150)
  * [Jang](https://medium.com/@jang.wangsu/di-dependency-injection-%EC%9D%B4%EB%9E%80-1b12fdefec4f)
  * [tecoble](https://tecoble.techcourse.co.kr/post/2021-04-27-dependency-injection/)

* ### AOP
  * [한선우 git](https://yadon079.github.io/2021/spring/spring-aop-core)
  * [새로비](https://engkimbs.tistory.com/746)
  * [wjdrbs96](https://devlog-wjdrbs96.tistory.com/398)
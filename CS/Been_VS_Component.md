# 스프링 빈(Spring Bean)이란?
### ▶ Spring IoC 컨테이너가 관리하는 자바 객체
> #### 기존의 Java Programming 에서는 Class를 생성하고 new를 입력하여 원하는 객체를 직접 생성한 후 사용하였음<br/> 
> #### Spring에서는 직접 new를 이용한 객체가 아닌, Spring에 의해 관리당하는 자바 객체를 사용
> #### Spring에 의하여 생성되고 관리되는 자바 객체를 Bean이라고 함

<hr/>

# @Bean
* ### `메소드 레벨`에서 선언
* ### 반환되는 객체를 개발자가 `수동으로 빈으로 등록`하는 어노테이션
* ### `외부 라이브러리들을 Bean으로 등록`하고 싶은 경우에 사용
* ### 유연한 빈 등록이 가능
    ###### 개발자가 컨트롤이 불가능한 외부라이브러리를 빈으로 등록하고 싶을 때 사용

# VS

# @Component
* ### `클래스 레벨`에서 선언
* ### 스프링이 런타임시에 컴포넌트스캔을 하여 `자동으로 빈을 찾고 등록`
* ### `싱글톤 클래스 빈을 생성`하는 어노테이션
* ### 일반적인 빈 등록에 사용
    ###### 개발자가 직접 컨트롤이 가능한 클래스에 사용

<hr/>
참고자료

* [Easy is Perfect](https://melonicedlatte.com/2021/07/11/232800.html)
* [Composite.log](https://velog.io/@composite/Spring-Component-Bean-%EC%95%8C%EA%B3%A0-%EC%93%B0%EA%B8%B0)
* [기억보단 기억을](https://jojoldu.tistory.com/27)
* [DevAndy](https://youngjinmo.github.io/2021/06/bean-component/)
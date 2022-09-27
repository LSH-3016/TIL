# JDK (Java Development Kit)
#### ▶ 자바 SE, 자바 EE, 또는 자바 ME 플랫폼 중 하나를 구현한 것

## 역사
### ■ JDK 1.0a2
* #### 1995년 5월 23일 발표
    ###### 자바 언어 자체가 정식으로 발표된 날
* #### 첫 명칭은 Oak

### ■ JDK 1.0
* #### 1996년 1월 23일 발표
* #### 이름을 Java로 변경

### ■ JDK 1.1
* #### 1997년 2월 19일 발표
* #### `JDBC`, `Inner Class`, `Java Beans`, `RMI`, `Reflection` 등이 추가
    * #### `RMI` : 서로 다른 JVM끼리 객체에 액세스/호출 할 수 있도록 하는 매커니즘
    * #### `Reflection` : 구체적인 클래스 타입을 알지 못해도 클래스의 정보(메서드, 타입, 변수 등)에 접근할 수 있게 해주는 API

### ■ JDK 1.2
* #### 1998년 12월 8일 발표
* #### `Swing GUI`, `JIT`, `Collection Framework` 등 추가
    * #### `JIT` : JVM 안에 속해 있는 컴파일러로 런타임 시 바이트 코드를 원시 시스템코드로 컴파일
    * #### `Collection Framework` : List, Queue, Set, Map 등의 인터페이스로 이루어진 가변 크기의 배열
* #### 자바를 세 가지 버전으로 나눔 (Java SE, ME, EE)

### ■ JDK 1.3
* #### 2000년 발표
* #### `HotSpot JVM`, `JNDI`, `JPDA`, `JavaSound` 등 추가
    * #### `HotSpot JVM` : 애플리케이션의 시작 시간을 빠르게 하고, 적은 메모리를 점유하도록 하는 컴파일러
    * #### `JDNI` : 디렉토리 서비스에서 제공하는 데이터 및 객체를 발견하고 참고하기 위한 API (WAS의 데이터베이스 정보에 설정)
    * #### `JDPA` : 리눅스의 자체 TOMCAT에 접속하여 원격으로 디버깅을 가능하게 하는 아키텍처
    * #### `Java Sound` : 

### ■ JDK 1.4
* #### 2002년 2월 6일 발표
* #### `assert`, `정규표현식`, `XML API`, `Security 2 version`, `Non Blocking IO(NIO)` 등 추가
    #### `assert` : 파라미터의 계산이 제대로 되는지 확인하는 예약어
```java
int value = -1;
assert value >= 0:"음수입니다";
System.out.println("값 :" + value);
```

### ■ Java 5
* #### 2004년 발표
* #### `Generics`, `Annotation`, `AutoBoxing/UnBoxing`, `Enum`, `가변 길이 파라미터`, `Static Imports`, `Concurrency API` 등 추가
* #### Java 5 이전에는 대부분 반환값으로 Object타입을 사용
```java
// Java 5 이전 컬렉션
List list = new ArrayList(10);
list.add(new Integer(10));
```
```java
// Java 5 이후 컬렉션
List<Integer> list = new ArrayList<>();
list.add(10);
```
* #### Generic 등장으로 타입 변환 최소화
```java
// Generic 사용 X
List list = new ArrayList();
list.add("Sangho");
String name = (String) List.get(0);
```
```java
// Generic 사용 O
List<String> list = new ArrayList<>();
list.add("Sangho");
String name = List.get(0);
```

### ■ Java 6
* #### 2004년 9월 30일 발표
* #### `Java Compiler API`, `Pluggable Annotation`, `G1(garbage First) GC 지원` 등 추가

### ■ Java 7
* #### 2011년 7월 7일 발표
* #### `try-catch-resources`, `이진수 리터럴`, `숫자 리터럴에 _ 지원`
* #### Switch문에서 String 사용
```java
switch(a){
    case "sangho":
        System.out.println("상호");
        break;
    case "se":
        System.out.println("SE랩");
        break;
    defalut:
        break;
        }
```

### ■ Java 8
* #### 2014년 3월 18일 발표
* #### 오라클 인수 후 처음 발표한 버전
* #### `Lamda Expression`, `새로운 날짜와 시간 API`, `Interface default/static method`, `Stream`, `PermGen Area 제거`
    * #### `PerGen Area` : 클래스 메타데이터(클래스의 이름, 생성정보, 필드정보, 메서드정보 등)가 존재하는 영역
    * ###### 삭제 이유 : https://blog.voidmainvoid.net/315

### ■ Java 9
* #### 2017년 9월 21일 발표
* #### 인터프리터 언어 쉘처럼 사용할 수 있는 JShell 추가
* #### `모듈 시스템`, `interface private method` 등 추가

### ■ Java 10
* #### 2018년 3월 20일 발표
* #### `Var` 추가
* #### 병렬 처리 가비지 컬렉션, Stop-the-World 추가로 이한 성능 향상
* #### JVM 힙 영역을 시스템 메모리가 아닌 다른 종류의 메모리에도 할당 가능

### ■ Java 11
* #### 2018년 9월 25일 발표
* #### Oracle JDK가 구독형 유료 모델로 전환 (라이선스)
* #### lambda 지역변수 사용법 변경
```java
// Java 11 이전
(var x, var y) -> x.process(y)
```
```java
// Java 11 이후
(x, y) -> x.process(y)
```

### ■ Java 12
* #### 2019년 3월 19일 발표
* #### Switch문 확장
```java
// Java 12 이전
switch (day){
    case MONDAY:
    case TUSEDAY:
    case WEDNESDAY:
    case THURSDAY:
    case FRIDAY:
        System.out,println("주중");
        break;
    case SATURDAY:
    case SUNDAY:
        System.out.println("주말");
        break;
}
```
```java
// Java 12 이후
switch (day){
    case MONDAY, TUSEDAY, WEDNESDAY, THURSDAY, FRIDAY -> System.out,println("주중");
    case SATURDAY, SUNDAY -> System.out.println("주말");
}
```

### ■ Java 13
* #### 2019년 9월 17일 발표
* #### `yield 예약어`, `Multiline Strings` 등 추가
    * #### `Multiline Strings` : [설명](https://dejavuhyo.github.io/posts/java-multiline-string/)

### ■ Java 14
* #### 2020년 3월 18일 발표
* #### `record` 추가

### ■ Java 15
* #### 2020년 9월 15일 발표
* #### `Sealed Class` 추가

### ■ Java 16
* #### 2021년 3월 발표
* #### OpenJDK의 버전관리를 Git으로 변경
    ###### OpenJDK소스를 GIthub에서 확인 가능

### ■ Java 17
* #### 2021년 9월 15일 발표
* `Java LTS`, `Deprecating the Security Manager` 등 추가

<hr/>

참고자료
* [](https://techvu.dev/136)
* [](https://www.skyer9.pe.kr/wordpress/?p=287)
# 에러(Error)
#### ▶ 시스템에 비정상적인 상황이 발생한 경우

## 특징
* #### 주로 JVM에서 발생
* #### 코드상으로 해결이 불가
* #### ex) OutOfMemoryError, ThreadDeath, StackOverflowError
    #### `OutOfMemoryError` : Java Heap을 더 이상 늘릴 수 없음 (객체나 Array, 배열 생성 불가)
    #### `ThreadDeath` : Thread가 종료되었음
    #### `StackOverflowError` : 너무 큰 지역 변수를 선언하거나 무한반복 함수 호출

<hr/>

# 예외 (Exception)
#### ▶ 정상적인 프로그램의 흐름을 어긋나는 것
![](../CS_IMG/Exception_Structure.png)

## ★ 특징
* #### 프로그래머가 직접 예측하여 막을 수 있음
* #### 처리 방법에는 복구, 회피, 전환이 있음
* #### 예외 처리 여부에 따라 Check Exception과 Unchecked Exception으로 나뉨

<br/>

## ★ 예외의 종류
### 예외는 Checked Exception과 Unchecked Exception으로 구분

## ■ `Checked Exception`
 #### ▶ RuntimeException의 하위 클래스가 아니면서 Exception 클래스 하위 클래스들

## 특징
* #### 예외 처리(try/catch or throw)를 반드시 해야 하는 Exception
* #### Error, FileNotFoundException, ClassNotFoundException 등이 대표적
* #### 스프링 프레임워크에서 트랜젝션 처리 시에 예외가 발생해도 롤백하지 않음


## ■ `Unchecked Exception`
#### ▶ RuntimeException의 하위 클래스들

## 특징
* #### 예외 처리할 필요 X
* #### ArrayIndexOutOfBoundsException, NullPointerException 등이 대표적
* #### 스프링 프레임워크에서 트랜젝션 처리시에 예외가 발생한 경우 롤백을 수행

<br/>

## ★ 예외처리 방법
#### 예외 처리 방법에는 `복구,회피,전환`이 있음

### ○ `예외복구` (throw new)
* #### 예외 상황을 파악하고 문제를 해결해서 정상 상태로 돌려놓는 방법
* #### 예외를 잡아서 일정 시간, 조건만큼 대기하고 다시 재시도를 반복
* #### 최대 재시도 횟수를 넘기게 되면 예외 발생

### ○ `예외처리 회피` (throw)
* #### 예외 처리를 직접 담당하지 않고 호출한 쪽으로 던져 회피하는 방법
* #### 예외 처리가 가능한만큼 처리하고 던지는 것이 좋음
* #### 긴밀하게 역하을 분담하고 있는 관계가 아니라면 예외를 그냥 던지는 것은 무책임

### ○ `예외 전환`
* #### 메서드 밖으로 에외를 던지지만, 적절한 예외로 전환해서 넘김
* #### 조금 더 명확한 의미로 전달을 위해 적합한 의미를 가진 예외로 변경

<hr/>

참고자료
* [오늘도 MadPlay!](https://madplay.github.io/post/java-checked-unchecked-exceptions)
* [Gyun's 개발일지](https://devlog-wjdrbs96.tistory.com/351)
* [개발자 지니의 기록](https://cocobi.tistory.com/146)
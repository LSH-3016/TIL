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

## 특징
* #### 프로그래머가 직접 예측하여 막을 수 있음
* #### 처리 방법에는 복구, 회피, 전환이 있음
* #### 예외 처리 여부에 따라 Check Exception과 Unchecked Exception으로 나뉨

## 예외의 종류
### 예외는 Checked Exception과 Unchecked Exception으로 구분

>## ■ Checked Exception
> #### ▶ RuntimeException의 하위 클래스가 아니면서 Exception 클래스 하위 클래스들
>
>## 특징
>#### 예외 처리(try/catch or throw)를 반드시 해야 하는 Exception
>#### Error, FileNotFoundException, ClassNotFoundException 등이 대표적
>#### 스프링 프레임워크에서 트랜젝션 처리 시에 예외가 발생해도 롤백하지 않음


>## ■ Unchecked Exception
>#### ▶ RuntimeException의 하위 클래스들
>
>## 특징
>#### 예외 처리할 필요 X
>#### ArrayIndexOutOfBoundsException, NullPointerException 등이 대표적
>#### 스프링 프레임워크에서 트랜젝션 처리시에 예외가 발생한 경우 롤백을 수행
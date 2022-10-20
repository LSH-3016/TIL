# Mutable vs Immutable

### ● Mutable : 변할 수 있는
### ● Immutable : 변경할 수 없는, 불변의

# Mutable
### ▶ 생성된 이후에도 수정이 가능한 객체

## 특징
* #### 값을 변경할 수 있는 메소드를 제공(getter / setter 존재)
* #### StringBuffer, StringBuilder, java.util.Date 등이 해당
* #### 병렬처리 시 값을 보장할 수 없음

# Immutable
### ▶ 생성후에는 수정이 불가능한 객체
### 객체의 생성
#### ① new 연산자로 객체 생성
#### ② heap 영역에 객체가 생성되고, 래퍼런스 값을 가지는 변수가 stack에 생성
#### ※ Immutable 객체는 heap 영역에서 객체의 값을 변경할 수 없음

## Immutable 객체 생성 방법
* #### 멤버변수를 final로 설정
* #### setter 메서드를 구현하지 않음
* #### class를 상속하지 못하도록 선언 (class를 final / 생성자를 private)
* #### 방어적 복사(defensive copy) 이용
    #### `방어적 복사` : 객체의 복사본을 만들어 내부 필드 초기화, 또는 getter메서드에 대해 객체의 복사본을 만들어 반환

## 특징
* #### 값을 변경할 수 있는 메소드를 제공하지 않음 (Getter/Setter 미존재)
* #### 객체 값 변경을 시도하면 객체의 값이 아닌 새로운 객체가 생성
* #### Legacy classes, Wrapper classes, String class 등이 해당
    #### `Legacy classes` : HashTable, Stack, Dictionary, Properties, Vector
    #### `Wrapper classes` : Byte, Short, Integer, Long, Float, Double, Character, Boolean

## 장단점
* #### 객체에 대한 신뢰도가 올라감 (객체의 값이 변경되지 않기 때문)
* #### multi-thread 환경에서 동기화 처리 없이 객체 공유 가능 (병렬처리 가능)
* #### 객체의 값이 할당될 때 마다 새로운 객체를 생성하므로 메모리 문제나 성능저하 발생

<hr/>

참고자료
* [코딩못하는사람](https://cantcoding.tistory.com/41)
* [guswlsapdlf](https://velog.io/@guswlsapdlf/Java%EC%9D%98-Mutable%EA%B3%BC-Immutable)
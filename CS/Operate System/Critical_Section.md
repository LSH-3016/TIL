# Critical Section
* #### 병렬 프로그래밍에서 둘 이상의 스레드가 동시에 공유자원에 접근하는 명령문 또는 일부 영역
* #### 서로 다른 두 개의 스레드가 값을 처리하면 동기화 처리를 반드시 해야 함
    #### `동기화` : 다중 프로세스 환경에서 데이터 일관성을 유지하도록 하는 것

## 임계 구역 해결조건
* ### 상호 배제 (Mutual Exclusion)
    #### 하나의 프로세스가 임계 구역에서 실행되고 있으면, 다른 프로세스들은 임계 구역에서 실행될 수 없음
* ### 진행 (Progress)
    #### 임계 구역에 실행 중인  프로세스가 없을 경우, 프로세스를 적절히 선태하여 실행시켜야 함
* ### 한정된 대기 (Bounded Waiting)
    #### 프로세스 기아 방지를 위해 임계 구역에서 실행된 프로세스는 다음 실행에 제한을 두어야 함

## 해결 방법
* ### Peterson's Algorithm (퍼터슨의 알고리즘)
```java
shared int turn, flag[2];
do {
    flag[me] = true;
    turn =! me;
    while(flag[!me] && turn ==! me);
    critical section;
    flag[me] = false;
    remainder section;
} while(true);
```
* #### 3가지 해결조건을 충족하며, 두 가지 변수만으로 해결 가능함
* #### 프로세스가 많이 몰리게 되면 계속 while문을 대기해야 함 → Busy Waiting (바쁜 대기) 상태

* ### Mutex(상호배제)
  * #### 자원 동시 사용을 막기위한 알고리즘
  * #### lock을 가진 쓰레드만 임계 구역에 접근하게 하고, 작업이 끝나면 lock을 반환 → Locking 매커니즘
* ### [Semaphore (세마포어)](https://github.com/LSH-3016/TIL/blob/main/CS/Operate%20System/Semaphore_VS_Mutex.md)

<hr/>

참고자료
* [Development is difficult](https://hun-developer.tistory.com/36)
* [궁금한 Daniel](https://dduddublog.tistory.com/25)
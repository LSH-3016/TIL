# 캐시(Cache)
#### ▶ 자주 사용하는 데이터나 값을 미리 복사해 놓은 임시 장소
###### 저장 공간이 작고 비용이 비산 대신 빠른 성능을 제공

## 캐시를 사용하면 좋은 경우
* #### 캐시의 접근 시간에 비해 원래 데이터를 접근하는 시간이 오래 걸리는 경우
* #### 값을 다시 계산하는 시간을 절약하고 싶은 경우
* #### 반복적으로 동일한 결과를 돌려주는 경우

## 캐시의 필요성
### Long Tail 법칙
20%의 요구가 시스템 리소스의 대부분을 사용한다는 법칙 → 20%의 기능에 캐시를 이용하여 리소스 사용량은 줄이고, 성능은 향상

## Local Cache
* #### Local 장비 내에서만 사용되는 캐시 (Local 장비의 Resource 이용)
* #### Local에서만 작동하기 떄문에 속도가 빠름
* #### Local에서만 작동하여 다른 서버와 데이터 공유가 어려움

## Global Cache
* #### 여러 서버에서 Cache Server에 접근하여 사용하는 캐시로 분산된 서버에서 데이터를 저장하고 조회할 수 있음
* #### 네트워크를 통해 데이터를 가져오므로, Local Cache에 비해 느림
* #### 별도의 Cache 서버를 이용하기 때문에 서버 간의 데이터 공유가 쉬움

<hr/>

참고자료
* [망나니 개발자](https://mangkyu.tistory.com/69)
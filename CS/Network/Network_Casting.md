# Network Casting
#### 네트워크에서 고유 주소로 메시지를 전송하는 방식

## Unicast
<img src = ../CS_IMG/Unicast.png width="50%" height="50%">

* ### 하나의 목적지로 전송하는 1:1 통신 방식
* ### Lan카드에서 MAC주소를 목적지 MAC주소와 비교하여 동일하지 않으면 프레임을 버림
  * #### LAN카드에서 작업이 일어나기 때문에 CPU나 PC 성능에 영향을 주지 않음
* ### 대량 배포를 유니캐스트로 전송시 대역폭을 많이 사용하여 많은 비용이 발생
  * #### 호스트의 컴퓨터 리소스도 영향을 줄 수 있음

## Broadcast
<img src = ../CS_IMG/Broadcast.png width="50%" height="50%">

* ### 송신된 네트워크에 연결된 모든 호스트에게 전송하는 방식
  * #### 송신자가 자신의 그룹 내의 모든 수신자에게 메시지를 전송
* ### ARP (Address Resolution Protocol)
    #### 통신하고자하는 상대편의 MAC주소를 모를 때 IP를 이용하여 정보를 보내 MAC주소를 알아내는 방식
* ### IPv6에서는 브로드캐스팅이 존재하지 않음
  * #### 해당 네트워크의 모든 수신자가 트래픽을 전달받기 때문에 멀티캐스트를 이용함
* ### 트래픽 증가로인한 CPU 성능의 저하를 야기할 수 있음

## Multicast
<img src = ../CS_IMG/Multicast.png width="50%" height="50%">

* ### 한 번의 전송으로 메시지나 정보를 여러 컴퓨터에 동시 전송하는 1:다 통신 방색
* ### 수신자를 그룹화하여 해당 수신자(라우터)에 유니캐스트 전송 + 그룹내는 브로드캐스트로 전송
  * ### 이때 수신자는 D 클래스 IP주소를 이용
  * ### 이 수신자 IP 주소에서 가입되어 있는 수신자들에게만 정보가 전송

## Anycast
* ### 단일 송신자로부터 가장 가까운 노드로 연결시키는 방식
  * #### 동일 주소 장비 중 가까운 장비 하나만 응답
* ### 트래픽 분산, 네트워크 이중화, DDos 공격의 피해 최소화
* ### DNS에 이용
  * #### 클라이언트가 DNS 요청을 했을 때, 가장 가까운 DNS 서버가 처리하도록하여 응답속도와 안정성을 향상

<hr/>

참고자료
* [build good habit](https://buildgoodhabit.tistory.com/96)
* [개발자를 꿈꾸는 프로그래머](https://jwprogramming.tistory.com/29)
* [easycelsius.log](https://velog.io/@easycelsius/Network-casting)
* [끄적끄적 동커벨](https://donghoson.tistory.com/25)
* [KaKao Tech](https://tech.kakao.com/2014/05/29/anycast/)
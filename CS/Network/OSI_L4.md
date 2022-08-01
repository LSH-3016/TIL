# OSI

### 단계별 스위치
* #### L2 스위치
    OSI Layer 2에 속하는 MAC Address를 참조하여 Switching 하는 장비
    * 자신에게 패킷이 오면 패킷의 목적지를 확인한 후 패킷을 목적지까지 전달
    * 허브보다는 진화한 형태
* #### L3 스위치
    OSI Layer 3에 속하는 IP Address를 참조하여 Switching 하는 장비
  * L2에 비해 발전한 형태
  * IP 주소 기반으로 라우팅을 할 수 있음

# OSI L4 스위치
#### OSI Layer 4에 속하는 IP Adress, TCP/UDP 포트 정보를 참조하여 Switching 하는 장비
## 스위칭 과정
 * ### 브라우저에서 주소 입력
   * 설정된 Local DNS 서버로 DNS Query
   * Local DNS 서버는 주소를 관리하는 DNS 서버에 DNS Query하여 L4의 VIP 주소 획득
 * ### Local DNS는 획득한 VIP 주소를 전송
 * ### 획득한 DNS를 기반으로 L4 VIP로 http요청
 * ### LoadBalancer 장비는 최적의 서비스 서버를 내부 알고리즘을 통하여 선별하고 요청을 전송
 * ### 처리 서버는 작업 결과를 LoadBalancer장비로 전송
 * ### 전달받은 http결과를 LoadBalancer장비를 통해 Client에 전송

 * ## 주요 기능
     * ### 서버 로드밸런싱 기능
         여러 대의 서버를 하나의 서버처럼 동작하게 함으로써, 인터넷 서버의 성능 및 안전성 향상(인터넷의 서버 부하분산 기능)
     * ### 캐시 리다이렉션 기능
         캐싱 서버를 좀 더 효율적으로 사용할 수 있게 하는 것
         ###### `캐시` : 인터넷의 서버와 클라이언트단에서 속도 향상과 WAN 구간의 트래픽 감속를 위해 서버의 데이터를 일시적으로 저장
     * ### 방화벽/VPN 로드 밸런싱 기능
         방화벽이나 VPN 게이트웨이 장비의 성능향상과 안정성 향상을 위한 기능
 * ## 사용 이유
   * ### Load Balancing
     * 하나의 공인 IP로 여러 개의 사설 IP를 사용할 수 있게 함
     * 여러 개의 사설 IP로 트래픽을 나누어 부하를 줄임
   * ### Fail Over (무결성)
     VIP를 이중화(Master & Slave) 시킴으로써 VIP장비의 실패에도 내성을 갖게 함
     ###### `VIP` : L4 스위치가 외부에 보여지는 대표 아이피
 * ## 알고리즘
   * ###  Round Robin
     * L4 하단에 연결된 서버에 순차적으로 접속
     * 일반적인 웹사이트에서 많이 사용
     * 간단하여 부하가 일어나지 않음
   * ### Least Connection
     * L4 하단에 현재 세션 수가 가장 적은 서버에 접속
     * 세션을 고려하기 때문에 약간의 메모리 자원 소비
   * ### Hash
     * 연결되었던 서버의 성립된 세션을 계속 유지해주는 방식
     * 새로운 사용자가 들어오면 사용자 IP 기반으로 Key 값을 생성
   * ### Minimum Misses
     어떤 서버가 서버 그룹에서 제외된 경우 해당 서버에 할당된 사용자에 대해서만 재할당 작업을 함
   * ### Fastest Response Time
     요청에 가장 빠르게 응답하는 Real Server에게 분배

### L4와 L7 스위치
#### 공통점 
▶ 스위치로 들어온 패킷을 적절한 목적지로 전송 (불필요 패킷은 Drop)
#### 차이점 
▶ 패킷을 분석하는 intelligence가 다르며, L7이 보안 기능이 더 강화됨

<hr/>

참고자료
* [Sarc](https://sarc.io/index.php/miscellaneous/758-osi-7-l4-l7)
* [초보개발자 긍.응.성](https://ckddn9496.tistory.com/31)
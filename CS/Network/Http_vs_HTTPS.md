# HTTP(HyperText Transfer Protocol)
* #### 웹 서버/브라우저의 데이터 전송을 위한 응용계층 프로토콜
* #### 80번 포트를 사용
* #### Stateless 프로토콜
  * #### `Stateless` : server에서 client와 server의 동작, 상태정보를 저장하지 않는 형태

### 구조
![](../CS_IMG/HTTP.png)
* #### Method, Path, Version of the Protocol, Headers, Body 등으로 구성
* #### 암호화 되지 않은 평문 데이터를 전송 → 보안 상 문제가 발생

<br/>

# HTTPS(HyperText Transfer Protocol Secure)
* #### HTTP에 데이터 암호화(SSL)가 추가된 프로토콜
  * #### 네트워크 상에서 제 3자가 정보를 볼 수 없도록 암호화 지원
  * #### 대칭키 암호화와 비대칭키 암호화 방식
* #### 443번 포트를 사용

### 대칭키 암호화
* #### 클라이언트와 서버가 동일한 키를 사용하여 암/복호화
* #### 같은 키를 사용하기 때문에 보안성이 취약
* #### 연산 속도가 빠름

### 비대칭키 암호화
* #### 1개의 쌍으로 구성된 공개키와 개인키를 암/복호화에 사용
  * #### 공개키와 개인키 사용
* #### 둘 중 하나가 노출되어도 상관 없어 강력한 보안
* #### 연산 속도가 느림

### HTTPS 연결 과정
<img src = ../CS_IMG/HTTPS.png width="40%" height="400%">

#### ① 클라이언트가 서버로 연결 시도
#### ② 서버가 공개키(인증서)를 브라우저에 전달
#### ③ 브라우저가 인증서의 유효성을 검사하고 세션키를 발급
#### ④ 브라우저가 세션키를 보관, 서버의 공개키로 세션키를 암호화하여 서버로 전송
#### ⑤ 서버에서 개인키로 암호화된 세션키를 복호화
#### ⑥ 클라이언트와 서버가 동일한 세션키를 공유하여 데이터 전달 시 세션키로 암/복호화 진행

<br/>

### HTTPS와 SEO
#### HTTP를 HTTPS로 전환하면 Google의 SEO 효과를 확인할 수 있음
* ### SEO(Search Engine Optimization) : 검색 엔진 최적화
* ### SEO의 효과
  * #### 더 나은 사용자 경험 제공 (Not secure 표시)
  * #### 신뢰성을 기반으로 사이트 체류시간 증가
  * #### HTTP보다 HTTPS가 사이트 로딩 속도가 빠름
    * #### http/1과 http/2의 차이
  * #### HTTPS는 트래픽 관리가 가능하여 확인 및 검증에 유리

<hr/>

참고자료
* [Ascent](https://www.ascentkorea.com/difference-between-http-and-https/)
* [망나니개발자](https://mangkyu.tistory.com/98)
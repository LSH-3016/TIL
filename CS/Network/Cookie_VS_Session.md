## HTTP의 약점
* ### Connectionless 프로토콜
    #### 클라이언트의 요청(Request)에 대한 응답(Response)을 주고 연결을 끊는 특성
* ### Stateless 프로토콜
    #### 요청과 응답이 처리되면 클라이언트와 서버의 통신이 끝나며, 상태 정보를 유지하지 않는 특성

### ※ 위 두가지 약점을 보완하기 위한 것이 `쿠키`와 `세션`

<hr/>

# 쿠키(Cookie)
#### ▶ 웹 서버가 브라우저에게 지시하여 사용자의 로컬 컴퓨터에 파일 또는 메모리에 저장하는 작은 기록 정보 파일

## 쿠키의 특징
* #### HTTP Response Header에 Set-Cookie 속성을 이용하여 클라이언트에 쿠키를 제공
* #### 클라이언트의 상태 정보를 로컬에 저장하고 요청할 때 참조
* #### 구성요소
  * `Name` : 이름
  * `Value` : 쿠키에 저장된 값
  * `Expires` : 쿠키의 삭제 시기 결정
  * `Domain` : 쿠키가 사용되는 도메인
  * `Path` : 쿠키를 반환할 경로를 설정
  * `Secure` : 보안 연결 설정
  * `HttpOnly` : Http외에 다른 통신 사용 가능 설정
* ### 클라이언트에 최대 300까지 쿠키를 저장할 수 있음
* ### 서버 도메인 하나당 최대 20까지만 쿠키를 저장할 수 있음
* ### 하나의 쿠키는 최대 4KB까지 저장할 수 있음

## 쿠키 종류
* ### Session Cookie
  #### 만료 날짜/시간을 지정하지 않으면 메모리에만 저장되며, 현재 세션이 끝날 때 삭제
* ### Persistent Cookie
  #### 만료 날짜/시간을 지정하면 파일로 저장되며, 브라우저 (프로세스)가 종료되어도 쿠키가 남아있음
* ### Secure Cookie
  #### HTTPS에서만 사용하는 암호화 쿠키
* ### Third-Party Cookie
  #### 방문한 도메인과 다른 도메인의 쿠키 (광고 베너 등)

## 쿠키 프로세스
![](../CS_IMG/Cookie_Process.png)
### ① 클라이언트가 페이지를 요청
### ② 웹 서버에서 쿠키를 생성
### ③ HTTP 헤더에 쿠키를 포함 시켜 응답
### ④ 브라우저가 종료되어도 만료기간이 지정되어있다면 클라이언트에서 보관 (로컬 PC에 저장)
### ⑤ 같은 요청을 할 경우 HTTP헤더에 쿠키를 함께 보냄
### ⑥ 서버에서 쿠키를 읽어 이전 상태 정보를 변경 할 필요가 있을 때 쿠키를 업데이트 하여 변경된 쿠키를 HTTP헤더에 포함시켜 응답

## 쿠키의 단점
* ### 쿠키에 대한 정보를 매 헤더에 추가하여 보내기 때문에 상당한 트래픽을 발생
* ### 결제정보 등을 쿠키에 저장하였을 때 쿠키가 유출되면 보안 문제가 발생

<hr/>

# 세션 (Seesion)
### ▶ 서버에 클라이언트의 상태 정보를 저장하는 기술

# 세션의 특징
* #### 사용자에 대한 정보를 서버에 두어 쿠키보다 보안에 좋지만, 동시 접속시 과부하가 일어남
* #### 접속 시간에 제한을 두어 일정 시간 응답이 없을 경우 정보가 유지되지 않게 설정 가능
* #### 사용자 정보를 서버 측에서 관리
* #### 웹 서버에 클라이언트에 대한 정보를 저장하고, 클라이언트에게 세션아이디를 부여하여 구분

## 세션 프로세스
### ① 클라이언트가 서버에 페이지를 요청
### ② 세션에 클라이언트에 대한 데이터를 저장, 세션 ID를 발급
###### (클라이언트는 발급 받은 세션 아이디를 쿠키로 저장)
### ③ 클라이언트가 서버에 요청을 할 때, 세션 ID를 포함하여 서버에 전달
### ④ 서버에서 세션 ID를 전달 받아 저장되어 있는 해당 클라이언트의 정보를 가져와 요청을 처리하여 클라이언트에게 응답

<hr/>

# 쿠키 VS 세션

|      |쿠키|세션|
|:----:|:---:|:----:|
| 저장위치 |클라이언트|웹서버|
|저장형식|Text|Object|
|만료시점|쿠키 저장시 설정<br/>(브라우저가 종료되어도 만료시점이 지나지 않으면 자동삭제되지 않음|브라우저 종료시 삭제<br/>(기간 지정 가능)|
|사용하는 자원(리소스)|클라이언트 리소스|웹 서버 리소스|
|용량제한|총 300개, 하나의 도메인 당 20개, 하나의 쿠키당 4KB|서버가 허용하는 한 제한 없음|
|속도|세션보다 빠름|쿠키보다 느림|
|보안|정보 노출 가능성 있음|쿠키를 개선하여 더 좋음|

<hr/>

참고자료
* [기본기를 쌓는 정아마추어 코딩 블로그](https://jeong-pro.tistory.com/80)
* [Nesoy Blog](https://nesoy.github.io/articles/2017-03/Session-Cookie)
* [hahahoho5915](https://hahahoho5915.tistory.com/32)
# REST(Representational State Transfer)
### ▶ 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것
* ### 네트워크상에서 Client와 Server 사이의 통신 방식 중 하나
* ### HTTP URL을 통해 자원을 명시하고, `HTTP Method`를 통해 해당 자원에 대한 `CRUD Operation`을 적용하는 것
    ### `CRUD Operation`
    기본적인 데이터 처리 기능인 `Create`, `Read`, `Update`, `Delete`를 묶어서 일컫는 말
  * `create` 데이터 생성 (POST)
  * `Read` : 데이터 조회 (GET)
  * `Update` : 데이터 수정 (PUT)
  * `Delete` : 데이터 삭제(DELETE)
  * `Head` : header 정보 조회(HEAD)

### REST 구성 요소
#### * `자원(Resource)` : HTTP URL
#### * `행위(Verb)` : HTTP Method
#### * `표현(Representation of Resource)` : HTTP Message Pay Load

### REST의 특징
#### * Server-Client(서버-클라이언트 구조)
###### 자원이 있는 쪽이 Server, 자원을 요청하는 쪽이 Client
#### * Stateless(무상태)
#### * Cacheable(캐시 처리 가능)
#### * Layered System(계층화)
#### * Uniform Interface(인터페이스 일관성)

### 장점
* HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구출할 필요 X
* HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용 가능
* 서버와 클라이언트의 역할을 명확하게 분리

### 단점
* 표준이 자체에 존재하지 않아 정의가 필요
* 사용할 수 있는 메소드가 4가지 뿐임

<hr/>

# REST API
### ▶ REST 기반으로 서비스 API를 구현하는 것
* ### 사내 시스템들도 REST 기반으로 시스템을 분산해 확장성과 재사용성을 높여 유지보수 및 운용을 편리하게 할 수 있음
* ### REST는 HTTP 표준을 기반으로 구현하므로, HTTP를 지원하는 프로그램 언어로 클라이언트, 서버를 구현할 수 있음

## 설계 규칙
#### * 슬래시 구분자는 계층 관계를 나타내는데 사용
#### * URL 마지막에 슬래시를 포함하지 않음
#### * 하이픈은 URL 가독성을 높이는데 사용
#### * 밑줄은 URL에 사용하지 않음
#### * URL 경로에는 소문자가 적합
#### * 파일확장자는 URL에 포함하지 않음

## ★ 응답상태 코드
* ### 1○○ : 전송 프로토콜 수준의 정보 교환
* ### 2○○ : 클라이언트 요청이 성공적으로 수행
* ### 3○○ : 클라이언트는 요청을 완료하기 위해 추가적인 행동이 필요
* ### 4○○ : 클라이언트의 잘못된 요청
* ### 5○○ : 서버쪽 오류

<hr/>

# RESTful
### ▶ REST의 원리를 따르는 시스템을 의미
###### REST API의 설계 규칙을 올바르게 지킨 시스템만을 RESTful이라고 칭함

## RESTful의 목적
* ### 이해하기 쉽고 사용하기 쉬운 REST API를 만드는 것
* ### 일관적인 컨벤션을 통한 API의 이해도 및 호환성을 높이는 것
###### 성능 향상에 목적을 두지 않기 때문에 성능이 중요한 상화에서는 굳이 RESTful한 API를 구현할 필요 없음

<hr/>

참고자료
* [hanamon](https://hanamon.kr/rest-api/)
* [히진쓰의 서버사이드 기술 블로그](https://khj93.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-REST-API%EB%9E%80-REST-RESTful%EC%9D%B4%EB%9E%80)
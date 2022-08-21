# SQL Injection
* #### 악의적인 사용자가 보안상의 취약점을 이용하여, 임의의 SQL문을 주입하고 실행되게 하여, 데이터베이스가 비정상적인 동작을 하도록 조작하는 행위
* #### 대부분 클라이언트가 입력한 데이터를 제대로 필터링 하지 못하는 경우에 발생
* #### OWASP TOP 10 중 첫 번째에 속해 있으며, 공격이 비교적 쉬운 편이고, 공격에 성공할 경우 큰 피해를 입힐 수 있음
    #### `OWASP` : 오픈소스 웹 애플리케이션 보안 프로젝트, 10대 웹 애플리케이션 취약점

<br/>

## 공격 종류
* ## Error based SQL Injection
    * #### 논리적 에러를 이용한 방법
    * #### 에러가 발생되는 사이트에서는 에러 정보들을 이용하여 DB 및 쿼리 구조 등의 정보를 추측 가능
    * #### 공격 대상 : `SELECT * FROM Users WHERE id = 'INPUT1' AND password = 'INPUT2'`
    * #### 공격 SQL : `SELECT * FROM Users WHERE id = '' OR 1=1 -- ' AND password = 'INPUT2'`
    ![](../CS_IMG/Error_based.png)
    * #### Users 테이블의 모든 정보를 조회하여 관리자 계정으로 로그인 (관리자 계정 탈취)
* ##  Union based SQL Injection
  * #### Union 명령어를 이용한 SQL Injection
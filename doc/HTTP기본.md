# 모든 것이 HTTP
> HTTP (HyperText Transfer Protocol)
* HTTP 메시지에 모든 것을 전송
* 거의 모든 형태의 데이터 전송 가능
	* HTML, TEXT, IMAGE, 음성, 영상, 파일, JSON, XML(API)
* 서버간에 데이터를 주고 받을 때도 대부분 HTTP 사용

### HTTP 역사 
* HTTP/0.9 1991년: GET 메서드만 지원, HTTP 헤더 X
* HTTP/1.0 1996년: 메서드, HTTP 헤더 추가
* HTTP/1.1 1997년: 가장 많이 사용, 모든 기능이 거의 다 들어가있음, 우리에게 가장 중요한 버전
* HTTP/2 2015년 : 성능개선
* HTTP/3 진행 중 : TCP 대신에 UDP 사용, 성능개선

### 기반 프로토콜 
* TCP : HTTP/1.1, HTTP/2
* UDP : HTTP/3
* 현재 HTTP/1.1 주로 사용
	* HTTP/2, HTTP3도 점점 증가 

### HTTP 특징
* 클라이언트 서버 구조
* 무상태 프로토콜(스테이스리스), 비연결성
* HTTP 메시지
* 단순함, 확장 가능

# 클라이언트 서버 구조 
* Request Response 구조 
* 클라이언트는 서버에 요청을 보내고, 응답을 대기
* 서버가 요청에 대한 결과를 만들어서 응답

# Stateless
* 서버가 클라이언트의 상태를 유지하지 않음.
* 상태를 저장하고 있지 않으면 중간에 서버가 장애가나도, 다른 서버에 요청하여 응답받을 수 있음.
* 스케일 아웃 - 수평 확장 유리 
* 무든 것을 무상태로 설계할 수 있는 경우도 있고 없는 경우도 있음
	* 무상태 - 로그인이 필요 없는 단순한 서비스 소개 화면
	* 상태유지 - 로그인
* 일반적으로 브라우저 쿠키와 서버세션 등을 사용해서 상태 유지
* 상태 유지는 최소한만 사용
* 전송 데이터 량이 많다는 것이 단점.

# 비연결성
* HTTP는 기본이 연결을 유지하지 않는 모델
* 일반적으로 초 단위의 이하의 빠른 속도로 응답
* 1시간동안 수천명이 서비스를 사용해도 실제 서버에서 동시에 처리하는 요청은 수십개 이하로 매우 작음
* 서버 자원을 매우 효율적으로 사용할 수 있음

### 비연결성 단점
* TCP/IP 연결을 새로 맺어야함 - 3way handshake 시간 추가 
* 웹 브라우저로 사이트를 요청하면 HTML 뿐만 아니라 자바스크립트, css 추가 이미지 등 수많은 자원이 함께 다운로드
* 지금은 HTTP 지속연결(persistent connections)로 문제 해결
	* 서버와 클라이언트 간에 하나의 TCP/IP 연결을 통해 여러개의 Object 전송 
	* HTTP 1.1 에서부터 사용
* HTTP/2, HTTP/3에서 더 많은 최적화 


# HTTP 메시지 

* HTTP 메시지 구조 
	* start-line 시작라인
	* header 헤더
	* empty line 공백라인 (CRLF)
	* message body

* HTTP 요청 메시지 예시 
	* GET /search?q=hello&h1=ko HTTP/1.1			(start-line)
	* Host: www.google.com 							(header 헤더)
	* 												(공백라인)
	*												(message body)

* HTTP 응답 메시지 
	* HTTP/1.1 200 OK								(start-line)
	* Content-type: text/html;charset=UTF-8			(header 헤더)
	* Content-Length: 3423							(header 헤더)
	* 												(공백라인)
	* <html><body></body></html>					(message body)


### 시작 라인 

* 요청 메시지 
	* start-line = request-line
	* GET /search?q=hello&h1=ko HTTP/1.1
		* HTTP 메서드 (GET, POST, DELETE, PUT)
		* 요청 대상 (/search?q=hello&h1=ko) : /절대경로?쿼리 
		* HTTP Version

* 응답 메시지 
	* start-line = status-line
	* HTTP/1.1 200 OK
		* HTTP 버전
		* HTTP 상태코드 : 요청 성공, 실패를 나타냄
			* 200 : 성공
			* 400 : 클라이언트 요청 오류
			* 500 : 서버 내부 오류


### HTTP 헤더 

* HTTP 전송에 필요한 모든 부가 정보
	* 예) 메시지 바디의 내용, 메시지 바디의 크기, 압축, 인증, 요청 클라이어늩 정보, 서버 애플리케이션 정보, 캐시 관리 정보
* 표준 헤더가 너무 많음.
* 필요 시 임의의 헤더 추가 가능 

### HTTP 메시지 바디

* 실제 전송할 데이터 
* HTML 문서, 이미지, 영상, JSON 등등  byte로 표현할 수 있는 모든 데이터 전송 가능
	
















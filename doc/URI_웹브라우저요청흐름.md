# URI (Uniform Resource Identifier) : URL + URN
* Uniform : 리소스를 식별하는 통일된 방식
* Resource : 자원, URI로 식별할 수 있는 모든 것 (제한 없음) 
* Identifier : 다른 항목과 구분하는데 필요한 정보 


* URL (Resource Locator) : 리소스가 있는 위치를 지정
* URN (Resource Name) : 리소스에 이름을 부여 
* URN 이름만으로 실제 리소스를 찾을 수 있는 방법이 보편화 되어있지 않음. 
* URI와 URL을 같은 의미로 보면 됨.

### URL schema
* schema://[userinfo@]host[:port][/path][?query][#fragment]
	* https://www.google.com:443/search?q=hello&hi=ko
	* https
* 주로 프로토콜 사용
	* 프로토콜 : 어떤 방식으로 자원에 접근할 것인가 하는 약속 규칙. 예) https, http, ftp 등등
* http는 80포트, https는 443 포트를 주로 사용, 포트는 생략 가능
* https는 http에 보안 추가 (HTTP Secure)

### URL userinfo
* schema://[userinfo@]host[:port][/path][?query][#fragment]
* url 에 사용자 인증 정보를 사용해야 할 때 사용하는데 거의 안씀

### URL host
* schema://[userinfo@]host[:port][/path][?query][#fragment]
	* https://www.google.com:443/search?q=hello&hi=ko
	* www.google.com
* 호스트명
* 도메인명 또는 IP 주소를 직접 사용 가능

### URL port
* schema://[userinfo@]host[:port][/path][?query][#fragment]
	* https://www.google.com:443/search?q=hello&hi=ko
	* 443
* http는 80포트, https는 443 포트를 주로 사용, 포트는 생략 가능

### URL path
* schema://[userinfo@]host[:port][/path][?query][#fragment]
	* https://www.google.com:443/search?q=hello&hi=ko
	* search
* 리소스 경로(path), 계층적 구조 
	* /home/file1.jpg
	* /members
	* /members/100, /items/iphone12

### URL query
* schema://[userinfo@]host[:port][/path][?query][#fragment]
	* https://www.google.com:443/search?q=hello&hi=ko
	* q=hello&hi=ko
* key=value 형태
* ?로 시작, &로 추가 가능 
* query parameter, query string 등으로 불림, 웹서버에 제공하는 파라미터, 문자형태

### URL fragment
* schema://[userinfo@]host[:port][/path][?query][#fragment]
* html 내부 북마크 등에 사용
* 서버에 전송하는 정보 아님

# 웹 브라우저 요청 흐름

* DNS 조회 -> IP 확인
* HTTP 요청 메시지 생성 
* HTTP 메시지 전송, 요청 패킷 전송
* 요청 패킷 도착 후 데이터 확인
* 요청에 대한 결과 데이터 생성 후 HTTP 응답 메시지 생성
* HTTP 응답 메시지 전송 
* 받은 데이터를 확인하여 클라이언트에서 작업. 







[ Service01 ]
	|-> Dependency
	|	|-> Actuator
	|
	|-> pom.xml
	|	|-> management: ... 추가
	|
	| -----------------------------------------------
	|-> Service01Controller2 추가
	|	|-> @Controller
	|	|-> return "page";
	|
	|-> page.html
		|-> index.html에서의 링크 2개 복사

[ GatewayServer ]
	|-> application.yml
		|-> routes: 에 actuator 관련 코드 추가
		|	|-> 그래야 localhost:8765/actuator/... 로 접속 가능해짐
		|-----------------------------------------------------------------------
		|-> routes: 에 Service01/tiger2 관련 코드 추가


***   localhost:8765/tiger2   &   localhost:8765/actuator/circuitbreakers
		|-> 두 개를 동시에 띄워놓고 보기
			|-> tiger2에서 버튼 1개 클릭하고,  actuator/circuitbreakers 새로고침해서 변하는거 보기
										|-> 특히 "state"관련해서 보기

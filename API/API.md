## API란 무엇인가?
> API는 정의 및 프로토콜의 집합을 사용하여 두 소프트웨어 구성 요소가 서로 통신할 수 있게 하는 메커니즘, <br />
> Ex) 기상청의 소프트웨어 시스템에는 일일 기상 데이터가 있다 -> 휴대폰의 날씨 앱은 API를 통해 이 시스템과 '대화' 하여 휴대폰에 매일 최신 정보를 보여준다


## API의 의미는 무엇인가?
> API는 Application Programming Interface(애플리케이션 프로그램 인터페이스)의 줄임말입니다. API의 맥락에서 애플리케이션이라는 단어는 고유한 기능을 가진 모든 소프트웨어를 나타냅니다. <br />
> 인터페이스는 두 애플리케이션 간의 서비스 계약이라고 할 수 있습니다. <br />
> 이 계약은 요청과 응답을 사용하여 두 애플리케이션이 서로 통신하는 방법을 정의합니다. API 문서에는 개발자가 이러한 요청과 응답을 구성하는 방법에 대한 정보가 들어 있습니다.


## API는 어떻게 작동하는가?
API 아케텍처는 일반적으로 클라이언트와 서버 측면에서 설명됩니다. 요청을 보내는 애플리케이션을 **클라이언트**라고 하고 응답을 보내는 애플리케이션을 **서버**라고 한다.
`기상청 DB = 서버, 모바일 앱 = 클라이언트`

API가 생성된 시기와 이유에 따라 API는 네 가지 방식으로 작동 할수 있다.

### SOAP API
>이 API는 단순 객체 접근 프로토콜을 사용함, 클라이트와 서버는 XML을 사용하여 메세지를 교환한다 `과거에 사용이 많이 되어 현재로써는 유연성이 떨어짐`


### RPC API
> 이 API를 원격 프로시저 호출이라고 한다. <br />
> 클라이언트가 서버에서 함수나 프로시저를 완료하면 서버가 출력을 클라이언트로 다시 전송한다.

### Websocket API
> Websocket API는 JSON 객체를 사용하여 데이터를 전달하는 최신 웹 API 개발이다. <br />
> Websocket API는 클라이언트 앱과 서버간의 **양방향 통신**을 지원한다. <br />
> 서버가 연결된 클라이언트에 콜백 메세지를 전송할 수 있어 REST API보다 효율적이다.
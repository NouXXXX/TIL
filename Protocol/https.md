# HTTPS

먼저, HTTP란 HyperText Transfer Protocol의 약자로써, 풀어서 해석하면 ***하이퍼텍스트(HyperText)를 전송(Transfer)하기 위해서 사용하는 통신 규약(Protocol)이다.

HTTP 서버는 기본 포트인 80번 포트에서 서비스 대기중이며, 클라이어느(웹 브라우저)가 TCP 80 포트를 사용해 연결하면 서버는 요청에 응답하면서 자료를 전송한다.
`HTTP는 정보를 텍스트로 주고 받기 때문에 네트워크에서 전송 신호를 인터셉트 하는 경우 원하지 않는 데이터 유출이 발행 할수 있다` 따라서 이러한 보안 문제를 해결하기 위해 나온 프로토콜이 `HTTP에 S(Secure Socket)이 추가된 HTTP이다.`

![](https://www.x-cart.com/wp-content/uploads/2017/02/http_to_https-1.jpg)

> HTTPS는 기본 골격이나 사용 목적 등은 HTTP와 거의 동일하지만, 데이터를 주고 받는 과정에 '보안'이 추가 되어있다. <br />
>> HTTPS는 암호화한 키가 그 페이지를 보는 특정 사용자에게만 알려지도록 한다. HTTPS는 SSL이나 TLS 프로토콜을 통해 세션 데이터를 암호화하며, 기본 TCP/IP 포트는 443이고, SSL 프로토콜 위에서 HTTPS 프로토콜이 동작한다.

> **TLS** <br/>
> Transport Layer Security의 줄임말. 과거 SSL에서 발전하여 이름이 변경되었다. 하지만 아직도 SSL이란 명칭이 많이 사용 되고 있다. <br />
> Transport Layer Security는 전송 계층 보안이라는 뜻이다. 전송 계층 보안은 컴퓨터 네트워크에 통신 보안을 제공 하기 위해 설계된 암호 규약이다.

## 암호화 방식

`공개키 암호화 방식과 공개키의 느리다는 단점을 보완한 대칭키 암호화 방식을 함께 사용한다. 공개키 방식으로 대칭키를 전달하고, 서로 공유된 대칭키를 가지고 통신하게 된다.`


### 공개키 방식
* A키로 암호화 하면 B키로 복호화 할 수 있다.
* B키로 암호화 하면 A키로 복호화 할 수 있다.
* 둘 중 하나를 비공개키(Primary Key) 혹은 개인키라 부르며, 이는 자신만 가지고 있고 공유되지 않는다.
* 나머지 하나를 공개키(Public Key)라고 부르며 타인에게 제공한다. 공개키는 유출이 되어도 비공개키를 모르면 복호화 할 수 없기 때문에 안전하다.

![](https://raonctf.com/static/essential/images/crypto/crypto_asymmetric_key_01.jpg)
![](https://blog.kakaocdn.net/dn/BWB42/btrgYkPJ7ja/6VY47rdHIMu9Kcs36adBF0/img.png)

### 대칭키 방식
* 동일한 키로 암호화, 복호화가 가능하다. 
* 대칭키는 매번 랜덤으로 생성되어 누출이되어도 다음에 사용할 때는 다른 키가 사용되기 때문에 안전하다.
* 공개키보다 빠르게 통신할 수 있다.

이러한 SSL 방식을 적용하려면 인증서를 발급받아 서버에 적용시켜야 한다. 인증서는 사용자가 접속한 서버가 우리가 의도한 서버가 맞는지를 보장하는 역할을 한다. 인증서를 발급하는 기관을 CA(Certificate Authority)라고 부른다. 공인인증기관의 경우 웹 브라우저는 미리 CA 리스트와 함께 각 CA의 공개키를 알고 있다.

> ### CA(Certificate Authority)란?
> certification authority (CA)는 공개키와 공개 DNS명(ex)www.example.com)의 연결을 보장하는 기관이다.
> 예를 들어 클라이언트가 `www.example.com`의 공개키가 이 공개키인지 어떻게 알 수 있는가?
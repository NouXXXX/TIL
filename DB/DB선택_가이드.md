## 1. Key-value Database

> 데이터를 `Key, Value` 형태로 저장하는 데이터베이스이다. <br />
> 예를 들어 이름과 나이를 저장하고 싶으면 아래와 같이 기록하면 된다.
> ![](https://i.gyazo.com/57144de55940300d8c9eb47c95bf8b48.png) <br />
> 사실 너무 간단해서 실용성은 그다지 크지 않다. <br/>
> 서브용 DB로 많이 사용된다. 그런데 좀 특수한 기능을 가진 데이터베이스 하나가 있는데 바로 `redis`라는 것이다. <br />
> ![](https://upload.wikimedia.org/wikipedia/en/6/6b/Redis_Logo.svg) <br />
> `redis`도 똑같이 `key, Value` 형태로 데이터를 저장할수 있다. <br />
> `redis`는 되게 많이 쓰인다. 왜냐하면 데이터를 하드디스크에 저장하는 것이 아니라 일차적으로 `RAM`에다가 저장을 해준다. 
> 왜냐하면 `RAM`이 하드디크스보단 몇 백 배 빠르기 때문이다.
> ![](https://i.gyazo.com/92f93564c65e785d1331368b4c1ec0c3.png) <br/>
> 그래서 이 `redis`를 어떻게 활용을 하냐면 메인 DB를 하나두고 그다음 고객들이 자주 사용하는 데이터들을 `redis`로 추가로 복사를 해둔다. <br />
> 그다음에 그 데이터를 요청하면 `메인 DB`에서 보여주는것이 아니라 `redis`에서 꺼내서 보여주는 경우가 있고 그러면 더 빠른 서비스를 만들수 있다.
> ![](https://i.gyazo.com/e87ed043ab3cc048ca04a1131bdc94ab.png) <br />
> 따라서 `Key-value Database`는 **자주쓰는 데이터 캐싱, 채팅을 위한 pub/sub, 영상 스트리밍, 로그인기록저장 등등**에 사용이 된다.

## 2. Relational Database

> 엑셀처럼 생긴 데이터베이스이다. <br/>
> 대표적으론 
> ![](https://i.gyazo.com/ed656fb82505689b790ecf1cb985de6d.png)
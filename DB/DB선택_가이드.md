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
> ![](https://i.gyazo.com/ed656fb82505689b790ecf1cb985de6d.png) <br/>
> 대표적으론 `MariaDB, MySQL, ORACLE, PostgreSQL 등등`이 있다.<br/>
> ![](https://i.gyazo.com/40bf8d72bfb6bc0bc8eb8662ff7bfe47.png) <br />
> 또한 이 관계형 DB는 다양한 곳에서 사용될 수 있어서 DB 점유율에서도 높은 위치에 있다. <br />
> ![](https://cdn-icons-png.flaticon.com/512/4492/4492311.png) <br/>
> 그리고 이러한 관계형 DB는 `SQL(Structured Query Language)`이라는 DB 문법을 사용해야한다. <br/>
> 그런데 이 `SQL`이라는 걸 사용하게 되면 `데이터 정규화`라는 것을 자주보게 되는데 `데이터 정규화는 중복이 되는 내용은 다른 테이블로 빼서 중복을 제거하는 것이다.` <br/>
> 또한 `데이터 정규화는 입출력을 할때 출력문법이 많이 복잡해지게 되는 단점이 있다.` <br/>
> 또한 기본적으로 `트렌젝션 (ACID Transaction)기능`이 있어서 돈을 거래하는 기능을 만들때 안전하게 구현이 가능하다. <br/>
> ![](https://www.databricks.com/wp-content/uploads/2021/02/delta-lake-1-min.png) <br/>
> 따라서 `입출력의 속도보단 정확도가 더 중요한 서비스라면 일반적으로 관계형 DB를 사용하는 경우가 많다.`
> > ### 추가 설명
> > 많은 사람들이 관계형 DB의 이름 때문에 `관계`를 더 잘 표현한다라고 생각하는데 사실은 수학용어중에 행렬을 배울 때 사용하는 `relation`에서 기인되었다. <br/>
> > ![](https://i.gyazo.com/6090d8a1d58d28d01baf54203e4b0998.png) <br/>
> > **따라서 Relational Database는 관계를 중점으로 다루기엔 어려운점이 많다. 만약 이 `관계`를 주로 DB에 저장하고 싶다면 `Graph Database`를 사용해야 한다.**

## 3. Graph Database

> 위에서 말했듯이 `관계`를 주로 DB에 저장하고 싶다면 사용하는 DB이다.<br/>
> 대표적으로는 `*Sparsity, neo4j, OrientDB, ArangoDB`등이 있다. <br/>
> 그중에서도 가장많이 사용하는 `neo4j`에 대해 알아보자 <br/>
> ![](https://upload.wikimedia.org/wikipedia/commons/e/e5/Neo4j-logo_color.png) <br/>
> `neo4j`는 아래와 같이 구성이 된다.
> 
> `node`라는 것을 만들고 이 `node`라는 것 안에 데이터들을 저장할 수 있는데 여기서 중요한건 `node`끼리 어떤 관계인지 기록을 해둘 수 있다. <br/>
> 또한 이러한 Graph Database를 입출력 할때는 GQL(Graph Query Language)를 사용해야 한다. <br/>
> ![](https://user-images.githubusercontent.com/38887077/75741240-f5ba2d80-5d44-11ea-80f6-f44d39fff43a.png) <br/>
> 이걸 사용하게 되면 방향, 관계 이런 것들이 표현 가능한데 기업에서는 이러한 `Graph Database`를 대표적으로는 `비행기 노선, SNS 친구관계, 코로나전염맵, 추천 서비스 등`에 사용을 많이한다.

## 4. Document Database

> `Graph Database`처럼 특수한 케이스 말고 일반적인 상황에서 사용하는 DB를 사용하고 싶다면 `Relational Database`를 사용하면 되는데 `Relational Database`보다 좀더 자유로운 DB를 사용하고 싶다면 `Document Database`를 사용하면 된다. <br/>
> 대표적으로는 `mongoDB, CouchDB, Cloud Firestore등`이 있다. <br/>
> 이 DB들의 원리에 대해서 알아보자 `Document Database`는 `collection`이라는 폴더를 하나 만들고 그 안에 `document`라는 것을 생성해서 `document` 안에 JSON 형태로 데이터를 저장 할 수 있게 되어있다. <br/>
> ![](https://i.gyazo.com/6785f50be7579aaef4b9dbdbc2348e2c.png) <br/>
> 이걸 사용하면 어떤 데이터를 저장하게 될지 미리 `정의`해놓을 필요가 없고 갑자기 구조가 바뀌어도 에러가 발생하지 않는다. 가장 큰 특징은 중복된 데이터를 제거하지 않는다. 한마디로 정규화를 하지 않는다. 따라서 데이터 입출력문이 메우 간단하다. <br/>
> 또한 데이터 분산처리를 매우 잘해주어서 `SNS, 실시간 채팅, 게시판, 온라인게임 등`에 주로 활용하는 경우가 있다. <br/>
> ![](https://i.gyazo.com/b503e5a496622bb85c138626625329b5.jpg) <br/>
> 다만 분산처리를 하게 되면 `일관성, 정확도`가 떨어질수 있다.

## 5. Column-family Database

> 만약 관계형 DB처럼(like excel) 사용하고 싶은데 좀 더 유연하게 사용하고 싶다 라고 하면 `Column-family Database`를 쓰면 된다.<br/>
> 대표적으로는 `cassandra, APACHE HBASE, Google Cloud Bigtable 등`이 있다. <br/>
> 이러한 DB도 똑같이 `table`을 하나 만들고 `row`를 만들고 `row`에 `column`을 만들어서 데이터를 넣을 수 있다. <br/>
> ![](https://i.gyazo.com/6aaec5105dd003e1eae334caabfb5b87.png) <br/>
> 다만 이러한 DB에 입출력을 하기 위해선 `SQL`이 아니라 그 회사에서 만든 언어를 사용해야 한다. cassandra의 경우에는 CQL(Cassandra Query Language)를 사용한다. (사실 SQL이랑 큰차이 없음) <br/>
> ![](https://cdn.educba.com/academy/wp-content/uploads/2019/11/Cassandra-Query-Language.png)<br/>
> 그리고 이러한 DB들은 `정규화없이 쓰는게 일반적`이다. 따라서 입출력문이 쉽고 `복제,분산 처리`를 잘한다.<br/>
> `많은 입출력`을 감당해야 하는 서비스에 사용된다. (복제해놓으면 단점 : 데이터 일관성 부족) <br/>
> 또한 데이터를 저장할때 `시간 기록을 쉽게 해주는 기능`이 있어서 많이 사용된다 (대표적으론 Netflix)

## 6. Search Engine

> 검색용 `index`를 보관하기 위한 DB도 있다. `elastic, Amazon CloudSearch, Google Cloud Search`가 대표적이다. <br/>
> 검색용 DB라고 해도 `일반적인 DB로 사용이 가능`하다. 그래도 `index 보관에 특화`되어 있어 `index`보관용으로 주로 사용된다. <br/>
> `index`란 `빠른 검색을 도와주는 목차와 같은 것`입니다.<br/>
> ![](https://i.gyazo.com/e1c374990deda8550babeb7e7b0a2528.png) <br/>
> 원리는 평소에 쓰던 `DB에서 데이터를 뽑아서 입력`을 하면 `index`를 생성하고 보관해주는 역할을 한다. <br/>
> 따라서 검색 요청이 들어오면 `index`를 이용해서 되게 쉽게 자료 검색을 도와준다.<br/>
> 또한 `Search Engine`을 사용하면 `실시간 검색어, 추천 검색어, 검색어 오타교정` 서비스를 만들기 쉽다.

## 📌 요약
> ### 일반적인 용도로는
> - Relational Database
> - Document Database
> ---
> ### 입출력이 매우 잦으면
> - Document Database가 일반적
> ---
> ### 정확도와 일관성이 중요하면
> - Relational Database가 일반적 (확장 방법에 따라 아닐 수도 있음)

### 📎 참고 자료
> https://www.youtube.com/watch?v=ZVuHZ2Fjkl4

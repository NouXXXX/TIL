# Index가 무엇인가?

![](https://i.gyazo.com/cd01caf7c86f020eb268aadc0f365702.png)

> ### 여기서 age가 20인 데이터를 찾으라고 컴퓨터에게 시켜보자
> * 컴퓨터 : 모든 행을 다 하나씩 찾아본다
> -> 더 많은 행이 있으면 더 많이 검사하기 떄문에 컴퓨터가 느려진다.
> -> 이걸 해결할수 있는 것이 바로 `index`이다.

### Index
![](https://i.gyazo.com/d9388974c4083e3250d9a35b48fa4094.png)
> 우리는 더 빠르게 원하는 행을 찾기 위해선 범위를 물어보는것이 좋다.(ex. 50보다 큰가요? 75보다 작은가요?) 그러기 위해서 전제조건이 하나 필요한데 <br />
> 바로 위 그림처럼 정렬된 컬럼사본이다. 그걸 우리는 `index`라고 부른다. (간단하게 설명하면 `정렬된 컬럼` = `index`)<br />
> 이게 `index`이다. 이렇게 끝나면 재미 없으니 index를 실제 어떻게 구성하는지도 알아보자.

## Index는 어떻게 구성이 되어 사용되는가?
![](https://i.gyazo.com/1ebc9296aeac39835719517516a6f820.png)
> 이렇게 데이터베이스의 자료들이 있다고 생각해보자, 실제로 데이터베이스는 이렇게 정렬되지 않은 자료들을 `Tree(나무)`형태로 데이터를 배치하고 정렬한다.

![](https://i.gyazo.com/c2adb1953a2f7037bd5d48571be8a058.png)
> Tree 구조로 배치를 해도 전처럼 `절반식 소거하면서 자료를 찾기`가 가능하다.

![](https://i.gyazo.com/e75d22cf6f4c7b7de1e7606242fe3aeb.png)

### Binary Search Tree
![](https://i.gyazo.com/e1cd7869166585b639d47677e7e215a5.png)
> 실제 데이터베이스에서도 `index`를 만들라고 요청을 하면 Tree 형태로 그리고 이렇게 생긴 Tree를 전문용어로 `Binary Search Tree`라고 부른다. <br />
> 그리고 이 `Binary Search Tree`의 성능을 좀더 강화 시킨것이 바로 `B-tree`라고 부른다.

### B-tree
![](https://i.gyazo.com/26d8924ea289b5575c4e57bdd782f224.png)
> 이렇게 해서 사용하게 되면 `Binary Search Tree`에선 2번의 이동으로 1~7까지 검색이 가능했는데 1부터 13 까지 찾을수 있게된다. <br/>
> 그리고 아직 이 `B-tree`의 성능을 더 강화 시킬수 있는데 그것을 바로 `B+tree`라고 부른다 그리고 실제 데이터베이스에선 `B-tree` 말고 `B+tree`를 많이 사용한다.

### B+tree
![](https://i.gyazo.com/4b01b34011b62dfe87bb237e101bd193.png)
> B+tree의 특징은 맨 밑 `node`에만 데이터를 보관한다. 그리고 위에 있는 `node`들은 데이터탐색 가이드라인만 제공한다.

![](https://i.gyazo.com/7e5316a3983d3ff623677fca752a0525.png)
> 또한 B+tree는 맨 밑 `node`가 화살표로 연결이 되어 있는데 이렇게 되면 범위검색이 매우쉬워진다. <br/>
> 예를 들어 4~8까지 찾는다라고 하면 4,5,6을 찾고 화살표를 타고 바로 7,8까지 찾을수 있기 때문에 범위검색이 쉬워지는 것이다.

## Index의 단점
### 1. DB용량을 더 많이 먹는다.
![](https://i.gyazo.com/fa0e8a23f55873884ebab901b481aecf.png)
> Index를 만드는 것 자체가 복사본을 하나 더 만드는 동작이기 때문에 DB의 용량을 차지할수 밖에 없다. <br />
> 따라서 검색작업이 필요없는 테이블은 index를 만들지 않는 것이 좋다.

### 2. 삽입, 수정, 삭제를 하면 성능 하락이 생길수 있다.
![](https://i.gyazo.com/822922fe888addae2b01cb6fa7852c9c.png)
> 변경된 사항은 Index에도 똑같이 적용이 되야 함으로 `성능하락`같은 것들이 생길수 있다. (사실 크게 신경 쓸건 아니다)

## 참고사항
![](https://i.gyazo.com/2af8aaa7f140015e0449f540e18929a5.png)
> Primary key는 자동으로 정렬이 되므로 index 생성이 필요없다. <br />
> 그리고 이것을 clustered index라고도 부른다.

### 🔍Reference
(https://www.youtube.com/watch?v=iNvYsGKelYs)
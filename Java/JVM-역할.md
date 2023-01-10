# JVM이란 무엇인가?

---
>**J**ava **V**irtual **M**achine의 줄임말. <br/>
> 직역하면 '자바를 위한 가상 머신'이다.
> Java는 OS에 종속적이지 않다는 특징을 가지고 있다. <br/>
> OS에 종속받지 않고 실행하기 위해서 OS위에서 Java를 실행 시킬 무언가가 바로 JVM이다. <br/>
> 즉, **OS에 종속받지 않고 CPU가 Java를 인식, 실행할 수 있게 하는 가상 컴퓨터이다.**

![](https://velog.velcdn.com/images%2Fpearl0725%2Fpost%2F0447372b-a7ab-49bf-8042-fee0fd90ac6c%2Fimage.png)
`.java -> javac(java compiler) -> .class -> JVM` <br/>
``간단하게 말하면 '컴퓨터'를 사용해서 '자바를 실행하기 위한 가상 컴퓨터' 라고 이해하면 좋을 것이다.``

![](https://blog.kakaocdn.net/dn/bvieSp/btqED1y0Dit/KpSawBlQlHKrQ2szrzVOVK/img.png)

> * 일반 애플리케이션의 코드 = OS만 거치고 하드웨어로 전달 <br/>
> * Java 애플리케이션 = JVM을 한번더 거치기 때문에, 그리고 하드웨어에 맞게 완전히 컴파일된 상태가 아니고 실행시에 해석(interpret)되기 때문에 속도가 느리다는 단점을 가지고 있다. <br/>

요즘엔 바이트코드(컴파일된 자바코드)를 하드웨어의 기계어로 바로 변환해주는 JIT컴파일러와 향상된 최적화 기술이 적용되어서 속도의 격차를 줄임

> 위 그림에서 볼수 있듯이 일반 애플리케이션은 OS와 바로 맞붙어 있기 때문에 OS에 종속적이다. <br />
> 따라서 다른 OS에서 실행을 시키기 위해선 애플리케이션을 그 OS에 맞게 변경해야 한다. <br />
> 단, JVM은 OS에 종속적이기 때문에 해당 OS에서 실행가능한 JVM이 필요하다.

![](https://blog.kakaocdn.net/dn/bj4r23/btqKC9Lso8f/KAECNkLIbzqKqZl2laBB01/img.png)

`이렇게 함으로써 자바의 중요한 장점 중의 하나인 "Write once, run anywhere.(한 번 작성하면 어디서든 실행된다.)"이 가능하게 되는 것이다.`
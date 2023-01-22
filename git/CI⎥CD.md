## 개요
> 회사에서 정말 많이 사용하는 CI/CD 개념 정리

### 📌 개념
```
CI : Continuous Intergration (지속적인 통합)
CD : Continuous Delivery (지속적인 제공)
또는 CD : Continuous Deployment (지속적인 배포)
```
---

#### CI
Continuous Integration (지속적인 통합)은 `버그 수정`이나 `새로 만드는 기능`들이 main Repository에 주기적으로 `build`되고 `test`하여 `merge` 되는것을 말한다.

>1. 코드 변경사항을 주기적으로 빈번하게 merge해야 한다. `(세부적으로 나누어서 개발하고 merge하는 것을 추천한다.)`
2. 통합을 위한 단계 (빌드, 테스트, 머지)의 자동화 `(회사에선 CI Script를 통해 Build하고 Test까지 한다.)`


#### 장점
* `주기적으로` merge를 해서 `개발 생산성`을 향상 시킬수 있고 코드의 결함이나 문제점을 빠르게 `발견`하고 `수정`할 수 있다.
* 문제를 수정해야 하는 `범위`가 작다.
* 코드 퀄리티 향상.
---

#### CD

CD에는 두가지가 있는데
Continuous Delivery(지속적인 제공) +
Continuous Deployment(지속적인 배포)가 있다.
하지만 서로 연관이 있고 섞어서 사용하는 경우도 있어서 비슷하다고 볼 수 있다.

> CI를 거쳐서 build와 test단계를 거치고 release 단계를 거친 후 `개발자가 코드를 확인`하고 `수동적`으로 `배포`하는 것은 Continuous Delivery(지속적인 제공)이라고 한다.

>위와 내용은 같지만 `배포를 자동적`으로 하는 것을 Continuous Deployment(지속적인 배포)라고 한다.

따라서
`지속적인 제공`인지 `지속적인 배포`인지 확인을 하려면 `자동화`가 되어 있는지 안되어 있는지만 확인하면 된다.

#### 요약
```
- 단계 -
code -> build -> release -> deploy
```

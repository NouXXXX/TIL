## Gitflow란 무엇인가?

> **Gitflow**란 5가지 브랜치를 이용해서 Repository(저장소)를 운영하는 브랜치 전략이다. <br/>
> 5가지 중 항시 유지되는 메인 브랜치 `main`, `develop` 2가지와 보조 브랜치 `feature`, `release`, `hotfix` 3가지로 구성이 되어 있다.

* `main` : 라이브 서버에 제품으로 출시되는 브랜치
* `develop` : 다음 출시 버전 개발 브런치
* `feature` : 기능 개발 브런치. `develop` 브랜치에 속함.
* `release` : 다음 버전 출시 준비 브랜치. `develop` 브랜치를 `release` 브랜치로 옮긴 후 QA, 테스트를 진행하고 `main`브랜치로 합친다.
* `hotfix` : `main`에서 발생한 버그들을 긴급하게 수정하는 브랜치.

이미지로 git-flow를 이해 해보자

## 1. 새로운 버전 개발
![](https://wac-cdn.atlassian.com/dam/jcr:a13c18d6-94f3-4fc4-84fb-2b8f1b2fd339/01%20How%20it%20works.svg?cdnVersion=721)

> `main`브랜치를 `develop` 브랜치로 보완 (다음 버전에서 추가 될 항목들 개발)

## 2. 기능 개발
![](https://wac-cdn.atlassian.com/dam/jcr:34c86360-8dea-4be4-92f7-6597d4d5bfae/02%20Feature%20branches.svg?cdnVersion=721)

> `feature` 브랜치에서 새로운 버전에 들어갈 기능 개발(친구추가, 그룹만들기 등등)

## 3. 배포
![](https://wac-cdn.atlassian.com/dam/jcr:8f00f1a4-ef2d-498a-a2c6-8020bb97902f/03%20Release%20branches.svg?cdnVersion=721)
> `develop`브랜치 -> `release`브랜치 옮긴후 QA, 테스트 진행 -> `main`브랜치에 merge

## 4. 오류 사항 수정
![](https://wac-cdn.atlassian.com/dam/jcr:cc0b526e-adb7-4d45-874e-9bcea9898b4a/04%20Hotfix%20branches.svg?cdnVersion=721)
> 배포후 생긴 버그(게임으로 치면 돈 복사 버그)를 빠르게 고치기 위해 `hotfix`브랜치에서 버그 사항 수정 후 `main`브랜치로 merge

### git-flow의 특징
* 주기적으로 배포하는 서비스에 적합함
* 가장 유명한 전략인 만큼 많은 IDE에서 시각화 도구, GUI를 지원해줌

### 번외
> 브랜치별 명명법이 조금 다른데 `main`는 `master`과 혼용하여 사용되고 있다.


### Reference
(https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
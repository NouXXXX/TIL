## Github Flow  방식
![](https://subicura.com/git/assets/img/github-flow.2fafce92.png)

> Github-Flow는 Github에서 제안하는 프로젝트 관리 방법이다. 브랜치와 `Pull Request`(줄여서 PR)라는 개념을 사용한다. <br />
> Github-Flow는 1개의 `master(main)` 브랜치와 PR을 활용한 단순하고 민첩한 브랜치 전략이다. <br/>
> `master(main)`브랜치는 제품이 출시되는 가장 최신버전의 브랜치이며, 모든 개발 내용이 `main`브랜치를 중심으로 구성된다.

그림을 보며 이해 해보자

### 1. 브랜치 생성
![](https://user-images.githubusercontent.com/37354145/110271724-ed599a00-800b-11eb-9709-116491dab98d.png)
> Github-Flow 전략은 기능 개발, 버그 픽스 등 어떤 이유로든 새로운 브랜치를 생성하는 것으로 시작된다. 단, 이때 체계적인 분류 없이 브랜치 하나에 의존하게 되기 때문에 **브랜치 이름을 통해 의도를 명확하게 드러내는 것이 매우 중요**하다.

### 2. 개발, 세부적 커밋
![](https://user-images.githubusercontent.com/37354145/110271726-edf23080-800b-11eb-96db-f48d64cbc249.png)
> 브랜치와 같이 커밋 메세지에 의존해야 하기 때문에 -> 커밋 메세지를 최대한 상세하게 적어주는 것이 중요하다.

### 3. PR 생성
![](https://user-images.githubusercontent.com/37354145/110271727-edf23080-800b-11eb-9911-87845f27da16.png)
> 개발이 완료되었다면 `master(main)` 브랜치 쪽으로 Pull-Request를 생성한다.

### 4. 리뷰, 토의, 리뷰, 토의
![](https://user-images.githubusercontent.com/37354145/110271728-ee8ac700-800b-11eb-82a0-744c87163305.png)
> 충분히 많은 리뷰와 토의를 거친다. PR이 `master(main)` 브랜치 쪽에 합쳐진다면 곧장 라이브 서버에 배포되는 것과 다름 없으므로 매우 상세한 리뷰와 토의가 이루어져야만 한다.

### 5. 토의가 끝났어도 테스트
![](https://user-images.githubusercontent.com/37354145/110271729-ee8ac700-800b-11eb-8834-fd0f077f337e.png)
> 리뷰와 토의가 끝났다면 해당 내용을 라이브 서버(혹은 테스트 환경)에 배포해본다. 배포시 문제가 발생한다면 곧장 `master(main)` 브랜치의 내용을 다시 배포하야 초기화 시킨다.

### 6. Merge
![](https://user-images.githubusercontent.com/37354145/110271731-ef235d80-800b-11eb-84d3-e4d52dbddc55.png)
> 라이브 서버(혹은 테스트 환경)에 배포했음에도 문제가 발견되지 않았다면 그대로 `master(main)` 브랜치에 push 하고, 즉시 배포를 진행한다. 대부분의 Github-Flow에선 `master(main)`브랜치를 최신 브랜치라고 가정하기 떄문에 배포 자동화 도구를 이용해서 Merge 즉시 배포를 시킨다.


## 🔍 Github-Flow의 특징
* 브런치 전략이 단순하며 git을 처음 접하는 사람도 쉽게 접근 가능하다.
* CI/CD가 자연스럽게 이루어진다.

**CI(Continuous Integration)**는 소스코드 변경 사항이 정기적으로 빌드 및 테스트되어 remote 저장소에 통합되는, 즉 빌드 및 테스트의 자동화를 의미한다. 지속적인 통합을 통해서 코드의 품질을 유지시키며, 여러 개발자가 동시에 소스코드 수정작업을 할 때 충돌을 최대한 줄여준다.

**CD(Continuous Deployment)**는 배포를 일일히 개발자가 하면 힘드니까 자동화 시키는 것, 즉 배포의 자동화다.

Github-Flow는 하나의 `master(main)`브랜치에 의존하기 때문에 자연스럽게 CI/CD가 진행된다.
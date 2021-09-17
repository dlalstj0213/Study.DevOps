## 목차

- [DevOps](#devops)
  - [정의](#정의)
  - [탄생 배경](#탄생-배경)
  - [DevOps의 필요성](#devops의-필요성)
    - [How to do](#how-to-do)
    - [How to practices : AWS](#how-to-practices--aws)

# DevOps

## 정의

> 제품의 변경사항을 품질을 보장함과 동시에 프로덕션에 반영하는데 걸리는 시간을 단축하기 위한 실천 방법의 모음  
> “a set of practices intended to reduce the time between committing a change to a system
and the change being placed into normal production, while ensuring high quality”


- 개발(Dev)와 운영(Ops)의 합성어.  
개발과 운영의 경계를 허물고 통합하고자 하는 문화 혹은 철학

즉, 데비옵스는 개발과 운영을 통합하여 제품 출시 및 조직의 효율성을 끌어올리기 위한 문화이다.

## 탄생 배경

아직 Cloud 서비스가 활발하지 않았던 시절, 개발과 운영의 괴리감이 크게 존재했다. 개발은 개발따로, 운영은 운영따로 관리하게 되면서 오류나 클라이언트 요청에 빠르게 대응하지 못했다.  
2009년 O'Reilly Velocity Conference에서 하루에 10회 이상 배포하기라는 미션을 가지고 Flicker에서 개발과 운영의 협업이 이루어지게 된다. 이후 Patrick Debois는 이 **10 Deploys per Day** 발표를 듣고 감명 받아 주최한 컨퍼런스가 DevOpsDays이며 이때 DevOps라는 단어가 만들어지기 시작했다.

## DevOps의 필요성

소프트웨어 개발은 다음과 같은 라이프사이클/생명주기를 가지고 있다.

**SDLC** (Software Development Lifecycle)

1. Design
2. Develop
3. Test
4. Deploy
5. Operate
6. Support

규모가 큰 서비스를 구성하게 되면 각 단계 별로 전문가를 주어 구성된 기능 조직을 운영할 수 있다.

1. Design - Architect
2. Develop - Developer
3. Test - SDET
4. Deploy - Release Eng
5. Operate - Sys Admin
6. Support - Customer Support

하지만, 그만큼 각 구간별로 의사소통이 많아지며 이는 커뮤니케이션 문제가 발생되고, 병목구간이 생기기 쉽다.

![](https://socio-tech.net/wp-content/uploads/2021/08/7602.1513404277.png)

그래서 위의 그림과 같이 개발자 본인이 작성한 코드에 대해 스스로 테스트하고, 배포하고, 운영에 참여할 수 있게 DevOps 문화를 만들어야 한다.

- 업무 효율성 개선
- 조직 내 협업 개선
- 빠른 제품 출시 주기

### How to do

데브옵스는 어떻게 해야하는 것일까?

데브옵스는 단순히 패러다임일 뿐이다. 그리고 방법을 제시하지 않으며 그저 조직의 문화이다.

하지만 데브옵스는 방법을 제시해주지는 않지만, 여러 실천 방법들을 활용할 수 있다.

데브옵스는 하나의 목표를 바라본다. "개발과 운영의 통합하여 더 빠르고 자주 배포하기"

### How to practices : AWS

1. **지속적 통합** ( Continuous Integration )

개발자가 만든 변경사항에 대하여 빌드 및 테스트를 진행한 후, 중앙코드 저장소에 통합하여 빠르게 버그를 발견하고 제품의 품질을 보장할 수 있게 해주는 소프트웨어 개발 방법이다.

2. **지속적 배포** ( Continuous Delivery )

개발 결과물인 산출물을 자동으로 개발환경이나 운영환경까지 배포하도록 하는 자동화된 파이프라인을 구축하여 배포하는 방법이다.

지속적 통합과 배포는 데브옵스를 적용함에 있어 가장 기본적으로 실천되어야 한다.

3. **마이크로서비스** ( Micro-services )

규모가 큰 서비스가 주로 해당되며, 이와 같은 상황에서는 빌드에 많은 시간이 걸리게 된다. 결국 빌드 및 테스트 단계에서 병목현상이 주로 발생하게 되는데, 이를 마이크로서비스를 도입하여 커다란 서비스를 여러 마이크로서비스로 쪼개어 빌드타임과 배포타임을 단축시킬 수 있다.

4. **IaC** ( Infrastructure as Code )

IaC는 Infrastructure를 코드로 관리하는 것을 의미한다. 서비스를 배포함에 있어서 결국은 인프라에서도 변경사항이 필요하게 된다. 그래서 인프라 또한 자동화된 관리가 필요하다. 즉, 여기서의 IaC는 인프라 변경사항을 자동화시켜 빠르게 적용시키는 방법을 이야기한다.

5. **모니터링과 로깅** ( Monitoring & Logging )

개발자에게 제품의 매트릭과 로그 데이터를 중앙에서 확인할 수 있는 환경을 제공해줌으로써 개발자가 직접 운영에 참여하여 문제 발생시 개발자가 보다더 빠르게 문제를 해결할 수 있다.

6. **소통 및 협업** ( Communication & Collaboration )

조직 문화에 있어 소통 및 협업을 개선하는 것도 데브옵스 문화를 정착시키는데 큰 도움을 준다. 사내에서 사용하는 Slack과 같은 메신저 시스템이나, Jira와 같은 이슈 트레킹 시스템 혹은 Confluence와 Notion과 같은 리치 시스템을 잘 활용하는 것도 중요하다.




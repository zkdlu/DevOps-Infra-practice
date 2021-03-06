# IT Infrastructure
- 어플리케이션을 가동시키기 위해 필요한 하드웨어나 OS, 미들웨어, 네트워크 등 시스템의 기반
- 시스템의 요구사항이라고 하면 해당 시스템이 어떤 기능을 하는지, 무엇을 할 수 있는지를 생각하는데 이를 기능적인 요구사항이라고 하며 이외에 시스템 성능, 안정성, 확장성, 보안 등과 같은 요구사항을 비기능적인 요구사항이라고 함.
- 인프라는 이런 비기능적인 요구사항과 관련이 있음

### 인프라의 구성요소
- 하드웨어 : 서버 장비 본체나 데이터를 저장하기 위한 스토리지, 전원 장치 등. 넓은 의미에서는 하드웨어를 설치하는 데이터센터의 설비도 포함
- 네트워크 : 사용자가 원격으로 접근할 수 있도록 서버를 연결하는 도구. 라우터, 스위치, 방화벽 등 네트워크 장비와이를 연결하는 케이블 배선 등. 사용자가 단말에서 무선으로 연결할 때 필요한 Access Point도 있음.
- 운영체제 : 하드웨어나 네트워크 장비를 제어하기 위한 기본적인 소프트웨어. 리소스나 프로세스를 관리
 - 클라이언트 OS : 사용자가 사용하기 쉽도록 하는데 초점을 맞춤 (Windows 등)
 - 서버 OS : 시스템을 빠르고 안정적으로 실행하는데 초점을 맞춤 ( Linux 등)
- 미들웨어 : 서버상에서 서버가 특정 역할을 하도록 기능을 제공하는 소프트웨어

# CI/CD (지속적 통합 / 지속적 배포)

- CI/CD 파이프라인은 새 버전의 소프트웨어ㅡㄹ 제공하기 위해 수행해야 하는 일련의 단계
- CI/CD 파이프라인은 통합 및 테스트 단계와 제공 및 배포 단계에서 모니터링 및 자동화를 도입하여 
어플리케이션 개발 프로세스를 개선함.

## 마틴 파울러 CI 4규칙
1. 모든 소스 코드가 살아있고 (실행되고) 어느 누구든 현재의 소스를 접근할 수 있는 단일 지점을 유지 할 것
2. 빌드 프로세스를 자동화시켜서 어느 누구든 소스로부터 시스템을 빌드하는 단일 명령어를 사용할 수 있게 할 것
3. 테스팅을 자동화시켜 단일 명령어를 통해서 언제든지 시스템에 대한 건전한 테스트를 실행할 수 있게 할 것
4. 누구나 현재 실행 파일을 얻으면 지금까지 최고의 실행파일을 얻었다는 확신을 하게 만들 것

### CI/CD 파이프라인 요소
- CI/CD 파이프라인의 단계는 각기 다른 태스크 하위 집합으로 이루어져 있는데, 이를 파이프라인 단계라고 부릅니다.

1. **빌드** - 어플리케이션 컴파일 하는 단계
2. **테스트** - 코드를 테스트 하는 단계. 이 단계를 자동화하여 시간과 수고를 줄일 수 있습니다.
3. **릴리즈** - 어플리케이션을 레포지토리에 제공하는 단계
4. **배포** - 코드를 프로덕션에 배포하는 단계
5. **검증 및 컴플라이언스** - 빌드 검증 단계는 해당 조직의 필요에 따라 결정됨.

> git push -> github action -> code deploy[s3 사용] -> ec2 배포 -> 실행
> - 참고: https://isntyet.github.io/deploy/github-action%EA%B3%BC-aws-code-deploy%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%98%EC%97%AC-spring-boot-%EB%B0%B0%ED%8F%AC%ED%95%98%EA%B8%B0(2)/


# 공부 리스트
## [Docker](https://github.com/zkdlu/docker-example)
spring boot 프로젝트로 docker 이미지 빌드하여 구동
> Docker network 랑 Docker 컴포져 공부하기

## [kafka](https://github.com/zkdlu/spring-boot-kafka)
> 메시지 큐 이용한 서비스 구현해보기

## [ELK](https://github.com/zkdlu/spring-boot-elasticsearch)
> 서비스에 로그 시스템으로 사용해보기

## [Redis](https://github.com/zkdlu/spring-boot-redis)
> 서비스에 캐싱용으로 사용해보기

## [MSA](https://github.com/zkdlu/spring-boot-cloud)
> .net이든 spring이든 마이크로 서비스 구축해보기

> 마이크로 서비스는 내가 아는 것 이상으로 서비스가 쪼개져야 한다. 로그인에 필요한 인증 서비스가 죽어도 메인 서비스는 구동이 되어야 하듯이

## [Github action or Jenkins](https://github.com/zkdlu/github-action-example)
> CI/CD, 수동으로 배포해보고 자동화 배포 해보기

## [Kubernetes](https://github.com/zkdlu/kubernetes-example)
> 쿠버네티스 활용하여 서비스 운용해보기
> - 도커가 CRI(Container Runtime Interface)를 지키지 않아 지원을 끊는다고 한다.
> - 도커에서 생성한 이미지는 생성하고 실행하는게 가능하다고 함.
> - 다른 컨테이너 런타임 쓰라고 한다. (containerd, CRI-O) 
> - 아직 각 좀 봐야겠다..
> - https://kubernetes.io/blog/2020/12/02/dont-panic-kubernetes-and-docker/

## [Amazon 인프라 활용하기](https://github.com/zkdlu/aws-example)
> EC2, Storage 등등

> 웹 서비스는 무조건 웹 방화벽을 생각하자

## [Back-End Framework](https://github.com/zkdlu/backend-framework)
> 꾸준히 공부하셈
> ASP.NET Core냐 Spring이냐 Node.js냐는 중요치 않음. 각 프레임워크가 가지고 있는 이점을 이해하자.
> 프레임워크만 아니라 개발 인프라를 얼마나 잘 활용하는지가 중요

## [DB](https://github.com/zkdlu/backend-framework/blob/main/db/mysql.md)
> DB도 공부 해야지

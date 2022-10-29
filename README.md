<br>

## 🚉 지하철 노선도 애플리케이션
<br>

<p align="center">
    <img width="200px;" src="https://raw.githubusercontent.com/woowacourse/atdd-subway-admin-frontend/master/images/main_logo.png"/>
</p>


### 💻 나의 프로젝트의 목표와 성과
#### 목표
- AWS 상에서 네트워크를 구성해본다.
- 컨테이너를 학습하고 3 tier로 운영환경을 구성해본다.
- Docker 가 필요한 이유에 대해 생각해본다.
- 애플리케이션이 운영되는 환경을 구성해보며 네트워크, 운영체제, 데이터베이스, 컨테이너 등에 대해 생각해본다.

#### 성과
- 실제 상용되는 서비스가 되기 위해서 필요한 요소들(`24시간`, `보안`, `무중단`)에 대한 이해와 이를 바탕으로 한 인프라 설계 <br>
  [↳ 그럴듯한 서비스란? 에 관한 블로그 포스팅 (@yyy96)](https://velog.io/@yyy96/인프라-미션)
  
- VPC 생성을 통한 subnet, internet gateway, route table 등 네트워크 이해 및 설계 <br>
  [↳ 통신망 구성에 관한 블로그 포스팅 (@yyy96)](https://velog.io/@yyy96/통신망)
  
- Docker을 사용한 배포 및 배포 스크립트 작성<br>
  [↳ 배포에 관한 블로그 포스팅 (@yyy96)](https://velog.io/@yyy96/통신망)


<br><br><br>

![image](https://user-images.githubusercontent.com/65826145/198815976-1e528d2e-068b-4ca3-8843-bb00f8bc7be9.png)

<br><br>

### 웹 서비스를 위한 통신망 구성하기
1. 구성한 망의 서브넷 대역
> - 대역 :
>   - 192.168.13.0/26 (외부망1, ap-northeast-2a), 
>   - 192.168.13.64/26 (외부망2, ap-northeast-2b), 
>   - 192.168.13.128/27(내부망, ap-northeast-2c), 
>   - 192.168.13.160/27(관리망, ap-northeast-2d)

2. 배포한 서비스의 공인 IP(혹은 URL)
> - IP  : 13.125.146.68
> - URL : https://infrayyy96.o-r.kr/

<br>

### 웹 애플리케이션 배포하기
1. TLS가 적용된 URL
> - URL : https://infrayyy96.o-r.kr/

2. 배포 스크립트 작성
> - deploy.sh


# 1. EC2 기초 

<details> <summary> 1. EC2 란 무엇인가? </summary>

## 1. EC2 란 무엇인가?

### 용어
- Elastic Compute Cloud 

### 정의
- Amazon Elastic Compush Cloud(EC2)는 안전하고 크기 조정이 가능한 컴퓨팅 파워를 클라우드에서 제공하는 웹 서비스이다.
- 개발자가 더 쉽게 웹 규모의 클라우드 컴퓨팅 작업을 할 수 있도록 설계되었다.
- Amazon EC2의 간단한 웹 서비스 인터페이스를 통해 간단하고 필요한 용량을 얻고 구성할 수 있다.
- 컴퓨팅 리소스에 대한 포괄적인 제어권을 제공하며, Amazon의 검증된 컴퓨팅 인프라에서 실행할 수 있다. 

### 특징
- 새로운 서버 인스턴스를 획득하고 부팅하는 데 필요한 시간을 단 몇 분으로 단축하므로 컴퓨팅 요구 사항의 변화에 따라 신속하게 용량을 확장하거나 축소할 수 있다.
- 실제 사용한 만큼만 요금을 지불하면 되므로, 컴퓨팅 비용이 절약된다.
- 개발자가 장애에 대한 복원력이 뛰어나고 일반적인 오류 상황에 영향을 받지 않는 애플리케이션을 구축할 수 있도록 도구를 제공한다.


</details>

<details> <summary> 2. EC2의 가격 정책 </summary>

## 2. EC2의 가격 정책

### On-Demand
- 실행하는 인스턴스에 따라 시간 또는 초당 컴퓨팅 파워로 측정된 가격을 지불
  - 약정은 필요 없음
  - 장기적인 수요 예측이 힘들거나 유연하게 EC2를 사용하고 싶을 때
  - 한번 써보고 싶을 때 

### Spot Instance
- 경매 형식으로 시장에 남는 인스턴스를 저렴하게 구매해서 쓰는  방식 
  - 최대 90%정도 저렴
  - 단 언제 도로 내주어야 할지 모름
  - 시작 종료가 자유롭거나 추가적인 컴퓨팅 파워가 필요한 경우 

### 예약 인스턴스(Reserved Instance-RI)
- 미리 일정 기간(1년~3년) 약정해서 쓰는 방식
  - 최대 75%까지 저렴 (On-Demand에 비해서)
  - 수요 예측이 확실할 때
  - 총 비용을 절감하기 위해 어느정도 기간의 약정이 가능한 사용자

### 전용 호스트(Dedicated)
- 실제 물리적인 서버를 임대하는 방식
  - 라이선스 이슈(Windows Server등)
  - 규정에 따라 필요한 경우 



</details>

<details> <summary> 3. EC2의 타입 종류 </summary>

## 3. EC2의 타입 종류

![image](https://user-images.githubusercontent.com/28394879/136486505-60bb1b4e-51f7-47c8-bbc6-681d39df87dd.png)


</details>

# 2. EC2 기초(2) 

<details> <summary> 1. EC2 와 다른 AWS 서비스들 </summary>

## 1. EC2 와 다른 AWS 서비스들

![image](https://user-images.githubusercontent.com/28394879/136922152-6d6d9a9b-6c72-476c-aecf-0f2f8e293f04.png)

</details>

<details> <summary> 2. DBS/Instance Storage </summary>

## 2. DBS/Instance Storage

### 용어 
- Elastic Block Store

### 정의 
- Amazon Elastic Block Store(EBS)는 AWS 클라우드의 Amazon EC2 인스턴스에 사용할 영구 블록 스토리지 볼륨을 제공한다.
- 각 Amazon EBS 볼륨은 가용 영역 내에 자동으로 뽁제되어 구성요소 장애로부터 보호해주고, 고가용성 및 내구성을 제공한다.
- Amazon EBS 볼륨은 워크로드 실행에 필요한 지연 시간이 잛고 일관된 성능을 제공한다.
- Amazon EBS를 사용하면 단 몇 분 내에 사용량을 많게 또는 적게 확장할 수 있으며, 프로비저닝한 부분에 대해서만 저렴한 비용을 지불한다.

![image](https://user-images.githubusercontent.com/28394879/136925202-f5785c89-9377-43ee-8fc2-45bbb47e424d.png)
- EBS Based: 반 영구적인 파일의 저장 가능
  - Snapshot 가능
  - 인스턴스 업그레이드 가능
  - STOP이 가능함
- Instance Store: 휘발성이나 빠른 방식
  - 빠르지만 저장이 필요 없는 경우
  - Stop이 불가능함 



</details>

<details> <summary> 3. AMI </summary>

## 3. AMI

### 용어
- Amazon Machine Image

### 정의
- Amazon 머신 이미지(AMI)는 인스턴스를 시작하는데 필요한 정보를 제공한다.
- 인스턴스를 시작할 때 AMI를 지정해야 한다.
- 동일한 구성의 인스턴스가 여러 개 필요할 때는 한 AMI에서 여러 인스턴스를 시작할 수 있다.
- 서로 다른 구성의 인스턴스가 필요할 때는 다양한 AMI를 사용하여 인스턴스를 시작하면 된다. 

### 특징

![image](https://user-images.githubusercontent.com/28394879/136926299-e8917a9f-404e-4a96-b485-c6722d608950.png)
- AMI는 다음을 포함한다
  - 1개 이상의 EBS 스냅샷 또는, 인스턴스 저장 지원 AMI의 경우, 인스턴스의 루트 볼륨에 대한 템플릿(예: 운영체제, 애플리케이션 서버, 애플리케이션)
  - AMI를 사용하여 인스턴스를 시작할 수 있는 AWS 계정을 제어하는 시작 권한
  - 시작될 때 인스턴스에 연결할 볼륨을 지정하는 블록 디바이스 매핑 




</details>



# 3. Security Group

<details> <summary> 1. Security Group 란 무엇인가? </summary>

## 1. Security Group 란 무엇인가?

![image](https://user-images.githubusercontent.com/28394879/136934211-085a6871-2ff6-423d-b208-88e55945c45f.png)

- 보안그룹은 인스턴스에 대한 인바운드 및 아웃바운드 트래픽을 제어하는 가상 방화벽 역할을 한다.
- VPC에서 인스턴스를 시작 할 때 최대 5개의 보안 그룹에 인스턴스를 할당할 수 있다.
- 보안 그룹은 **서브넷 수준이 아니라 인스턴스 수준에서 작동**하므로 VPC에 있는 서브넷의 각 인스턴스를 서로 다른 보안 그룹 세트에 할당할 수 있다.
- 시작 할 때 특정 그룹을 지정하지 않으면 인스턴스가 자동으로 VPC의 기본 보안 그룹에 할당된다.

</details>

<details> <summary> 2. Security Group 특징 </summary>

## 2. Security Group 특징

- 보안 장치
  - Network Access List(NACL)와 함께 방화벽의 역할을 하는 서비스
- Port 허용
  - 트래픽이 지나갈 수 있는 Port와 Source를 설정 가능
  - Deny는 불가능 -> NACL 로 가능 
- 인스턴스 단위
  - 하나의 인스턴스에 하나 이상의 SG설정 가능
  - NACL의 경우 서브넷 단위
  - 설정된 Instance는 설정한 모든 SG의 룰을 적용 받음


![image](https://user-images.githubusercontent.com/28394879/136935520-e5b45cb7-28e1-48e6-863f-02572c399284.png)

- 설정된 모든 룰을 사용해서 필터링
  - NACL의 경우 적용된 룰의 순서대로 필터링 
- Stateful  
  - Inbound로 들어온 트래픽이 별 다른 Outbound 설정 없이 나갈 수 있음
  - NACL은 Stateless

![image](https://user-images.githubusercontent.com/28394879/136936301-7550285b-8c2a-4428-9414-d4072812e38b.png)

![image](https://user-images.githubusercontent.com/28394879/136936510-05742607-16dc-4031-b1b4-972aa13cad5e.png)

</details>

# 4. ELB

<details> <summary> 1. ELB란 무엇인가? </summary>

## 1. ELB란 무엇인가?
![image](https://user-images.githubusercontent.com/28394879/137287365-896396b6-3eca-4894-afd1-6c1750340e39.png)

### 용어 
- Elastic Load Balancer

### 정의
- Elastic Load Balancing은 들어오는 애플리케이션 트래픽을 Amazon EC2 인스턴스, 컨테이너, IP 주소, Lambda 함수와 같은 여러 대상에 자동으로 분산시킨다.
- Elastic Load Balancing은 단일 가용 영역 또는 여러 가용 영역에서 다양한 애플리케이션 부하를 처리할 수 있다.
- Elastic Load Balancing이 제공하는 세 가지 로드 밸런서는 모두 애플리케이션의 내결함성에 필요한 **고가용성, 자동 확장/축소, 강력한 보안**을 갖추고 있다.

### Vertical Scale
![image](https://user-images.githubusercontent.com/28394879/137288267-d5a5a8b8-4907-44d1-9bcd-12a13be07bf1.png)

![image](https://user-images.githubusercontent.com/28394879/137288362-b1ce0bd9-4d9a-44b2-a8ee-ed6b544915a2.png)

### Horizontal Scale
![image](https://user-images.githubusercontent.com/28394879/137288510-7d1db362-be70-4dce-b59e-9c5bfe216d33.png)

![image](https://user-images.githubusercontent.com/28394879/137288634-1ed44f9c-a25e-41b1-a928-b698d694d0c2.png)


</details>

<details> <summary> 2. ELB의 특징 </summary>

## 2. ELB의 특징

- IP가 지속적으로 바뀜
  - 지속적으로 IP 주소가 바뀜
  - 따라서 도메인 기반으로 사용해야 함
- Health Check
  - 직접 트래픽을 발생시켜 Instance가 살아있는지를 체크함
  - InService, OutofService 두가지 상태로 나누어짐 
- 3가지 종류가 존재함
  - Application Load Balancer
  - Network Load Balancer
  - Classic Load Balancer



</details>

<details> <summary> 3. ELB의 종류 </summary>

## 3. ELB의 종류

### Application Load Balancer
- Application Level
- "똑똑한 놈"

### Network Load Balancer
- "빠른놈"
- Elastic IP 할당 가능 

### Classic Load Balancer
- "옛날놈"
- 요즘은 잘 안씀 


</details>

<details> <summary> 4. Sticky Session </summary>

## 4. Sticky Session

![image](https://user-images.githubusercontent.com/28394879/137290519-58ba8dec-02b3-400a-8973-20412d1fcc0b.png)
- 2개이상의 Instance가 있다고 했을때 A Instance의 웹서버에 로그인을하면 Session이 하나 발급될 것이다.
- 그런데, 한번더 요청을 했을때 B Instance의 웹서버에 요청하느라 Session이 없어 재로그인을 하라고 요청을 할 것이다.
- 이 것을 방지하기 위해 나온 것이 Sticky Session이다.
- Sticky Session은 사용자마다 어떤 인스턴스에 접근했는지를 저장해두고 다음번의 요청시에 해당하는 인스턴스로 접속할 수 있도록 해주는 것이다.





</details>



# 5. Auto Scaling

<details> <summary> 1. Autoscaling 이란 무엇인가 </summary>

## 1. Autoscaling 이란 무엇인가

- AWS Auto Scaling은 애플리케이션을 모니터링하고 용량을 자동으로 조정하여, **최대한 저렴한 비용으로 안정적**이고 예측 가능한 성능을 유지한다.
- AWS Auto Scaling을 사용하면 몇 분 만에 손쉽게 여러 서비스 전체에서 여러 리소스에 대해 애플리케이션 규모 조정을 설정 할 수 있다.

![image](https://user-images.githubusercontent.com/28394879/137873154-df8c7c15-d8a4-4c0c-9d71-2387331edfd4.png)


</details>

<details> <summary> 2. Autoscaling 의 활용 </summary>

## 2. Autoscaling 의 활용

- 최소한의 인스턴스 사용
- 원하는 만큼의 인스턴스 개수를 목표로 유지
- 최대 인스턴스 개수 이하로 인스턴스를 유지
- Availability Zone 에 골고루 분산될 수 있도록 인스턴스를 분배
- 항상 서비스가 유지될 수 있는 인스턴스를 확보 

### EC2 Auto Scaling의 구성
- Launch Configuration: 무엇을 어떻게 실행시킬 것인가?
  - EC2의 타입, 사이즈
  - AMI
  - Security Group, Key, IAM
  - User Data
- Monitoring: 언제 실행시킬 것인가? + 상태 확인
  - 예: CPU 점유율이 일정 %을 넘어섰을 때 추가로 실행 or 2개 이상이 필요한 스택에서 EC2 하나가 죽었을 때
  - Cloud Watch (And/Or) ELB 와 연계
- Desired Capacity: **얼만큼** 실행 시킬 것인가?
  - 예: 최소 1개 ~ 최대 3개
- Lifecycle Hook: 인스턴스 시작/종료 시 Callback
  - 다른 서비스와 연계하여 전/후 처리 가능 -> CloudWatch Event/SNS/SQS
  - Terminating: wait/Terminating: Proceed 상태로 전환
  - 기본 3600초 동안 기다림 ( 기다리는 동안 이미지 백업이나 로그 백업 등의 작업을 할 수 있게끔 )

### EC2 Auto Scaling의 순서도
![image](https://user-images.githubusercontent.com/28394879/137876824-8fb023db-f32b-4959-93c4-a1c930bf792f.png)


</details>


# 6. VPC

<details> <summary> 1. VPC란? </summary>

## 1. VPC란?

- Amazon Virtual Private Cloud(VPC)를 사용하면 AWS 클라우드에서 **논리적으로 격리된 공간**을 프로비저닝 하여 고객이 정의하는 **가상 네트워크**에서 AWS 리소스를 시작할 수 있다.   
- **IP 주소 범위 선택, 서브넷 생성, 라우팅 테이블 및 네트워크 게이트 구성** 등 가상 네트워킹 환성을 완벽하게 제어할 수 있다. 
- VPC에서 IPv4와 IPv6를 모두 사용하여 리소스와 애플리케이션에 안전하고 쉽게 액세스 할 수 있다.

- Default VPC
  - 계정 생성 시 자동으로 셋업 되어 있음(모든 리전에)
  - 모든 서브넷의 인터넷 접근이 가능함
  - EC2가 퍼블릭 IP와 Private IP 모두 가지고 있음
  - 삭제시 복구 불가
- Custom VPC
  - 새로 만들어야 함
  - Default VPC의 특징을 가지고 있지 않음 

- VPC를 사용하여 할 수 있는 일들
  - EC2 실행 가능
  - 서브넷을 구성 가능
  - 보안 설정(Ip block, 인터넷에 노출되지 않은 EC2 구성 등) 가능
- VPC Peering: VPC간에 연결
  - Transitive Peering 불가능: 한 다리 건너 연결 되어 있다고 해서 Peering이 된 것이 아님
- VPC Flow Log
  - VPC의 로그를 CloudWatch에 저장 가능
- IP 대역 지정 가능
- Region에 하나: 다른 Region으로 확장 불가능 

</details>

<details> <summary> 2. VPC의 구성요소 </summary>

## 2. VPC의 구성요소

![image](https://user-images.githubusercontent.com/28394879/141058705-4ac55134-69e5-441a-b1ba-3b4f71c90e28.png)

1. **A**vailability **Z**one
2. Subnet
3. **I**nternet **G**ate **W**ay
4. **N**etwork **A**ccess **C**ontrol **L**ist/Secuirty Group
5. Route Table
6. **N**etwork **A**ddress **T**ranslation Instance/NAT Gateway
7. Bastion Host
8. VPC Endpoint


### Availability Zone
- 물리적으로 분리되어 있는 인프라가 모여 있는 데이터 센터
- 고가용성을 위해서 항상 일정 거리 이상 떨어져 있음
- 하나의 리전은 2개 이상의 AZ로 이루어져 있음 
  - 계정 1의 AZ-A는 계정 2의 AZ-A와 다른곳에 있음 

![image](https://user-images.githubusercontent.com/28394879/141059214-0bf68399-1fb8-4a6e-9b75-83d29d2cb893.png)

### Subnet
- VPC의 하위 단위
- 하나의 AZ에만 생성 가능: 다른 AZ로 확장 불가 
  - 하나의 AZ에는 여러 Subnet 생성 가능 
- Private Subnet: 인터넷에 접근 불가능한 Subnet
- Public Subnet: 인터넷에 접근 가능한 Subnet
- CIDR block range 설정 가능 

### Internet Gateway(IGW)
- 인터넷으로 나가는 경로 
- 고가용성이 확보되어 있음 
- IGW로 연결되어 있지 않은 서브넷=Private Subnet
- Route Table에서 연결해줘야 함


### NACL/Security Group
- 검문소
- NACL => Stateless, SG => Stateful
- 기본적으로 VPC 생성시 만들어줌
- Deny는 NACL에서만 가능

### Route Table
![image](https://user-images.githubusercontent.com/28394879/141064479-4e31b75a-e564-40a1-8574-306f150a2def.png)

- 트래픽이 어디로 가야 할지 알려주는 이정표
- 기본적으로 VPC 생성시 만들어줌 


### NAT Instance/NAT Gateway

![image](https://user-images.githubusercontent.com/28394879/141087041-97f1c809-eb26-4950-88ea-5b900c7637e6.png)

- Private Instance가 외부의 인터넷과 통신하기 위한 통로 
- NAT Instance는 단일 Instance / NAT Gateway는 AWS에서 제공하는 서비스
- NAT Instance를 사용할 때 Source/Destination Check을 해제해야 함 
- NAT Instance는 Public Subnet에 있어야 함


### Bastion Host

![image](https://user-images.githubusercontent.com/28394879/141087702-b6cdb535-04ea-4c4a-8624-3cf642539183.png)


- Private Instance 에 접근하기 위한 Instance 
- Public Subnet에 위치해야 함


### VPC Endpoint
- VPC 엔드포인트를 통해 인터넷 게이트웨이, NAT 디바이스, VPN 연결 또는 AWS Direct Connect 연결을 필요로 하지 않고 AWS PrivateLink 구동 지원 AWS 서비스 및 VPC 엔드포인트 서비스에 **비공개**로 연결할 수 있다.
- VPC의 인스턴스는 서비스의 리소스와 통신하는데 **퍼블릭 IP 주소를 필요로 하지 않다**
- VPC와 기타 서비스 간의 트래픽은 **Amazon 네트워크를 벗어나지 않는다.**

#### VPC Endpoint 종류

![image](https://user-images.githubusercontent.com/28394879/141247694-0059b7ae-aa55-4f35-96e1-03e15351161e.png)
- Interface Endpoint: ENI(Elastic Network Interface) 기반 
  - Private ip 를 만들어 서비스로 연결시켜줌
  - 많은 서비스들을 지원 (SQS, SNS, Kinesis, Sagemaker 등)

![image](https://user-images.githubusercontent.com/28394879/141247612-e2e9ef57-147f-4889-81c2-c4b2d6ab6293.png)
- Gateway Endpoint: 라우팅 테이블에서 경로의 대상으로 지정하여 사용
  - S3, DynamoDB 지원

</details>



# 7. 고가용성과 장애내구성의 차이는? - 클라우드 관련 개념/용어

<details> <summary> 1. 고가용성과 장애내구성의 차이는? </summary>

## 1. 고가용성과 장애내구성의 차이는?

- 고가용성(High Availability, HA): 장애 상황을 해결하고 서비스를 지속할 수 있는 능력
  - 장애 상황을 위한 준비가 필요
- 장애 내구성 or 내결함성(Fault Tolerance): 장애 상황에도 서비스를 지속할 수 있는 능력
  - 장애 상황에 영향을 받지 않는 아키텍처가 필요 

![image](https://user-images.githubusercontent.com/28394879/141256455-d986a851-5aba-4ec0-871f-f9ea4cb91206.png)


</details>

<details> <summary> 2. 재해 복구 </summary>

## 2. 재해 복구

- 재해 복구(disaster recovery)
  - 말 그대로 장애 상황을 복구하는 것


</details>

<details> <summary> 3. 확장성/탄력성 </summary>

## 3. 확장성/탄력성

![image](https://user-images.githubusercontent.com/28394879/141257750-4bbd0946-33c1-4e09-b308-ecc6bc9529a5.png)
- 확장성(Scalable): 쉽고 빠르게 규모를 늘릴 수 있는 능력
  - 주로 수요에 따라 컴퓨팅 파워 혹은 용량 확장 


![image](https://user-images.githubusercontent.com/28394879/141257658-d3bb6d6f-9423-4135-a2e6-27b39610924a.png)
- 탄력성(Elastic): 수요에 따라 컴퓨팅 파워/용량을 확장하거나 축소할 수 있는 능력
  - 불필요한 자원을 사용하지 않고 비용 최적화에 필수적인 능력 

</details>



# 8. RDS

<details> <summary> 1. RDS란? </summary>

## 1. RDS란?

- Amazon Relational Database Service(RDS)를 사용하면 클라우드에서 관계형 데이터베이스를 간편하게 설정, 운영 및 확장할 수 있다.
- 하드웨어 프로비저닝, 데이터베이스 설정, 패치 및 백업과 같은 시간 소모적인 관리 작업을 자동화하면서 비용 효율적이고 크기 조정 가능한 용량을 제공한다.
- 사용자가 애플리케이션에 집중하여 애플리케이션에 필요한 빠른 성능, 고가용성, 보안 및 호환성을 제공할 수 있도록 지원한다.

</details>

<details> <summary> 2. RDS의 아키텍처 </summary>

## 2. RDS의 아키텍처 

![image](https://user-images.githubusercontent.com/28394879/141259851-a09fe71d-97fd-4716-92de-9154f23cf694.png)

</details>

<details> <summary> 3. RDS의 특징 </summary>

## 3. RDS의 특징

- 관계형 데이터베이스를 제공하는 서비스
  - Relational Database Service: **관계형** 데이터베이스
  - <--> NoSql(DynamoDB, DocumentDB, ElasticCache)
- 가상 머신 위에서 동작
  - 단 직접 시스템에 직접 로그인 불가능 -> OS 패치, 관리 등은 AWS의 역할
- RDS는 Serverless 서비스가 아님
  - 단 Aurora Serverless는 말그대로 Serverless 서비스
- CloudWatch 와 연동
  - DB 인스턴스의 모니터링(EC2와 동일)
  - DB에서 발생하는 여러 로그 (Error Log, General Log 등)을 CloudWatch와 연동하여 확인 가능
- 내부에서는 EC2를 활용
  - VPC안에서 동작
    - 기본적으로 public IP를 부여하지 않아 외부에서 접근 불가능
    - 설정에 따라 public 으로 오픈 가능(DNS로 접근)
  - 서브넷과 보안그룹 지정 필요
  - EC2 타입의 지정 필요
  - 스토리지는 EBS를 활용
    - EBS 타입의 선택 필요
    - 생성시 EBS의 용량을 지정해서 생성
- Parameter Group: Root유저만 설정 가능한 DB의 설정값들을 모아 그룹화한 개념
  - DB 클러스터에 파라메터 그룹을 적용시켜 설정값을 적용
- 업데이트
  - 마이너 버전 엔진 업데이트는 자동으로 업데이트 설정 가능
  - 기타 업데이트의 경우 점검 시간(Maintenance Window)를 설정하여 특정 시간에 업데이트가 이루어질수 있도록 설정 가능 
 
</details>

<details> <summary> 4. RDS의 인증방법 </summary>

## 4. RDS의 인증방법 

- 전통적인 유저/패스워드 방식
  - AWS Secret Manager와 연동하여 자동 로테이션 가능
- IAM DB 인증
  - 데이터베이스를 IAM 유저 크레덴셜/Role을 통해 관리 가능
- Kerberos 인증

</details>

<details> <summary> 5. RDS의 가격 모델 </summary>

## 5. RDS의 가격 모델

- 컴퓨팅 파워 + 스토리지 용량 + 백업 용량 + 네트워크 비용
- Reserved Instance 구매 가능
  - EC2와 마찬가지로 일정 기간을 계약하여 저렴한 가격에 서비스를 이용

</details>

<details> <summary> 6. RDS에서 제공하는 DB 엔진  </summary>

## 6. RDS에서 제공하는 DB 엔진

- MS SQL Server 
- Oracle
  - Oracle OLAP
- MySQL Server
- PostgreSQL
- MariaDB
- Amazon Aurora

- MS SQL Server, Oracle, Oracle OLAP는 오픈소스가 아니기 떄문에 라이선스 비용 추가(자신의 러이선스 사용 가능)

</details>

<details> <summary> 7. RDS의 암호화  </summary>

## 7. RDS의 암호화

- 암호화 지원
  - SQL 서버 혹은 Oracle에서는 TDE(Transparent Data Encryption) 지원
  - 모든 엔진에서 EBS 볼륨 암호화 지원
    - Default Master Key 혹은 생성한 Master Key 선택 가능
  - 자동 백업, 스냅샷, Read Replica 등에 적용됨 

</details>

<details> <summary> 8. RDS의 백업  </summary>

## 8. RDS의 백업

- 자동 백업
  - 매일마다 스냅샷을 만들고 트렌젝션 로그를 저장
  - 데이터는 S3에 저장되며 데이터베이스의 크기 만큼의 공간 점유
  - 저장된 데이터를 바탕으로 일정 기간 내의 특정 시간으로 롤백 가능
    - 다른 DB 클러스터를 새로 생성
  - 1~35일 까지 보관 지원
  - Backup을 시행할 때는 약간의 딜레이 발생 가능성
  - 기본적으로 사용 상태로 설정되어 있음
- 수동 백업(DB 스냅샷)
  - 유저, 혹은 다른 프로세스로 부터 요청에 따라 만들어지는 스냅샷
  - 데이터베이스가 삭제된 이후에도 계속 보관
  - 스냅샷의 복구는 항상 새로운 DB Instance를 생성하여 수행

</details>
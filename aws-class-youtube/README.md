
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

<details> <summary> 4. EC2로 웹서버 만들기 실습 </summary>

## 4. EC2로 웹서버 만들기 실습 

### EC2 만들기
- EC2 설정하기 -> AMI, 타입, 세부설정, 보안그룹, 키 발급
- 실행


**상세 방법**
1. aws 홈페이지 접속
2. 서비스 
3. EC2 
4. 인스턴스 시작 
5. Amazon Linux 2 AMI (HVM), SSD Volume Type(x86) 선택 
6. 프리티어 사용가능 선택, 다음: 인스턴스 세부 정보 구성 클릭 
7. 서브넷 설정 후 다음: 스토리지 추가 클릭
![image](https://user-images.githubusercontent.com/28394879/136487665-d746c5e5-c894-4719-83f1-cad9bfcdbacf.png)


8. 볼륨 유형 선택후 다음: 태그 추가 클릭
![image](https://user-images.githubusercontent.com/28394879/136487835-473944a6-53e6-4de0-9bb4-e68ba2aed85c.png)



9. 태그 설정 후 다음: 보안그룹 구성 클릭
![image](https://user-images.githubusercontent.com/28394879/136489136-a41f5e89-b804-4738-996d-9b83b250cc6d.png)

10. 보안그룹 설정 후 검토 및 시작 클릭
![image](https://user-images.githubusercontent.com/28394879/136489337-1289fbbb-23a4-47e1-80f9-b26b8778e540.png)


11. 범용(SSD)에서 부팅을 마그네틱을 이 인스턴스의 부트 볼륨으로 계속 사용 클릭 후 다음 
12. 시작하기 클릭
13. 새 키페어 다운로드 후 인스턴스 시작 
![image](https://user-images.githubusercontent.com/28394879/136489509-f63cd8c7-74a8-443f-abf7-e9625acb8d3d.png) 


### EC2에 접속
- Putty Gen을 통해 PPK파일 만들기
- Putty를 통해 접속하기
- FileZila를 통해 FTP 접속하기

```
chmod 400 lecture-test.pem
ssh -i "lecture-test.pem" ec2-user@ec2-{ip}.us-east-2.compute.amazonaws.com
```


### 웹서버 설치 및 구동
- Yum을 통해 아파치 설치
- Httpd 서비스 등록
- 새로운 인트로 페이지 생성

```
sudo -s
yum install httpd -y
service httpd start
chkconfig httpd on
cd /var/www/html
vi index.html
```

- index.html 파일 완성 후 http://{ip}/ 로 결과 확인



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

<details> <summary> 4. AMI를 통한 Backup/Scale Up 실습 </summary>

## 4. AMI를 통한 Backup/Scale Up 실습

### AMI 만들기
- 현재 EC2의 AMI를 만들어 Backup하기

1. 이미지 생성 버튼 
![image](https://user-images.githubusercontent.com/28394879/136926967-9a4d113a-a2c0-4e6d-bfd1-7339dd3f4651.png)

2. 입력 후 생성 
![image](https://user-images.githubusercontent.com/28394879/136927295-177b0a95-9bfd-4b3c-8a21-e28f47daeb92.png)




### 새로운 EC2 실행하기
- 기존의 EC2보다 더 좋은 성능의 EC2를 기존의 AMI로 실행하기

1. AMI 탭 클릭
2. 사용할 AMI이미지 선택 후 시작하기 버튼 
![image](https://user-images.githubusercontent.com/28394879/136928114-47a15a1f-d595-4785-a2de-b33191e3c0a6.png)

3. 원하는 인스턴스 종류 선택후 다음
![image](https://user-images.githubusercontent.com/28394879/136928252-5806df8e-6f9d-4a2b-b96c-d626aac85013.png)

4. 인스턴스 구성은 지금은 따로안하고 다음:스토리지 추가 버튼 클릭
5. 다음:태그 추가 버튼 클릭
6. 태그 추가 후 다음:보안 그룹 구성 버튼 클릭
![image](https://user-images.githubusercontent.com/28394879/136928697-2aec2eb2-5b30-4f46-b82f-fd65f7aedf0b.png)
7. 기존 보안 그룹 선택 후 검토 및 시작 
![image](https://user-images.githubusercontent.com/28394879/136928831-d19dd3ac-a0dc-4744-ab7b-eb7becef8d8d.png)

8. 범용 SSD 에서 부팅 설정 후 다음
![image](https://user-images.githubusercontent.com/28394879/136928967-24269dd7-d423-433d-ae56-7a0de6636f65.png)

9. 시작하기 버튼 클릭 

10. 기존 키페어 선택 후 인스턴스 시작
![image](https://user-images.githubusercontent.com/28394879/136929153-05fe4144-8d2a-433f-8657-adbdc16b45da.png)

11. 기존 인스턴스 종료
![image](https://user-images.githubusercontent.com/28394879/136929511-70db58ac-c364-4b0f-90bf-3cd67d7049ec.png)


### 동작 확인하기 
- 새로운 인스턴스의 아이피로 접속해보면 이전에 만들어 두었던 helloworld apache 서버가 잘 동작 하는 것을 알 수 있다.

</details>
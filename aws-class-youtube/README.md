
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

</details>

<details> <summary> 2. DBS/Instance Storage </summary>

</details>

<details> <summary> 3. AMI </summary>

</details>

<details> <summary> 4. AMI를 통한 Backup/Scale Up 실습 </summary>

</details>
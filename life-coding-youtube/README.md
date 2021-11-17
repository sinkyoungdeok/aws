# 1. AWS Elastic Beanstalk

<details> <summary> 1. Elastic Beanstalk이란? </summary>

## 1. Elastic Beanstalk이란?
- AWS 인프라를 자동으로 관리해주는 역할을 한다.
- 기능
  - 용량 프로비저닝
  - 로드 밸런싱
  - 조정
  - 애플리케이션 상태 모니터링

</details>

<details> <summary> 2. Elastic Beanstalk 실습 </summary>

## 2. Elastic Beanstalk 실습

1. Elastic Beanstalk 화면에서 새 애플리케이션에서 애플리케이션 이름만 지정하고 생성
2. 애플리케이션을 구체적으로 동작시킬 서버를 생성하는것을 환경생성이라고하는데, 웹서버 환경을 선택
3. 환경이름 지정, 관리형 플랫폼언어 지정, 샘플 애플리케이션으로 해두고 추가옵션 구성 클릭
4. 사전 설정: 단일 인스턴스 / 용량: 편집-> nano로 변경 / 보안: 키페어 지정 / 으로 지정해서 환경 생성
5. index.php 작성후 압축 (php서버로 실습)
6. 생성한 환경에서 업로드 및 배포 클릭해서 zip파일 업로드
![image](https://user-images.githubusercontent.com/28394879/142143339-57e59535-ce6c-4dc4-b485-a637ab82f1ed.png)
7. 업로드가 완료되면 접속해보면 우리가 작성한 것이 잘 띄워진 것을 확인할 수 있다.
8. 애플리케이션 버전으로 들어가면 원하는 버전으로 돌리거나 업그레이드 하는식으로 바로 배포할 수 있다.



</details>
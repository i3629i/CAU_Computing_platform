# 도커 사용 예제 - Wordpress실행방법
--------------------------------------------------------------------------------------------------------------------------------------------
## 환경
* OS - window10
## 필요 SW
* Window Terminal 설치
* Ubuntu 20.04 설치
* WSL Version2
* Docker Desktop 설치
--------------------------------------------------------------------------------------------------------------------------------------------

## 1. Window Terminal 설치
* Window Terminal은 윈도우 10용 cmd, 파워셸, WSL SSH지원 포함. (도스창임)   
<img src="https://user-images.githubusercontent.com/50629716/115194651-b3aaa180-a128-11eb-94d7-9a321107f986.png" width="70%" height="70%">    

## 2. WSL2 설치
* window Terminal 켜서 아래 명령어 입력 WSL2준비작업   
<img src="https://user-images.githubusercontent.com/50629716/115194972-2c116280-a129-11eb-978f-9b03751e8726.png" width="70%" height="70%">   

> dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart   
> dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart   

## 3. Ubuntu 설치
<img src="https://user-images.githubusercontent.com/50629716/115195179-67139600-a129-11eb-8083-b18c94612c76.png" width="70%" height="70%">   

## 4. WSL2 버전으로 활성화하기
* WSL 버전1이 아닌 2를 사용하기 위해 설치가 필요함 아래 사이트에 들어가 "x64 머신용 최신 WSL2 Linux 커널 업데이트 패키지" 설치후 실행

[링크]https://docs.microsoft.com/ko-kr/windows/wsl/install-win10#step-4---download-the-linux-kernel-update-package   

<img src="https://user-images.githubusercontent.com/50629716/115195459-c07bc500-a129-11eb-9fdb-7de790a45f87.png" width="70%" height="70%">   

## 5. WSL2 적용
* wsl -l -v  버전확인(version2로 나와야함)
* wsl --set-version Ubuntu 2 안나와있으면 2로 설정
* wsl --set-default-version 2 wsl실행시 기본을 2로 설정

## 6. WSL2에서 도커 데스크탑으로 서버 실행
* Docker Desktop을 깔고 설정을 들어가 아래와 같이 설정을 해준다. 자신의 WSL2의 이름을 설정해주면 터미널에서 도커 명령어 사용가능
![image](https://user-images.githubusercontent.com/50629716/115196117-8828b680-a12a-11eb-8f7a-70ef2accb1fc.png)   
   
* 설정이 완료됐으면 Docker ps사용하면 아래와 같이 나와야함
 ![image](https://user-images.githubusercontent.com/50629716/115196386-ccb45200-a12a-11eb-89a8-ec2bffe8d3cb.png)
 
## 7. 받고자 하는 도커 이미지 생성
* wordpress를 설치하려면 sql이 있어야 하기 때문에 (1) sql 설치하고 (2) wordpress설치   
* Docker compose up -d 를 통해서 해당 도커 이미지 실행!
![image](https://user-images.githubusercontent.com/50629716/115196511-f5d4e280-a12a-11eb-9a93-cf15d1c1fcf5.png)   

## 8. 실행후에
* 아래와 같이 wordpress, mysql 설치되고 포트도 열림(도커 애용하자!!)   

![image](https://user-images.githubusercontent.com/50629716/115196953-75fb4800-a12b-11eb-8361-2622de962115.png)

## 9. wordpress정상 작동함
<img src="https://user-images.githubusercontent.com/50629716/115197194-af33b800-a12b-11eb-9b6b-9fcf624bca7e.png" width="70%" height="70%">   

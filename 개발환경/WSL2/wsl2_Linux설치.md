# **[WSL2] WSL2 환경에서 Linux 배포판 설치**

WSL(Linux용 windows 하위 시스템)을 설치하여 Ubuntu 설치하기

<br/>

## **1.Linux용 windows 하위 시스템 사용 설정**

<br/>

cmd, windows Terminal, PowerShell 중 하나를 선택해 **관리자 권한**으로 실행 후, 아래 명령어를 실행합니다.
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
<br/>

## **2.pc 재부팅**

<br/>

## **3.Linux 커널 업데이트 패키지 [설치하기](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)**

<br/>

## **4.WsL2를 기본 값으로 설정**

<br/>

cmd, windows Terminal, PowerShell 중 하나를 선택해 **관리자 권한**으로 실행 후, 아래 명령어를 실행합니다.
 
 ```
 wsl --set-default-version 2
 ```

<br/>

## **5.ubuntu 설치**

<br/>

ms sotre에서 ubuntu 검색 후 자신에게 맞는 버전 설치 (20.0.4)

ubuntu 실행 후 name password 입력

<br/>

## **6.wsl실행**

<br/>

cmd, windows Terminal, Powershell 중 하나에 wsl을 치면 우분투로 이동 완료


<br/>

[참고 자료](https://cha-vi.tistory.com/entry/WSL2-WSL2-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C-Linux-%EB%B0%B0%ED%8F%AC%ED%8C%90-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0)
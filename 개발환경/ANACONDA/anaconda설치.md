 # **Anaconda WsL2 ubuntu 20,04에 설치해보기**

개발환경 구축을 위해 anaconda  wsl에 설치하기😉

<br/>

 ## **Anaconda 설치**


[아나콘다 다운로드](https://www.anaconda.com/products/individual)

아나콘다의 공식 홈페이지에서 Individual Edition 탭에서 맨 밑에 Anaconda Installers를 보면 Windows, MasOS, Linux 별 설치파일을 다운받을 수 있다. 

<br/>

Linux에 64-bit install에 우클릭 후 링크 주소 복사하기 이후 터미널을 킨 wget 이러 설치
```
wget (링크주소)
```
이후 엔터를 계속 누르고 한참 라이센스 설명이 나온다. 맨 마지막엔 yes를 입력

<br/>

밑에 멘트가 나오면 .bashrc에 환경 변수를 등록해줄까라는 내용이다 바로 **yes** 누르기 이후 wsl을 실행하면 바로 (base) 된 상대로 나온다 

```
Do you wish the installer to initialize Anaconda3 by running conda init?[yes|no]
```

이후 code . 하면 wsl+conda환경으로 vscode 실행이 된다

<br/>

[참고자료](https://thinmug.tistory.com/51)
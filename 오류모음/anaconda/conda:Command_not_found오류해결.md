 # **[Ubuntu] Anaconda  conda : command not found 오류 해결 방법**

wsl 설치 후 wget (링크) 한 뒤에 conda를 치면 **conda command not found**가 나오는분들이 4명이나 있었다 그래서 설치 오류 해결 방법 공유한다🤗

<br/>

 ## **1. 먼저 다운로드 받은 파일 삭제**

<br/>

 하도 많이 다운받아서 더러우니 먼저 아나콘다 삭제후 다시 진행한다
 ls 친 후에 설치파일 명을 복사한 후 rm -rf (설치 파일명)

 <br/>

 ```
 rm -rf Anaconda3-5.2.0-Linuz-x86_64.sh
 ```

<br/>

 ## **2. 재설치**

<br/>

설치할 때 cd ~ 를 치고 홈 디렉토리에서 실행시키자 그래야 설치파일을 깔끔하게 볼 수 있다 (홈 디렉도리에는 다른 설치 파일들이 많이 없을거다)

<br/>

```
#홈 디렉토리 이동후 재설치 (cd ~)

wegt https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh
```

<br/>

 ## **3.설치 확인**

<br/>

설치후 conda를 쳤는데도 conda:Command not found가 나왔다면 다음과 같이 진행하자
```
ls 
```

현재 경로에서 설치파일을 확인 할 수 있다. 아나콘다를 설치했음에도 불구히고 command not found 오류가 생긴다면 path 설정이 안되있는 경우라 경로 설정을 해주어야 된다.

<br/>

## **4.PATH 설정**

<br/>

anaconda3 폴더가 있는 디렉토리 즉 anaconda를 설치한 경로로 가서 진행을 해주어야 된다. 

<br/>

```
#현재 경로 찾기
pwd

source ~/.bashrc
export PATH="/[경로]/anaconda3/bin:$PATH"
```

<br/>

경로는 아나콘다를 설치한 경로로 가서 진행을 해줘야 되는데 pwd 명령어를 친 뒤 현재 경로를 파악하고 export경로를 자신의 상황에 맞게 입력해주자

<br/>

## **5. 다시 확인**

<br/>

anaconda3 폴더가 있는 디렉토리 즉 anaconda를 설치한 경로로 가서 진행을 해주어야 된다. 이후 conda를 치면 command not found 오류가 안뜰것이다. 만약에 뜬다면 vi로 경로설정을 해줘야되기에 [여기 참고](https://jisoo-coding.tistory.com/6)하자

<br/>

## **6. 가상환경 실행시키기**

<br/>

conda는 설치가 되었으니 conda를 실행시켜보자

<br/>

```
source activate base
```

뒤에 base는 처음 생성할 때 디폴트값으로 정해진건데 자기가 새롭게 만든 가상환경을 쓰고 싶음 새롭게 create 해서 뒤에 base 부분을 자기가 만든 conda가상환경명을 쓰면 된다.

<br/>

## **7. 가상환경 자동 실행**

<br/>

제대로 실행이 된다면 우분투 앞에 (base) 라고 써져있을텐데 새 명령프롬프트에서 wsl을 치고 우분투를 실행시키면 (base)부분이 없고 다시 source activate base로 실행시켜줘야 된다. 그래서 아나콘다를 자동 실행 시키기는 방법을 알아보자

<br/>

```
#처음 conda 실행시킬시 conda init 

conda init

# 자동 활성화시키기

conda config --set auto_activate_base true

```

위에 처럼 두개의 명령어를 실행시키면 우분투 환경에서 conda가 자동적으로 활성화가 된다. 만약 base 환경이 자동 활성화 되는걸 끄고 싶다면 true 부분을 false로 고치면 된다. 

<br/>

### **가지각색 오류들이 많지만 오류를 해결할 수 있는 유일한 방법은 구글링과 끈기 ... 안된다고 도망가지 말자 도망가도 언젠간 같은 오류 또 나와서 해결해야 됨😔** 

<br/>

[참고자료- conda 자동 활성화](https://sike6054.github.io/blog/etc/fourth-post/)

[아나콘다 실행 오류](https://willbesoon.tistory.com/119)

[command not found오류 참고자료1](https://jisoo-coding.tistory.com/6)

[command not found오류 참고자료2](https://starseeker711.tistory.com/182)

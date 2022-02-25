## **Scrapy 파일 Docker Image 만들고 cotainer만들어 실행하기**

<br/>

scrapy 파일을 docker image로 생성하고 이를 conainer에 담든 작업을 진행하자

<br/>

**1. Docker Image만들기**

docker image를 생성하기위해 dockerfile을 작성한다  가장 중요한점은 **Dockerfile 위치**이다

**Scrapy를 실핼 시킬 .sh 파일과 docker file은 spides 폴더 보다 상위폴도에 있어야 된다**

```
FROM python:3.10.2-slim-buster  #slim-buster을 사용해서 image 용량을 줄인다

COPY requirements.txt ./     

COPY . .

RUN pip install --upgrade pip

RUN pip install scrapy

RUN pip install requests

RUN pip install mysql-connector-python

ENTRYPOINT [ "/bin/sh","startcrawl.sh" ]  #여기서 startcraawl.sh을 실행시킨다.

```




<br/>

밑에는 인코딩 된 db 생성이다. 나는 docker로 mysql불러 오지 않는이상 인코딩 문제는 일어나지 않아 위에있는 명령어로 DB생성을 하였다

!()[]
## **Docker에서 nginx 설치하기**

<br/>

**1. 이미지 다운로드**
```
sudo docker pull nginx
```

<br/>

**2. 다운받은 이미지 확인**
```
sudo docker images
```

<br/>

**3. nginx 실행**
```
docker container run --name webserver -d -p 8888:80 nginx
```
--name : 실행할 컨테이너 이름 지정 (name 뒤에 원하는 이름 적기)

-d : 백그라운드로 실행

-p : 포트를 설정한다. 왼쪽엔 호스트 포트를 쓰고 오른쪽엔 컨테이너 포트 설정

- nginx 구동 되는지 테스트 할 땐 웹브라우저에 자신의 ip (ipconfig로 확인가능(wsl ip 사용))적고 포트 번호 적으면 된다
  
  ex) 172.22.160.1:8888 => welcome to nginx 뜨면 성공
 
 => 정상처리가 되면 컨테이너 ID가 뜬다

<br/>

**4. 실행중인 컨테이너 확인**
```
sudo docker container ps
```

<br/>

**5. nignx정지**
```
docker stop webserver(name)
```
정지된 컨테이너는 ps -a로 조회

<br>

**6. 컨테이너 실행**
```
docker start webserver
```

<br/>

[참고자료](https://velog.io/@latte_h/Docker%EC%97%90%EC%84%9C-NginX-%EC%84%A4%EC%B9%98)

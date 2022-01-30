## **Docker에서 nginx html 수정해서 띄우기**

<br/>

**1. 자기가 만든 localthost:80으로 접속해서 보이는 페이지가 nginx의 본래 index.html이다**
```
sudo docker pull nginx
```

<br/>

**2. 위치를 찾기 위해 컨테이너 내부로 들어간다**
```
docker exec -it (nginx) /bin/bash
```
가로는 컨테이너 ID이다 (ps -a로 찾자)

<br/>

**3. 해당 컨테이너 내부로 들어왔으면 index.html 찾기**
```
find / -name index.html 2>/dev/null
```
그럼 /usr/share/nginx/html/index.html <= 이런식으로 html의 위치를 찾을 수 있음


<br/>

**4. cp로 경로 복사하기**
```
docker cp (nginx):(/usr/share/nginx/html/index.html) index.html
```
exit로 파일을 빠저나온 뒤 위에 찾은 경로를 복사하자 

<br/>


**5. 제대로 복사 되었는지 확인**
```
ls-al | grep index.html 
```


<br>

**6. 그 다음 vi index.htm로 수정**

**7. 수정한 index.html 파일을 nginx 이미지 내부에 잡어넣기**
```
docker cp index.html (nginx):/usr/share/nginx/html/index.html
```

<br/>

**8. 이후 localhost:xxxx으로 접근 했을 때 처럼 페이지를 새로고침하면 바뀌어져있다.**



<br/>
<br/>


[참고자료](https://gracelove91.tistory.com/111)

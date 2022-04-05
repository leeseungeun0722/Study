[MySQL_8.x_사용자생성](https://myborn.tistory.com/12)


```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Tmddms0722@';

GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost'; 

 flush privileges;

create user 'root'@'localhost' identified by 'pass'; 
```

포트확인

 SHOW GLOBAL VARIABLES LIKE 'PORT';

 flush privileges;

 select user,authentication_string, plugin,host from mysql.user;
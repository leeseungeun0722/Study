## **MySQL 오류 모음**

<br/>

### **1 _ 로그인시 에러**

```
$ mysql -uroot -p

=> ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
```

> 해결법
<br/>

```
service mysql restart
sudo service mysql restart
```


<br/>

### **2_ ERROR 1054 (42S22): Unknown column 'password' in 'field list'**

```
$ select host, user, password from user;

=> ERROR 1054 (42S22): Unknown column 'password' in 'field list
```

> 해결법

mysql 버전 확인을 하자 mysql 8.x부터는 password가 authentication_strig로 변경 되었다.

```
select user,authentication_string, plugin,host from mysql.user;


```

<br/>

### **3_ DB생성시 오류**

```
=> mysql.connector.errors.NotSupportedError: Authentication plugin 'caching_sha2_password' is not supported
```

> 해결법

mysql 비밀 번호 정책에 어긋날 경우 (대소문자 포함, 숫자, 특수문자포함) 오류메세지 발생했다 + 그리고 한 구문을 추가해줘야 한다

```
alter user ['naverland']@['localhost'] identified with mysql_native_password by[ '변경할비번'];

```

```
DB = mysql.connector.connect(
    host = 'localhost',
    user = 'naverland',
    password = 'password',
    database = 'test',
    auth_plugin='mysql_native_password'
)
```
맨 밑에 auth_plugin='mysql_native_password' 추기하자


[참고](https://exerror.com/solved-mysql-connector-errors-notsupportederror-authentication-plugin-caching_sha2_password-is-not-supported/)

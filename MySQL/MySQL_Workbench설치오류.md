# **[이 제품의 구성 데이터가 손상되었습니다. 고객 지원 담당자에게 문의하십시오] MySQL workbench 설치 오류** 

mysql 연결이 안돼서 바보 같은 나는 mysql과 관련된 모든 파일을 삭제하고 심지어 레지스트리에 있는 mysql 경로 파일들을 싸그리 삭제했다 그리고 다시 설치하려 하니 [이 제품의 구성 데이터가 손상되었습니다. 고객 지원 담당자에게 문의하십시오] 오류 메세지와 함께 mysql workbench가 안깔리더라 ... 🙄 그래서 mysql workbench 없는 삶을 살까 하다가 설치 오류 해결법으로 해결함. 레츠고

<br/>

## **1.명령프롬프트로 관리자 권한으로 실행한 뒤 MySQL workbench 설치한 파일 경로로 이동하자**

<br/>

관리자 권한으로 cmd 실행 후 mysqlworkbench를 설치한 폴더로 이동을 하자. 나는 download 폴더에 있었다. 이동후 **/i [mysqlworkbench 설치 파일명] /l*v msilog.txt**

```
/i mysql-workbench-community-8.0.28-winx64.msi /l*v msilog.txt
```

명령어를 입력하면 해당 폴더 안에 log.txt 파일이 생성된다. 저 명령어를 쓰면 계속 손실 되었습니다 오류 메세지가 뜨는데 그건 그냥 뜨는거고 명령어 입력후 폴더를 다시 보자 그럼 msilog.txt 파일이 있을것 

<br/>

## **2.msilog.txt 확인후 레지스트리 편집기로 이동하기**

msilog.txt 파일을 열면 아래와 같은 구문이 있다. 만약 안나온다면 ? 다운로드 폴더 말고 (다운로드 폴더안에 같은 파일명으로 된 파일이 있을 수 있기 떄문) 다른 파일로 workbench 설치 파일 옮겨서 그 폴더에서 실행시켜보자.

```
MSI (c) (8C:B0) [17:07:01:165]: Unexpected or missing value (name: 'PackageName', value: '') in key 'HKLM\Software\Classes\Installer\Products\1682E5284B5FA5A43A4BA62AE7BE4F99\SourceList'

```
in key 뒷 구문을 복사하고 레지스트리 편집기를 열어 붙여넣어준다. 그럼 SourceList 폴더를 통제로 삭제해주면 된다. 그럼 하위요소들까지 사라질것. 그상태로 다시 workbench를 열면 mysql이 실해잉 될 것이다 **앞으로 레지스트리 편집기 파일 삭제는 조심히 하자** 😏

<br/>

[참고자료](https://m.blog.naver.com/dhalswjd30/222101255535)
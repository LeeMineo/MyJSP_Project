# MyJSP_Project

## Walab Tomcat 서버에 배포 및 실행테스트

- Maven deploy war file 생성 <br>
> 우측창 Maven 선택 -> Lifecycle -> package -> 우클릭, Run Maven Build 선택 <br>

- war 파일명변경 :[자신의 Walab 계정]_1.war <br>
- 자신의 Walab 계정으로 sftp 연결후, web apps 디렉토리에 war 파일업로드 <br>
> sftp p3_22100503@walab.handong.edu <br>
> ls (webapps 확인하기) <br>
> cd webapps <br>
> put ./target/demo-1.0-SNAPSHOT.war (없으면 직접 만들자) <br>
> put ./target/demo-1.0-SNAPSHOT.war p3_22100503_1.war (war파일명 변경)  <br>

> ~~터미널에서 바로 ls 해서 target으로 들어가서 생성해보자.~~<br>
> 저 경로로 파일을 put 하니까 안되서 그냥 lls -l해서 파일목록을 보고 put으로 바로 파일을 올리니까 올라가졌다!!!

- 실행테스트주소 : http://walab.handong.edu:8080/p3_22100503_1

------
# 기획

## 1.서비스 선택 > 데이터 구조 기획 
- 주제 : 내가 읽고싶은, 읽은 책 목록 정리한 사이트 제작
- 데이터 구조 : 넘버링, 책표지, 책제목, 저자, 한줄소개, 카테고리, 읽기여부, 등록일자, 수정, 삭제

- seq (넘버링) : int auto_increment
- img (책표지) : 첨부파일 
- title (책제목) : varchar(100)
- writer (저자) : varchar(30)
- content (한줄소개) : varchar (1000)
- category (카테고리) : varchar (100)
- read_yn 읽기여부 : int (0 = x , 1 = o)
- regdate (등록일자) : current_timestamp timestamp
- 수정
- 삭제 


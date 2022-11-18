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


----
# 파일 업로드 CRUD with File upload
1.FileUpload class 설계 및 제작
- com.example.img 패키지 내
- public BoardVO uploadPhoto (HttpServletRequest request)
- public static void deleteFile (HttpServletRequest request, String filename)

2. BoardDAO class 변경
- method 추가 : public String getPhotoFilename (int sid)

3. 관련 JSP 소스 변경 및 스타일 일관성 적용
- addpostform.jsp (addform.jsp): photo 내용을 파일을 선택하여 첨부하도록 변경
- addpost.jsp (add_ok.jsp): 전송된 파일을 저장하는 기능추가
- post.jsp (view.jsp): photo로 저장되어 있는 파일을 화면에 표시하도록 변경
- editform.jsp (editform.jsp) : photo파일을 보여주고, 변경할 파일을 선택하여 첨부하도록 변경
- editpost.jsp (edit_ok.jsp): 전송된 파일을 새롭게 저장하는 기능추가
- deletepost.jsp (delete_ok.jsp): 기존에 저장된 파일을 삭제하는 기능 추가


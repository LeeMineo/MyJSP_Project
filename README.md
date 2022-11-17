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

- 실행테스트주소 : http://walab.handong.edu:8080/[자신의 Walab 계정]_1

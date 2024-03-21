<h2 align="center"> 기능 소개 </h2>

```
게시글 작성 화면 
게시글 작성 데이터 컨트롤러에 가져오기
게시글 작성 데이터 DB에 저장
목록 출력 메서드 구현
목록 출력 화면 구현
게시글 조회(조회수 처리하기) 메서드 구현
게시글 조회 화면 구현
게시글 수정 메서드 구현
게시글 수정 화면 구현
게시글 삭제하기
파일첨부 메서드 구현
파일조회 메서드 구현
파일첨부 화면 구현, WebConfig 클래스 정의
다중 파일첨부 메서드 구현
다중 파일첨부 화면 구현
```

<h2 align="center"> Tools / Languages </h2>

![Front-end](https://skillicons.dev/icons?i=idea,spring,gradle,java,mysql)<br>
<img src="https://img.shields.io/badge/Spring Web-59666C?style=for-the-badge&logo=Spring&logoColor=white"/>
<img src="https://img.shields.io/badge/SpringBoot-59666C?style=for-the-badge&logo=SpringBoot&logoColor=white"/>
<img src="https://img.shields.io/badge/Mybatis-59666C?style=for-the-badge&logo=Spring&logoColor=white"/><br>
<img src="https://img.shields.io/badge/Java-59666C?style=for-the-badge&logo=Java&logoColor=white"/>
<img src="https://img.shields.io/badge/gradle-59666C?style=for-the-badge&logo=gradle&logoColor=white"/>
<img src="https://img.shields.io/badge/Lombok-59666C?style=for-the-badge&logo=Lombok&logoColor=white"/>
<img src="https://img.shields.io/badge/Tymeleaf-59666C?style=for-the-badge&logo=Tymeleaf&logoColor=white">
<img src="https://img.shields.io/badge/Mysql-59666C?style=for-the-badge&logo=MySql&logoColor=white"/>

<h2 align="center"> Table </h2>

```sql
-- board_table
 drop table if exists board_table;
 create table board_table
 (
	id bigint primary key auto_increment,
    boardTitle varchar(50),
    boardWriter varchar(20),
    boardPass varchar(20),
    boardContents varchar(500),
    boardHits int default 0,
    createdAt datetime default now(), 
    fileAttached int default 0
);
-- board_file_table
drop table if exists board_file_table;
create table board_file_table
(
    id	bigint auto_increment primary key,
    originalFileName varchar(100),
    storedFileName varchar(100),
    boardId bigint,
    constraint fk_board_file foreign key(boardId) references board_table(id) on delete cascade
);
```

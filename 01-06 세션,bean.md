# 21-01-06(세션,bean)

### 1. session 이란?

> session

- 클라이언트와 서버의 연결을 유지 시켜주는 방법 중 하나이다.
- 서버상 객체로 존재하며 서버에서만 접근이 가능하다.
- 보안이 높고 저장할 수 있는 데이터 한계가 없다.
- 웹 브라우저 당 1개씩 생성되어 웹 컨테이너에 저장된다.

프로그래밍 언어 중에 session이 중복되는 단어들이 많다. 각 session마다 의미가 다르기 때문에 어떤 언어의 session인지 분별을 잘해야 한다!

**session의 구조**

![Untitled](https://user-images.githubusercontent.com/75012998/103763259-ea1e4e00-505c-11eb-8d08-8aae17684f1c.png)

---

### 2. DBMS의 의미와 종류는?

> DBMS(DataBase Management System)

- 데이터베이스를 관리하며 응용 프로그램들이 데이터베이스를 공유하며 사용할 수 있는 환경을 제공하는 소프트웨어이다.

![Untitled 1](https://user-images.githubusercontent.com/75012998/103763239-e68ac700-505c-11eb-91f7-4005cffda416.png)

**종류**

 1. Oracle

- 오라클에서 만들어 판매중인 상업용 데이터베이스
- 오픈소스가 아닌 비공개 소스로 운영
- MS_SQL, MY_SQL보다 대량의 데이터를 처리하기 좋음

 2. MY_SQL

- MySQL사에서 개발, 썬마이크로시스템즈를 거쳐 현재 오라클에 흡수 합병되었다.
- 오픈소스로 이루어져 있는 무료 프로그램

 3. MS_SQL

- 마이크로소프트 사에서 개발한 상업용 데이터베이스
- 비공개 소스로 폐쇄적인 정책

---

### 3. session id란?

> session ID

- 컴퓨터 시스템, 일반적으로 서버가 특정 세션 중에 단일 사용자의 작업을 식별하고 추적할 수 있는 방법이다.
- 인터넷에서 다양한 웹 사이트에 의해 광범위하게 사용되며 쿠키 또는 이를 추적하기 위한 URL과 같은 다양한 방법을 사용할 수 있다.

---

### 4. 에러 페이지 처리 방법 2가지를 설명하시오?

```java
1. page 디렉티스 errorPage속성을 이용한 에러처리
 EX) <%@page errorPage = "error.jsp"(에러페이지 주소) %>
- 특정 페이지에서 에러가 났을 경우 처리할 때 주로 사용한다.
- 에러를 처리 할 특정페이지의 page디렉티브에 errorPage를 추가하면 된다.
- 페이지에서 에러가 날 경우 지정된 페이지를 화면에 나타나게 함. 

* 에러페이지 생성 : <%@page isErrorPage = "true" %>
- 에러를 나타낼 페이지에 위 디렉티스를 추가한다.

2. web.xml에서 에러처리
EX)
<error-page>
	<error-code>404</error-code> ->에러코드
	<location>/error/error404.jsp</location> -> 에러페이지 주소
</error-page>

- web.xml 파일에서 <error-page> 태그를 통해 에러를 처리한다.
- 404 에러가 나게 되면서 지정된 페이지를 보여주게 된다.
```

---

### 5. bean 이란?

> Bean

- Java언어의 데이터(속성)와 기능(메소드)으로 이루어진 클래스이다.
- 반복적인 작업을 효율적으로 하기 위해 사용한다.
- 액션태그를 이용하여 getter,setter 클래스를 생성한다.

**사용법**

```java
<jsp:useBean> 액션태그를 이용하여 사용한다.
EX) <jsp:useBean id = "빈 이름" class = "자바빈 클래스명" scope = "범위"/>
- id: 생성할 객체(인스턴스) 이름을 정의
- class : 객체를 생성할 클래스명(패키지명.클래스명으로 설정)을 정의
- scope : 자바빈 객체가 공유되는 범위를 지정(기본값 : page)

<jsp:setProperty> : 자바빈의 프로퍼티의 값을 저장하기 위한 태그
EX) <jsp:setProperty name ="객체명" property = "프로퍼티 명" value = "설정 값">
- name : userBean을 이용해 생성한 객체이름을 명시
- property : 값을 저장할 프로퍼티의 이름을 명시
- value : 저장할 값을 정의

<jsp:getProperty> : 자바빈의 프로퍼티 값을 가져오기 위한 태그
EX) <jsp:getProperty name = "객체명" property = "프로퍼티 명">
- name : 사용할 객체 이름을 명시
- property : 가져올 프로퍼티 이름을 명시 
```

---

### 6. 아래 문제를 푸시오.

![Untitled 2](https://user-images.githubusercontent.com/75012998/103763243-e7bbf400-505c-11eb-9397-cfa619953e6d.png)

![Untitled 3](https://user-images.githubusercontent.com/75012998/103763251-e985b780-505c-11eb-8370-5518c8f90c74.png)

![Untitled 4](https://user-images.githubusercontent.com/75012998/103763257-ea1e4e00-505c-11eb-87df-fa582fbb91c1.png)

- JSP 소스 파일
```java
<%@ page language="java" contentType="text/html; charset=EUC-KR"
    pageEncoding="EUC-KR"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
	<style>
		button{
			width : 100px;
			height : 30px;
			margin-left : 280px;
		}
		
		a{
			text-decoration : none;
		}
		.result{
			border : 1px solid black;
			width : 700px;
			height : 100px;
			line-height : 100px;
			background-color : beige;
			font-size : 30px;
			font-family : fantasy;
			color : #FFC6C3;
			text-align : center;
		}
		
		 img{
			width : 250px;
			height : 250px;
			
		}
	
	</style>
	
</head>
<body>
	<%! int player,com; %>
	
	<% 
		player = Integer.parseInt(request.getParameter("player"));
		com = (int)(Math.random()*3) + 1;
		
		if(com == 1){
			%>
			COM : <img src = "https://img.lovepik.com/element/40135/5246.png_300.png">
			<%
		}else if(com == 2){
			%>
			COM : <img src = "https://data.ac-illust.com/data/thumbnails/a6/a6864b8e323722d8f0b6ad20be822f52_t.jpeg">
			<%
		}else{
			%>
			COM : <img src = "https://file.edupre.co.kr/plan/clips/thumb/5/clips_20150820135918_6456.jpg.thumb.300">
			<%
		}
		
		if(player == 1){
			%>
			Player : <img src = "https://img.lovepik.com/element/40135/5246.png_300.png">
			<%
		}else if(player == 2){
			%>
			Player : <img src = "https://data.ac-illust.com/data/thumbnails/a6/a6864b8e323722d8f0b6ad20be822f52_t.jpeg">
			<%
		}else{
			%>
			Player : <img src = "https://file.edupre.co.kr/plan/clips/thumb/5/clips_20150820135918_6456.jpg.thumb.300">
			<%
		}
		
		
		%>
		<%
		switch(player){
		case 1:
			if(player == 1){
				if(com == 2){
					%>
					<div class = "result"><%="결과 : Player 승리~" %></div>
					<%
				}else if(com == 3){
					%>
					<div class = "result"><%="결과 : Player 패배...ㅠㅠ" %></div>
					<%
				}else{
					%>
					<div class = "result"><%="결과 : 무승부" %></div>
				<%
				}
				break;
			}
		
		case 2:
			if(player == 2){
				if(com == 3){
					%>
					<div class = "result"><%="결과 : Player 승리~" %></div>
					<%
				}else if(com== 1){
					%>
					<div class = "result"><%="결과 : Player 패배...ㅠㅠ" %></div>
					<%
				}else{
					%>
					<div class = "result"><%="결과 : 무승부" %></div>
				<%
				}
				break;
			}
		case 3:
			if(player == 3){
				if(com == 1){
					%>
					<div class "result"><%="결과 : Player 승리~" %></div>
					<%
				}else if(com == 2){
					%>
					<div class "result"><%="결과 : Player 패배...ㅠㅠ" %></div>
					<%
				}else{
					%>
					<div class "result"><%="결과 : 무승부" %></div>
				<%
				}
				break;
			}
		}
	
	%>
	
	<button><a href = "Game.html">다시하기</a></button>
</body>
</html>
```
- HTML & CSS파일
```java
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
	<style>
		#boad{
			border : 1px solid beige;
			width : 600px;
			height : 350px;
			background-color : #FFC6C3
		}
		
		#boad div:nth-child(1){
			border : 7px groove beige;
			text-align : center;
			margin : 0 auto;
			margin-top : 15px;
			width : 300px;
			height : 50px;
			line-height : 50px;
			font-size : 25px;
			font-family : fantasy;
			font-weight : bold;
			color : beige;
		}
		
		#boad div img{
			border : 6px dashed beige;
			margin-top : 15px;
			margin-left : 45px;
			width : 500px;
			height : 150px;
		}
		
		#boad div:nth-child(3){
			border : 6px double beige;
			text-align : center;
			margin : 0 auto;
			width : 500px;
			height : 40px;
			line-height : 40px;
		}
		
		
	</style>
</head>
<body>
	<form action = "GamePrint.jsp" method = "post">
	<div id = "boad">
		<div>가위 바위 보 게임!</div>
		<div><img src = "가위바위보.jfif"></div>
		<div>
			<select name = "player">
				<option value = "2">가위</option>
				<option value = "1">바위</option>
				<option value = "3">보</option>
			</select>
		<input type ="submit" value = "경기시작">
		</div>
	</div>
</body>
</html>
```
- 결과

![결과 2](https://user-images.githubusercontent.com/75012998/103852698-be987380-50ef-11eb-8c9d-7a7639cc1ab5.png)

![결과 1](https://user-images.githubusercontent.com/75012998/103852696-bd674680-50ef-11eb-81b6-1dea0251f493.png)

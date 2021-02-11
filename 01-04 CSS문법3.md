# 21-01-04(CSS문법3)

### 1. box-sizing 속성들에 대하여 설명하시오.

> content-box

1. CSS 표준이 정의한 초기 기본값
2. width와 height 속성이 콘텐츠 영역만 포함하고 안팎 여백과 테두리는 포함하지 않는다.

> border-box

1. width와 height 속성이 안쪽 여백과 테두리는 포함하고, 바깥 여백은 포함하지 않는다.
2. 안쪽 여백과 테두리가 요소 상자 안에 위치한다.

box-sizing이란? 박스의 크기를 어떤 것을 기준으로 계산할 지를 정하는 속성이다. 기본값으로 content-box의 속성을 가지고 있다.

![01-04 bc5205942f744952b7534526010d92cd](https://user-images.githubusercontent.com/75012998/103526722-adb7ea00-4ec4-11eb-91d7-fcad1a5f9f0b.png)


---

### 2. margin 과 padding의 차이는?

> margin

1. 블록의 외부 간격을 조절해주는 속성 

> padding

1. 블록의 내부 간격을 조절해주는 속성

![01-04 bc5205942f744952b7534526010d92cd 1](https://user-images.githubusercontent.com/75012998/103526754-b7d9e880-4ec4-11eb-9fa4-d7e1cb6222c2.png)

---

### 3. 내장객체에 대하여 설명하시오.

내장 객체란?? JSP에서 내장객체는 JSP페이지 내에서 제공하는 특수한 레퍼런스타입의 변수이다. 하지만 어떠한 변수선언이나 객체생성없이 사용할 수있는 이유는 JSP페이지가 서블릿으로 변환될 때 JSP컨테이너가 자동적으로 제공하기 때문이다. 

**내장객체의 주요 키워드**

1. **request** : 웹 브라우저의 요청 정보를 저장하는 객체

리턴타입 : javax.servlet.http.httpServletRequest

 2. **response** : 웹 브라우저의 요청에 대한 응답 정보를 저장하는 객체

리턴타입 : javax.servlet.http.httpServletResponse

 3. **out** : JSP 페이지의 출력할 내용을 가지고 있는 출력 스트림 객체

리턴타입 : javax.servlet.jsp.JspWriter

 4. **session** : 하나의 웹 브라우저 내에서 정보를 유지하기 위한 세션 정보를 저장하고 있는 객체

리턴타입 : javax.servlet.http.HttpSession

 5. **application** : 웹 어플리케이션 Context의 정보를 담고 있는 객체

리턴타입 : javax.servlet.ServletContext

 6. **pageContext** : JSP 페이지에 대한 정보를 저장하고 있는 객체

리턴타입 : javax.servlet.jsp.PageContext

 7. **page** : JSP 페이지를 구현한 자바 클래스 객체

리턴타입 : java.lang.Object

 8. **config** : JSP 페이지에 대한 설정 정보를 담고 있는 객체

리턴타입 : javax.servlet.ServletConfig

 9 . **exception** : JSP페이지에서 예외가 발생한 경우 사용하는객체

리턴타입 : java.lang.Throwable

---

### 4.구구단을 세로로 나타내도록 jsp 로 짜시오.

- **out.println 을쓰지 말고 <%= expression을 사용 하시오.**
- JSP 소스코드

    ```html
    <%@ page language="java" contentType="text/html; charset=EUC-KR"
        pageEncoding="EUC-KR"%>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<h1>구구단 출력!</h1>
    	
    	<table border = 1>
    	<% 
    		for(int i=1 ; i <= 9 ; i++){
    	%>
    		<tr>
    	<% 
    			for(int j=2 ; j <= 9 ; j++){
    	 %>
    	 		<td>
    	 		<%= j + "x" + i + "=" + (j*i) %>
    	 		</td>
    	 <% 
    			}
    		} 
    	%>
    		</tr>
    	</table>
    	
    </body>
    </html>
    ```

- 결과

    ![_](https://user-images.githubusercontent.com/75012998/103526786-c0322380-4ec4-11eb-93c0-662fc661d1d5.png)

---

### 5.redirect forward 의 차이는?

> forward

1. WAS의 서블릿이나 JSP가 요청을 받은 후 그 요청을 처리하다가, 추가적인 처리를 같은 웹 어플리케이션 안에 포함된 다른 서블릿 이나 JSP에게 위힘하는 경우이다.

    ![01-04 bc5205942f744952b7534526010d92cd 3](https://user-images.githubusercontent.com/75012998/103527069-261eab00-4ec5-11eb-9fe3-bf7538ad2c98.png)

> redirect

1. 서버가 클라이언트에게 어떤 URL로 이동하라는 요청을 보내는 것
     
     ![01-04 bc5205942f744952b7534526010d92cd 2](https://user-images.githubusercontent.com/75012998/103526864-dc35c500-4ec4-11eb-9ea5-eca60422812f.png)

**redirect와 forward의 이해를 위한 예**

![리디렉트와포워드](https://user-images.githubusercontent.com/75012998/103597755-5194aa80-4f44-11eb-96a9-287b7a2b9871.png)


---

### 6. 아래 문제를 푸시오.

![01-04 12](https://user-images.githubusercontent.com/75012998/103527128-3c2c6b80-4ec5-11eb-8543-4c3ebe6fbefc.png)

- 1번 HTML 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#nav{
    			border : 1px solid #cccccc;
    			margin : 0 auto;
    			width : 800px;
    			overflow : hidden
    		}
    		
    		#nav div{
    			float : left;
    			border-top : 1px solid #cccccc;
    			border-bottom : 1px solid #cccccc;
    			width : 150px;
    			height : 100px;
    			line-height : 100px;
    			margin : 5px;
    			text-align : center;
    			font-size : 20px;
    		}

    		#nav a{
    			text-decoration : none;
    			color : black;
    		}
    	</style>
    </head>
    <body>
    	<div id = "nav">
    		<div><a href = "#">menu1</a></div>
    		<div><a href = "#">menu2</a></div>
    		<div><a href = "#">menu3</a></div>
    		<div><a href = "#">menu4</a></div>
    		<div><a href = "#">menu5</a></div>
    	</div>
    </body>
    </html>
    ```

- 결과

    ![01-04 1](https://user-images.githubusercontent.com/75012998/103527148-43537980-4ec5-11eb-9a71-c530c36e5191.png)

- 2번 HTML 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#nav{
    			border : 1px solid #cccccc;
    			margin : 0 auto;
    			width : 800px;
    			overflow : hidden
    		}
    		
    		#nav div:nth-child(1){
    			border : 1px solid white;
    			text-align : center;
    			font-size : 30px;
    			height : 150px;
    			line-height : 150px;
    			text-decoration : underline;

    		}
    		#nav div:nth-child(2){
    			border : 1px solid white;
    			font-size : 20px;
    			margin : 5px;
    		}
    		#nav div:nth-child(3){
    			border : 1px solid white;
    			margin : 5px;

    		}
    		#nav div:nth-child(4){
    			border : 1px solid white;
    			text-align : right;
    			margin : 10px;
    			font-size : 20px;
    		}
    		#nav div:nth-child(5){
    			border-top : 2px solid #cccccc;
    			margin : 10px;
    			text-align : center;
    			font-size : 25px;
    			height : 100px;
    			line-height : 100px;
    		}
    		
    		a {
    			text-decoration : none;
    		}
    		
    	</style>
    </head>
    <body>
    	<div id = "nav">
    		<div>HTML5,CSS3 Document</div>
    		<div>To. all member</div>
    		<div>html5,CSS5 study is very easy</div>
    		<div>Form.SBA</div>
    		<div><a href = "http://www.sba.seoul.kr" target = "_black">서울산업진흥원</a></div>
    	</div>
    </body>
    </html>
    ```

- 결과

   ![01-04 2](https://user-images.githubusercontent.com/75012998/103527168-48b0c400-4ec5-11eb-8872-ba97361a8551.png)

---

![01-04 3png](https://user-images.githubusercontent.com/75012998/103527202-55351c80-4ec5-11eb-8072-855000d9a768.png)

- 3번 HTML소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#nav {
    			border : 1px solid black;
    			width : 800px;
    			height : 450px;
    			margin : 0 auto;
    		}
    		
    		#nav div:nth-child(1){
    			border : 2px solid #cccccc;
    			width : 780px;
    			height : 70px;
    			line-height : 70px;
    			margin-top : 20px;
    			margin-bottom : 20px;
    			margin-left : 10px;
    			font-size : 30px;
    			font-weight : bold;
    			color : green;
    		}
    		
    		#nav p{
    			margin-left : 10px;
    		}

    	</style>
    </head>
    <body>
    	<div id = "nav">
    		<div>세계 3대 미항</div>
    		<div><image src = "리오데자네이로1.jpg" width = "630px" height = "210px" style = "margin-left : 10px;"></div>
    		<p>시드니(Sydney), 호주</p>
    		<p>리우데자네이루(Rio de Janeiro),브라질</p>
    		<p>나폴리(Napoles),이탈리아</p>
    	</div>
    </body>
    </html>
    ```

- 결과

    ![01-04 3번답](https://user-images.githubusercontent.com/75012998/103602180-af2df480-4f4e-11eb-8760-33c21b9e8d7b.png)

---

![01-04 42](https://user-images.githubusercontent.com/75012998/103527225-5cf4c100-4ec5-11eb-85c9-f48bde5115c6.png)

![01-04 4](https://user-images.githubusercontent.com/75012998/103527262-6847ec80-4ec5-11eb-8894-464dfc5fe110.png)

- JSP 소스코드

    ```html
    <%@ page language="java" contentType="text/html; charset=EUC-KR"
        pageEncoding="EUC-KR"%>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<form action = "JspTest.jsp" method = "post">
    		이름 : <input type = "text" name = "uname" size = "5"><br/>
    		아이디 : <input type = "text" name = "uid" size = "5"><br/>
    		비밀번호 : <input type = "password" name = "upw" size = "5"><br/>
    		취미 : <input type = "checkbox" name = "hobby" value = "read">독서
    			<input type = "checkbox" name = "hobby" value = "cook">요리
    			<input type = "checkbox" name = "hobby" value = "run">조깅
    			<input type = "checkbox" name = "hobby" value = "swim">수영
    			<input type = "checkbox" name = "hobby" value = "sleep">취침<br/>
    		전공 : <input type = "radio" name = "major" value = "kor">국어
    			<input type = "radio" name = "major" value = "eng">영어
    			<input type = "radio" name = "major" value = "math">수학
    			<input type = "radio" name = "major" value = "design">디자인<br/>
    		<select name = "protocol">
    			<option name = "http">http</option>
    			<option name = "ftp">ftp</option>
    			<option name = "smtp">smtp</option>
    			<option name = "pop">pop</option>
    		</select>
    		<input type = "submit" value = "전송">
    		<input type = "reset" value = "초기화">		
    	
    	</form>
    </body>
    </html>
    ```

- JSP 소스코드 2

    ```html
    <%@page import = "java.util.Arrays"%>
    <%@ page language="java" contentType="text/html; charset=EUC-KR"
        pageEncoding="EUC-KR"%>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    <%!
    	String name,id,pw,major,protocol;
    	String[] hobbys;
    %>
    <%
    	response.setContentType("text/html; charset = EUC-KR");
    	request.setCharacterEncoding("EUC-KR");
    %>
    <% name = request.getParameter("uname"); 
        id = request.getParameter("uid");   
        pw = request.getParameter("upw");
        hobbys = request.getParameterValues("hobby");
        major = request.getParameter("major");
        protocol = request.getParameter("protocol"); 
    %>
      
   이름 : <%= name %><br/>
   아이디 : <%= id %><br/>
   비밀번호 : <%= pw %><br/>
   취미 : <%= Arrays.toString(hobbys) %><br/>
   전공 : <%= major %><br/>
   프로토콜 : <%= protocol %>
    	
    </body>
    </html>
    ```

- 결과

    ![01-04 4 1](https://user-images.githubusercontent.com/75012998/103527273-6ed66400-4ec5-11eb-9f12-1aa00b777a30.png)

    ![01-04 42 1](https://user-images.githubusercontent.com/75012998/103527244-61b97500-4ec5-11eb-8b2b-8a2f519f5660.png)

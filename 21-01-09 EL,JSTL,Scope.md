# 2021.01.09  EL,JSTL,Scope

### 1. el 이란 무엇인가?

> EL(Expression Language)

- 자바 빈의 프로퍼티, 값을 JSP의 표현식이나 액션태그를 사용하는 것보다 쉽고 간결하게 꺼낼수 있게 하는 기술이다.

**표기법**

```sql
1. ${ }
- JSP가 실행될 때 즉시 반영된다.
- 객체 프로퍼티 값을 꺼낼때 주로 사용

2. #{ }
- 시스템에서 필요하다고 판단될 때 그 값을 사용한다.
- 사용자가 입력값을 객체의 프로퍼티에 담는 용도로 주로 사용
```

**내장객체**

1. pageScope : 페이지 Scope에 접근
2. requestScope : 리퀘스트 Scope에 접근
3. sessionScope : 세션 Scope에 접근
4. applicationScope : 어플리케이션 Scope에 접근
5. param : 파라미터값 얻어올 때(1개의 key,1개의 value)
6. paramValues : 파라미터값 배열로 얻어올때 (1개의 key, 여러개의 value)
7. header : 헤더값 얻어올때 (1개의 key,1개의value)
8. headerValues : 헤더값 배열로 얻어올때(1개의 key,여러개의 value)
9. cookie : ${cookie.key값,value값}으로 쿠키값 조회
10. initParam : 초기 파라미터 조회
11. pageContext : 페이지 컨텍스트 객체를 참조

---

### 2. jstl 문법에 대하여 설명하시오.

> JSTL(Jsp Standard Tag Library)

- 연산이나 조건문,반복문등을 편하게 처리할 수 있는 태그

**태그 종류**

```html
1. <c:set> : 변수의 선언과 초기화 태그
ex) <c:set var = "변수명" value = "변수값"/>

2. <c:out> : 출력문을 사용할 때 쓰는 태그
ex) <c:out value = "출력할 값"/>

3. <c:remove> : 한 영역의 변수명을 지우는 태그
ex) <c:remove var = "변수명" scope = "영역"/>

4. <c:if>
ex) <c:if test = "조건식" var = "조건을 검사하고 return되는 bool값을 저장할 변수" scope = "bool변수가 사용될 범위"/>

5. <c:choose>
ex) <c:when test = "조건식"/><c:orderwise/>

6. <c:foreach>
ex) <c:foreach begin = "시작값" end = "끝 값" step = "증가값" var = "count값이 저장될 변수"/>
		<c:foreach var = "변수" items = "배열 or 컬렉션">

7. <c:forTokens>
ex) <c:forTokens items = "배열 or 컬렉션" delims = "구분자" var = "" begin = "" end = "" step = ""/>

8. <c:catch>
ex) <c:catch var = "에러명"></c:catch>
```

---

### 3. scope 에 대하여 설명하시오.

> Scope

- 웹 서버에서 객체 또는 변수가 생성된 후 유효할 수 있는 범위를 말한다.

**종류**

 **1. page**

- 실제 선언된 jsp 페이지 내에서만 사용할 수 있는 것.
- JSP페이지에서 PageContext라는 내장객체로 사용가능하다.
- PageContext이름.setAttribute(), pageContext이름.getAttribute()의 방법으로 사용한다.

 **2. request**

- 클라이언트로부터 하나의 요청이 들어와서 서버가 일을 수행한 후 응답을 보낼 때까지 계속 사용할 수 있는 scope
- Web container 안에 있는 servlet에 대한 http요청을, WAS가 받아서 웹 브라우저에게 응답할 때까지 변수 값을 유지하고자 할 경우 사용한다.
- JSP에서는 내장변수, Servlet에서는 HttpServletRequest 객체를 사용한다.

 **3. session**

- session객체가 만들어져서 소멸할 때까지의 scope
- 웹 브라우저 별로 변수를 관리하고자 할 경우 사용한다.
- JSP에서는 내장변수, Servlet에서는 HttpServletRequest의 getSession()의 메소스를 이용하여 session객체를 얻는다.

 **4. application**

- 하나의 application이 생성되고 소멸될 때까지 계속 유지.
- Eclipse에서 하나의 프로젝트가 하나의 application이고 하나의 서버에는 여러 개의 웹 어플리케이션이 존재할 수 있다.
- JSP에서는 application 내장 객체를 이용, Servlet에서는 getServletContext()메소드를 이용하여 application 객체를 이용한다.

---

### 6. 아래 문제를 푸시오.

![_1](https://user-images.githubusercontent.com/75012998/104305699-580cbe80-5510-11eb-9647-ddf9dda337be.png)

- HTML & CSS 소스코드

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="EUC-KR">
  <title>Insert title here</title>
  	<style>
  		table{
  			border: 1px solid blue;
  		}
  		
  		h1{
  			color : blue;
  		}
  	</style>
  </head>
  <body>
  	<h1>성적입력</h1><br/>
  	<form action = "gradePrint.jsp" method = "post">
  	<table border = "1">
  		<tr>
  			<td colspan = "2">학번</td>
  			<td><input type = "text" name = "classNum"></td>
  		</tr>
  		<tr>
  			<td rowspan = "3">과목</td>	
  			<td>Java</td>
  			<td><input type = "text" name = java></td>
  		</tr>	
  		<tr>
  			<td>Database</td>
  			<td><input type = "text" name = "db"></td>
  		</tr>	
  		<tr>
  			<td>JSP</td>
  			<td><input type = "text" name = "jsp"></td>
  		</tr>
  		<tr>	
  			<td><input type = "submit" value = "전송"></td>
  		</tr>
  	</table>
  	</form>
  </body>
  </html>
  ```

- JSP 소스코드

  ```java
  <%@ page language="java" contentType="text/html; charset=EUC-KR"
      pageEncoding="EUC-KR"%>
  <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
  <jsp:useBean id = "grade" class ="test.bit.ex.Grade" scope = "page"></jsp:useBean>    
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="EUC-KR">
  <title>Insert title here</title>
  	<style>
  		#tb {
  			border: 2px solid black;
  		}
  		#tb .d1{
  			font-weight : bold;
  		} 
  	</style>
  </head>
  <body>
  	<table id = "tb" border = "1">
  		<tr class = "r1">
  			<td colspan = "2">학번</td>
  			<jsp:setProperty name = "grade" property = "classNum" value = "${param.classNum }" />
  			<td class = "d1">${grade.classNum }</td>
  		</tr>
  		<tr class = "r1">
  			<td rowspan = "3">과목</td>	
  			<jsp:setProperty name = "grade" property = "java" value = "${param.java }" />
  			<td>Java</td>
  			<td class = "d1">${grade.java }</td>
  		</tr>	
  		<tr class = "r1">
  			<td>Database</td>
  			<jsp:setProperty name = "grade" property = "db" value = "${param.db }" />
  			<td class = "d1">${grade.db }</td>
  		</tr>	
  		<tr class = "r1">
  			<td>JSP</td>
  			<jsp:setProperty name = "grade" property = "jsp" value = "${param.jsp }" />
  			<td class = "d1">${grade.jsp }</td>
  		</tr>
  		<tr class = "r1">
  			<td colspan = "2">평균점수</td>
  			<td style = "color : red; font-weight : bold;" ><c:out value = "${grade.getArea() }" /></td>
  		</tr>
  		<tr class = "r1">	
  			<td><button><a href = "gradeInfo.html">입력화면</a></button></td>
  		</tr>
  	</table>
  </body>
  </html>
  ```

- JAVA BEAN 소스코드

  ```java
  package test.bit.ex;
  
  public class Grade {
  	private int cNum;
  	private int java;
  	private int db;
  	private int jsp;
  	
  	public int getClassNum() {
  		return cNum;
  	}
  	public void setClassNum(int cNum) {
  		this.cNum = cNum;
  	}
  	public int getJava() {
  		return java;
  	}
  	public void setJava(int java) {
  		this.java = java;
  	}
  	public int getDb() {
  		return db;
  	}
  	public void setDb(int db) {
  		this.db = db;
  	}
  	public int getJsp() {
  		return jsp;
  	}
  	public void setJsp(int jsp) {
  		this.jsp = jsp;
  	}
  	public double getArea() {
  		return (java + db + jsp) / 3.0;
  	}
  	
  }
  ```

- 결과

![Untitled](https://user-images.githubusercontent.com/75012998/104305688-55aa6480-5510-11eb-8f5a-1b7859e90591.png)

![Untitled 1](https://user-images.githubusercontent.com/75012998/104305698-580cbe80-5510-11eb-8068-03dd0cc9f25b.png)

---

![Untitled 2](https://user-images.githubusercontent.com/75012998/104305696-57742800-5510-11eb-8e04-0e6645ff6354.png)

![Untitled 3](https://user-images.githubusercontent.com/75012998/104305693-56db9180-5510-11eb-8434-1e3982efda71.png)

- 결과

구현중...

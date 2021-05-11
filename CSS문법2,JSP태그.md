# 20-12-31(CSS문법2)

### 1. css 에서의 display 종류와 속성에 대하여 설명하시오.

> block

- 기본적으로 가로 영역 전체를 차지하며 다음 블록은 줄바꿈이 된다.
- width & height의 속성을 지정할 수 있다.

> inline

- 줄을 바꾸지 않고 다른요소와 함께 한 줄에 위치하려는 속성이다.
- width & height의 속성을 지정할 수 없다.

> inline-block

- inline속성처럼 전,후 줄바꿈 없이 한 줄에 나란히 배치된다.
- width & height의 속성을 지정할 수 있다.

---

### 2. px 과 em 의 차이는?

> px

- 표시장치(모니터)를 따라서 상대적인 크기를 갖는다.

> em

- 지정되거나 상속받은 요소에 대한 백분율 상대 크기

**CSS의 크기단위**

 ***1. 상대단위***

- 부모 요소나 다른요소의 크기에 영향을 받아 상대적으로 크기가 변한다.
- 반응형 웹사이트에 자주 사용된다.
- ex) em, ex, px, %등이 있다.

 ***2. 절대단위***

- 고정된 값을 출력하며 절대 크기가 변하지 않는다.
- 크기가 가변적인 웹사이트일 경우 유용하나,반응형 사이트에서는 적용하기 위해 과정이 매우 복잡한 하다는 단점이 있다.
- ex) in, cm, mm, pt, pc등이 있다.

---

### 3. inline-block 태그의 종류는?

 **1. button**

- 클릭할 수 있는 버튼을 정의할 때 사용한다.
- 항상 type속성을 지정하고 써야한다.

 **2. select**

- 원하는 값을 선택할 수있는 입력폼을 제공한다.
- option태그와 함께 사용된다.

---

### 4. opacity 속성의 사용법은?

> opacity

- 투명도를 조절하는 속성이다.
- 1은 완전히 불투명하고 0은 완전히 투명한 단계이다.(기본값 : 1)

**사용법**

<img width="659" alt="_0" src="https://user-images.githubusercontent.com/75012998/103525103-0934a880-4ec2-11eb-9424-1abeaee33a18.png">

<img width="657" alt="_0 3" src="https://user-images.githubusercontent.com/75012998/103525080-fde17d00-4ec1-11eb-9624-f89f71a016d7.png">

<img width="659" alt="_1" src="https://user-images.githubusercontent.com/75012998/103525120-10f44d00-4ec2-11eb-9a50-937653031a5d.png">

---

### 5. display:none 과 visibility:hidden 의 차이는?

> display : none

- block이 아예 사라지게 하는것, 보이지도 않고 공간도 차지하지 않는다.

> visibility : hidden

- block이 보이지 않지만 공간은 존재한다, width와 height값을 지정하였다면 그만큼의 공간을 차지한다.

**none과 hidden의 예**

<img width="511" alt="display" src="https://user-images.githubusercontent.com/75012998/103525144-1b164b80-4ec2-11eb-99de-87c87e38c59b.png">

---

### 6. 아래의 동영상 사이트를 시청하시오.

[[ㅇ] 오버플로우 overflow | 코딩가나다 | 빔캠프](https://www.youtube.com/watch?v=O-n1EjDEuIc)

---

### 7. 동적문서와 정적문서의 차이는?

> 동적문서

- 클라이언트가 웹사이트에 접속했을 때 어떠한 페이지를 열면 매번 새로운 페이지를 보여주고 내용도 달라지는 웹문서이다.

<img width="377" alt="12-31 d1845d9613854c92bd09ca841d212413 1" src="https://user-images.githubusercontent.com/75012998/103523498-451a3e80-4ebf-11eb-9d6e-3eb8972b8a66.png">

> 정적문서

- 클라이언트가 웹사이트에 접속 했을 때 어떠한 페이지를 열어도 변하지 않고 똑같은 내용만 보여주는 웹문서이다.

<img width="512" alt="12-31 d1845d9613854c92bd09ca841d212413" src="https://user-images.githubusercontent.com/75012998/103523508-49465c00-4ebf-11eb-940a-64189bb5d03d.png">

### 8. 아래를(JSP 태그) 설명하시오.

> 스크립트릿

- JSP에서 자바코드를 선언할 때 가장 많이 사용하는 태그

**사용법**

 1. (<% %>)

> 선언

- 문서 전체에 사용되기 때문에 전역의 개념으로 사용한다.
- 변수나 메소드등을 선언하기위해 사용한다.

**사용법**

 1. (<%! %>)

> 표현식

- 결과값을 출력하기 위해 사용하며, String값으로 출력된다.

**사용법**

 1. (<%= %>)

> 지시자

- JSP페이지 처리에 필요한 정보나 다른 JSP파일을 include할 때 사용한다.
- 전체적인 속성을 지정할 때 사용한다.

**사용법**

 1.(<%@page %>) : 해당 페이지의 전체적인 속성 지정하며, 주로 import문을 사용한다.

 2.(<%@include %>) : 별도의 페이지나 현재 페이지에 삽입.

> 액션태그

- JSP페이지 내에서 어떤 동작을 하도록 지시하는 태그이다.
- 페이지 이동이나, include,Bean태그 등과 사용된다.

> 주석

- 브라우저 상에서 소스보기를 했을 때 코드가 주석을 선언한 코드는 보이지 않는다.

**사용법**

 1.  (<!— —>)

---

### 9. 아래 문제를 푸시오.

![12-31_1](https://user-images.githubusercontent.com/75012998/103525175-29646780-4ec2-11eb-8fea-98e25379688f.png)

- 9 - 1번 위 문제를 servlet으로 작성 하시오.
- servlet 소스코드

    ```jsx
    import java.io.IOException;
    import java.io.PrintWriter;

    import javax.servlet.ServletException;
    import javax.servlet.annotation.WebServlet;
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;

    /**
     * Servlet implementation class TestSer
     */
    @WebServlet("/TestSer")
    public class TestSer extends HttpServlet {
    	private static final long serialVersionUID = 1L;
           
        /**
         * @see HttpServlet#HttpServlet()
         */
        public TestSer() {
            super();
            // TODO Auto-generated constructor stub
        }

    	/**
    	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
    	 */
    	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    		System.out.println("doGet");
    		
    		response.setContentType("text/html; charset=UTF-8"); 
    		
    		PrintWriter writer = response.getWriter();
    		
    		writer.println("<html><head></head><body>");
    		writer.println("<table border = 1>");
    		writer.println("<tr>");
    		for(int i=2 ; i <= 9 ; i++) {
    			for(int j=1 ; j <= 9 ; j++) {
    				writer.println("<td>");
    				writer.println(i + "x" + j + "=" + (i*j));
    				writer.println("</td>");
    			}
    		}
    		writer.println("</tr>");
    		writer.println("</table>");
    		writer.println("</body></html>");
    		
    		writer.close();
    	}

    	/**
    	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse response)
    	 */
    	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    		// TODO Auto-generated method stub
    		doGet(request, response);
    	}

    }
    ```

- 결과

    <img width="483" alt="1" src="https://user-images.githubusercontent.com/75012998/103525246-3f722800-4ec2-11eb-9a55-53b68136e0de.png">

---

- 9 - 2번 위 문제를 jsp로 작성 하시오.
- jsp 소스코드

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
    	<table border = "1">
    		<%
    			for(int i=2 ; i <= 9 ; i++){
    				%>
    				<tr>
    				<%
    				for(int j=1 ; j <= 9 ; j++){
    				%>
    				<td>
    				<%= i + "x" + j + "=" + (i * j)%>
    				</td>
    				<%
    				}
    				%>
    				</tr>
    				<%
    			}
    		%>
    	</table>
    </body>
    </html>
    ```

- 결과

    <img width="461" alt="2_" src="https://user-images.githubusercontent.com/75012998/103525270-46993600-4ec2-11eb-9d3d-b98f4c86374b.png">

---

- 9 - 3번 아래 문제를 jsp로 작성 하시오.

 1. include.jsp파일을 생성합니다.

<h4> 태그에 '구구단 출력하기'를 작성합니다.

include_data.jsp 파일로 이동하도록 작성합니다.

param 액션 태그로 숫자 5를 출력하는 include_data.jsp 파일에 전달하도록 작성합니다.

- jsp 소스코드

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
    	<h4>구구단 출력하기</h4>
    	<jsp:include page = "include_data.jsp">
    		<jsp:param name ="number" value = "5" />
    	</jsp:include>	
    </body>
    </html>
    ```

---

 2. include_data.jsp 파일을 생성합니다.

전달 받은 숫자 5의 구구단을 출력 하도록 작성합니다.

- jsp 소스코드

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
    	<%
    	String num = request.getParameter("number");
    	int dan = Integer.parseInt(num);
    	
    	for(int i=1 ; i <= 9 ; i++){
    		out.println(dan + "x" + i + "=" + (dan * i));
    		%>
    		<br/>
    		<%
    	}
    			
    	%>
    </body>
    </html>
    ```

---

 3. 웹 브라우저에 [http://localhost:8080/Exercise/ch04/include.jsp를](http://localhost:8080/Exercise/ch04/forward.jsp를) 입력하여 실행 결과 확인!

- 결과

    <img width="597" alt="3" src="https://user-images.githubusercontent.com/75012998/103525296-50bb3480-4ec2-11eb-8945-8271e3f2fb78.png">

![12-31_4_](https://user-images.githubusercontent.com/75012998/103525484-a7c10980-4ec2-11eb-9213-af5c64aae669.png)

 4. 위를 jsp로 작성 하시오.

- jsp 소스코드

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
    		이름 : <input type = "text" name ="uname"><br/>
    		주소 : <input type = "text" name = "uadress"><br/>
    		이메일 : <input type = "email" name = "uemail"><br/>
    		전송 : <input type = "submit" value = "전송">
    	</form>
    </body>
    </html>
    ```

- jsp 소스코드2

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
    	<% response.setContentType("text/html; charset = EUC-KR");
    	   request.setCharacterEncoding("EUC-KR");
    	%>
    	<% String id = request.getParameter("uname"); %>
    	아이디 : <%= id %><br/>
    	<% String adress = request.getParameter("uadress"); %>
    	주소 : <%= adress %><br/>
    	<% String email = request.getParameter("uemail"); %>
    	이메일 : <%= email %><br/>
    </body>
    </html>
    ```

- 결과

    ![4](https://user-images.githubusercontent.com/75012998/103525311-56b11580-4ec2-11eb-81bf-76e5fb77afa2.png)

    ![42](https://user-images.githubusercontent.com/75012998/103525388-79432e80-4ec2-11eb-85bd-9cac0dfecd15.png)

---

![12-31_5](https://user-images.githubusercontent.com/75012998/103525462-9aa41a80-4ec2-11eb-8e1c-65d76ec754d1.png)

 5. 위를 jsp로 작성 하시오.

- jsp 소스코드

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
    		오렌지<input type = "checkbox" name = "fruit" value = "오렌지">
    		사과<input type = "checkbox" name = "fruit" value = "사과">
    		바나나<input type = "checkbox" name = "fruit" value = "바나나">
    		<input type = "submit" value = "전송">
    	</form>
    </body>
    </html>
    ```

- jsp 소스코드2

    ```html
    <%@page import = "java.util.Arrays" %>
    <%@ page language="java" contentType="text/html; charset=EUC-KR"
        pageEncoding="EUC-KR"%>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<% response.setContentType("text/html; charset = EUC-KR");
    	   request.setCharacterEncoding("EUC-KR");
    		
    	   String[] fruit = request.getParameterValues("fruit");
    	%>
    	<b>선택한 과일</b><br/>
    	<%= Arrays.toString(fruit) %>
    </body>
    </html>
    ```

- 결과

    ![5](https://user-images.githubusercontent.com/75012998/103525319-5a449c80-4ec2-11eb-8879-8a908eea3d21.png)

    ![5_2](https://user-images.githubusercontent.com/75012998/103525326-5d3f8d00-4ec2-11eb-8597-3eaa3eb84c17.png)

---

![6](https://user-images.githubusercontent.com/75012998/103525335-5fa1e700-4ec2-11eb-867c-015ff29234a0.png)

 6. 위를 jsp로 작성 하시오.

- jsp 소스코드

    ```html
    <%@page import = "java.util.Date" %>
    <%@ page language="java" contentType="text/html; charset=EUC-KR"
        pageEncoding="EUC-KR"%>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<h1><b>몇시일까요??</b></h1>
    	<% Date today = new Date(); %>
    	<%= today %>
    </body>
    </html>
    ```

- 결과

    ![12-31_6](https://user-images.githubusercontent.com/75012998/103525429-89f3a480-4ec2-11eb-97e6-38108d605234.png)

---

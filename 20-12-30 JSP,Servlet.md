
# 20-12-30(JSP,Servlet)

### 1. jsp/servlet 에서 한글 처리 방식은?

> 한글처리

 1. Get방식 요청

- server.xml파일을 열어 port="8080"인 태그 끝에 URIEncoding="UTF-8" 추가한다 (혹은 EUC-KR)

 2. Post방식 요청

- servlet파일을 생성하여 doPost메소드에 request.setCharacterEncoding("EUC-KR");(혹은 UTF-8) 함수를 넣어준다.

Tomcat 서버의 기본 문자 처리 방식은 IOS-8859-1 방식이다. 따라서 개발자가 별도로 한글 코딩하지 않으면 클라이언트들에겐 한글이 깨져 보인다.

---

### 2. 아래의 선택자에 대하여 설명하시오.

> >

- 자손선택자 태그로 선택자a > 선택자b 처럼 쓰며, 선택자a의 자손에 위치하는 선택자 b를 선택한다.

> +

- 선택자 a 바로 뒤에 위치한 선택자 b 하나를 선택

> ~

- 선택자 a 뒤에 위치한 여러 선택자 b를 선택

> a[href="[https://net.tutsplus.com](https://net.tutsplus.com/)"]

- href속성은 hypertext referance약자로, 연결할 주소를 지정하는 속성이다.

---

### 3.웹 어플리케이션 감시를 위한 프로그래밍 방법은?

> ServletContextListener

- 리스너의 해당 메소드가 웹 어플리케이션의 시작과 종료시 호출된다.
- (contextInitialized(),contextDestroyed())메소드를 override 받아야한다.
- 해당 웹 어플리케이션의 생명 주기를 감시하는 역할

-사용방법

 1. 리스너 클래스 제작 후 web.xml파일에 리스너 클래스 작성

```java
<?xml version="1.0" encoding="UTF-8"?>
 <web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://xmlns.jcp.org/xml/ns/javaee" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd" id="WebApp_ID" version="3.1">
 <display-name>WebTest</display-name> 
<welcome-file-list>
  <welcome-file>index.html</welcome-file> 
	<welcome-file>index.htm</welcome-file>
	<welcome-file>index.jsp</welcome-file> 
	<welcome-file>default.html</welcome-file> 
	<welcome-file>default.htm</welcome-file> 
	<welcome-file>default.jsp</welcome-file> 
</welcome-file-list> 

<listener> 
	<listener-class>com.javalec.ex.ServletL</listener-class> 
</listener> 

</web-app>
```

 2. 리스너 클래스 제작 후 리스너 클래스에 리스너 작성

```java
package com.javalec.ex;

import javax.servlet.ServletContextEvent;
import javax.servlet.ServletContextListener;
public class ServletL implements ServletContextListener { 

		//웹어플리이션이 종료될때 작동 (가장 늦게 실행) 
	@Override 
	public void contextDestroyed(ServletContextEvent arg0) { 
		// TODO Auto-generated method stub 
			System.out.println("contextdestroyed");
	}

	//웹어플리이션이 실행될때 작동 ( 가장 먼저 실행) 
	@Override 
	public void contextInitialized(ServletContextEvent arg0) { 
		// TODO Auto-generated method stub 
		System.out.println("contextInitialized"); 
	} 
}
```

---

### 4.데이터 공유를 위한 ServletContext와 서블릿 초기화 파라미터 ServletConfig에 대하여 설명하시오.

> ServletContext

- 여러 servlet에서 데이터를 같이 공유할 때 사용
- web application내 모든 component가 사용될 수 있는 초기 파라미터

> ServletConfig

- 특정 서블릿, JSP만 사용할 수 있는 파라미터
- 하나의 Servlet 초기화에 필요한 정보를 전달하기 위한 Config 객체입니다.

![컨피그,컨텍스트](https://user-images.githubusercontent.com/75012998/103348178-98197d80-4adc-11eb-9ea4-5103b7bdbe8b.png)

---

### 5. Servlet에서 forward방법은?

```java
RequestDispatcher dispatcher = request.getRequestDispatcher(viewPage);
dispatcher.forward(request, response);

/*
	클라이언트의 최초 요청을 받을 servlet내에 특정 자원에 처리를 요청하고 처리 결과를 
	얻어오는 기능을 수행하는 클래스인 RequestDispatcher객체를 사용하여 viewPage에서 요청받은 것을
	설계된 로직에 의해 실행되어 클라이언트 요청에 알맞는 UI화면을 응답시켜준다.
*/
```

---

### 6.후손 선택자와 자식 선택자에 대하여 설명하시오.

> 자식선택자

- 특정요소의 직계자식만 선택하는 선택자이다.

```java
A > B {
	 속성 : 속성값;
}
```

> 후손선택자

- 문서 구조에서 특정요소의 후손을 선택하는 선택자이다.

사용법

```java
A B{
	속성 : 속성값;
}
```

---

### 7. 아래 문제를 푸시오.

![12-30 1번](https://user-images.githubusercontent.com/75012998/103348087-5983c300-4adc-11eb-97bd-5e3fd1ea2d6d.png)

- 1번 HTML & CSS 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<form action ="Gugudan" method = "post">
    	출력한 구구단 단수 입력 : <input type = "text" name = "number"><input type = "submit" value = "실행">
    	</form>
    </body>
    </html>
    ```

- 1번 JSP 소스코드

    ```java
    import java.io.IOException;
    import java.io.PrintWriter;

    import javax.servlet.ServletException;
    import javax.servlet.annotation.WebServlet;
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;

    /**
     * Servlet implementation class Gugudan
     */
    @WebServlet("/Gugudan")
    public class Gugudan extends HttpServlet {
    	private static final long serialVersionUID = 1L;
           
        /**
         * @see HttpServlet#HttpServlet()
         */
        public Gugudan() {
            super();
            // TODO Auto-generated constructor stub
        }

    	/**
    	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
    	 */
    	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    		// TODO Auto-generated method stub
    		response.getWriter().append("Served at: ").append(request.getContextPath());
    	}

    	/**
    	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse response)
    	 */
    	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    		System.out.println("doPost");
    		response.setContentType("text/html; charset = EUC-KR");
    		request.setCharacterEncoding("EUC-KR");
    		
    		String num = request.getParameter("number");
    		PrintWriter writer = response.getWriter();
    		
    		
    		writer.println("<html><head></head><body>");
    		writer.println("<table border = 1>");
    		writer.println("<tr>");
    		writer.println("<td align = center>" + num +"단" + "</td>");
    		writer.println("</tr>");
    		int temp = 0;
    		
    		for(int i=1 ; i <= 9 ; i++) {
    				temp = Integer.parseInt(num);
    				writer.println("<tr>");
    				writer.println("<td>" + num + " x " + i + " = " + (temp*i) + "</td>");
    				writer.println("</tr>");
    		}
    		writer.println("</table>");
    		writer.println("<input type = button value = 돌아가기 onclick = history.back(-1)>");
    		writer.println("</body></html>");
    		writer.close();
    	}

    }
    ```

- 1번 결과

    ![12-30 1번답](https://user-images.githubusercontent.com/75012998/103348120-71f3dd80-4adc-11eb-9747-f10023dd050e.png)

    ![12-30 1-1번답](https://user-images.githubusercontent.com/75012998/103348129-77512800-4adc-11eb-986d-539685a089f9.png)

---

- 2번 HTML & CSS 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#head{
    			border : 2px solid gray;
    			width : 500px;
    			height : 70px;
    			text-align : center;
    			background-color : #41A541;
    		}
    		h3{
    			font-family : sans-serif;
    			color : white;
    		}
    		
    		input{
    			width : 100px;
    			height : 30px;
    			
    		}
    	
    	</style>

    </head>
    <body>
    	<form action = "Rectangle" method = "post">
    		
    		<div id = head><h3>사각형 넓이 구하기!</h3><br /></div>
    		가로 : <input type = "text" name = "width">
    		세로 : <input type = "text" name = "height">
    		<input type = "submit" value = "전송">
    	</form>
    </body>
    </html>
    ```

- 2번 JSP 소스코드

    ```java
    import java.io.IOException;
    import java.io.PrintWriter;

    import javax.servlet.ServletException;
    import javax.servlet.annotation.WebServlet;
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;

    /**
     * Servlet implementation class Rectangle
     */
    @WebServlet("/Rectangle")
    public class Rectangle extends HttpServlet {
    	private static final long serialVersionUID = 1L;
           
        /**
         * @see HttpServlet#HttpServlet()
         */
        public Rectangle() {
            super();
            // TODO Auto-generated constructor stub
        }

    	/**
    	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
    	 */
    	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    		// TODO Auto-generated method stub
    		response.getWriter().append("Served at: ").append(request.getContextPath());
    	}

    	/**
    	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse response)
    	 */
    	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    		System.out.println("doPost");
    		
    		String wth = request.getParameter("width");
    		String hgt = request.getParameter("height");
    		
    		response.setContentType("text/html; charset = EUC-KR");
    		request.setCharacterEncoding("EUC-KR");
    		
    		PrintWriter writer = response.getWriter();
    		
    		writer.println("<html><head></head><body>");
    		int temp1 = 0;
    		int temp2 = 0;
    		temp1 = Integer.parseInt(wth);
    		temp2 = Integer.parseInt(hgt);
    		writer.println("<table border = 1>");
    		writer.println("<tr>");
    		writer.println("<td width = 300 height = 50 align = center> 사각형의 넓이 : " + (temp1 * temp2) + "</td>");
    		writer.println("</tr>");
    		writer.println("</table>");
    		writer.println("<input type = button value = 돌아가기 onclick = history.back(-1)>");
    		writer.println("</body></html>");
    	}

    }
    ```

- 2번 결과

    ![12-30 2번답](https://user-images.githubusercontent.com/75012998/103348145-7fa96300-4adc-11eb-9ec0-5dc2778e7ac4.png)

    ![12-30 2-1번답](https://user-images.githubusercontent.com/75012998/103348154-83d58080-4adc-11eb-9fd3-e4ce70524c31.png)

---

![12-30 2번](https://user-images.githubusercontent.com/75012998/103348099-60123a80-4adc-11eb-93c6-4971bd8e760e.png)

- 3번 HTML & CSS 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#div1{
    			display : inline-block;
    			width : 1000px;
    		}

    		#div2{
    			display : inline-block;
    			width : 1000px;
    		}
    		
    		#div3{
    			display : inline-block;
    			width : 1000px;
    		}
    		
    		
    		#hleft {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 0px 25px 0px; 
    			height : 100px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#hright {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 0px 0px 25px;
    			height : 100px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#hcenter {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 0px 25px 25px; 
    			height : 100px;
    			width : 550px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		
    		#contentsleft {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 25px 25px 0px; 
    			height : 250px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#contentsright {
    			display : inline-block;
    			border-top-width: 0px;
    			border : 1px solid gray;
    			border-radius : 25px 0px 0px 25px;
    			height : 250px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#contentscenter {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 25px 25px 25px 25px; 
    			height : 250px;
    			width : 550px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		
    		#fleft {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 25px 0px 0px; 
    			height : 100px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#fright {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 25px 0px 0px 0px;
    			height : 100px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#fcenter {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 25px 25px 0px 0px; 
    			height : 100px;
    			width : 550px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		
    		.menu1 ,.menu2,.menu3,.menu4{
    			display : inline-block;
    			font-weight : bold;
    			padding-right : 40px;
    		}
    		
    		#word{
    			padding-right : 10px;
    			padding-left : 10px;
    		}
    		
    	</style>
    </head>
    <body>
    	<div id = "div1">
    		<div id = "hleft"></div>
    		<div id = "hcenter"></div>
    		<div id = "hright"></div>
    		
    	</div>
    	
    	<br/>
    	
    	<div id = "div2">
    		<div id = "contentsleft" style = "border-top-width: 0px;"></div>
    		<div id = "contentscenter" style = "border-top-width: 0px;">
    			<ul>
    				<li class = "menu1">menu1</li>
    				<li class = "menu2">menu2</li>
    				<li class = "menu3">menu3</li>
    				<li class = "menu4">menu4</li>
    			</ul>
    			<h1>&nbsp하이서울브랜드</h1>
    			<p id = "word">서울시와 서울산업진흥원(SBA)이 공동으로 지원하는 하이 서울브랜드 사업은 우수한 기술력과
    				상품력을 보유하고 있으나 고유브랜드 육성에 어려움을 겪고 있는 우수 기업들이 서울시가 인정한
    				중소기업 공동브랜드인 하이서울브랜드를 활용하여 제품 경쟁력을 강화할 수 있도록 각종 홍보 마케팅을 지원하는 사업입니다.</p>
    		</div>
    		<div id = "contentsright" style = "border-top-width: 0px;"></div>
    	</div>
    	

    	
    	<div id = "div3">
    		<div id = "fleft" style = "border-top-width: 0px;"></div>
    		<div id = "fcenter" style = "border-top-width: 0px;"></div>
    		<div id = "fright" style = "border-top-width: 0px;"></div>
    	</div>

    </body>
    </html>
    ```

- 3번 결과

    ![3번답](https://user-images.githubusercontent.com/75012998/103348161-8cc65200-4adc-11eb-944c-948954b94d26.png)

---

- 4번 HTML & CSS 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#div1{
    			display : inline-block;
    			width : 1000px;
    		}

    		#div2{
    			display : inline-block;
    			width : 1000px;
    		}
    		
    		#div3{
    			display : inline-block;
    			width : 1000px;
    		}
    		
    		#hleft {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 25px 0px 25px 0px; 
    			height : 100px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#hright {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 25px 0px 25px;
    			height : 100px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#hcenter {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 0px 25px 25px; 
    			height : 100px;
    			width : 550px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		
    		#contentsleft {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 25px 25px 0px; 
    			height : 250px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#contentsright {
    			display : inline-block;
    			border-top-width: 0px;
    			border : 1px solid gray;
    			border-radius : 25px 0px 0px 25px;
    			height : 250px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#contentscenter {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 25px 25px 25px 25px; 
    			height : 250px;
    			width : 550px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		
    		#fleft {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 0px 25px 0px 0px; 
    			height : 100px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#fright {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 25px 0px 25px 0px;
    			height : 100px;
    			width : 150px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		#fcenter {
    			display : inline-block;
    			border : 1px solid gray;
    			border-radius : 25px 25px 0px 0px; 
    			height : 100px;
    			width : 550px;
    			float : left;
    			background-color : #dcdcdc;
    		}
    		
    		.menu1 ,.menu2,.menu3,.menu4{
    			display : inline-block;
    			font-weight : bold;
    			padding-right : 40px;
    		}
    		
    		#word{
    			padding-right : 10px;
    			padding-left : 10px;
    		}
    		
    	</style>
    </head>
    <body>
    	<div id = "div1">
    		<div id = "hleft"></div>
    		<div id = "hcenter"></div>
    		<div id = "hright"></div>
    		
    	</div>
    	
    	<br/>
    	
    	<div id = "div2">
    		<div id = "contentsleft" style = "border-top-width: 0px;"></div>
    		<div id = "contentscenter" style = "border-top-width: 0px;">
    			<ul>
    				<li class = "menu1">menu1</li>
    				<li class = "menu2">menu2</li>
    				<li class = "menu3">menu3</li>
    				<li class = "menu4">menu4</li>
    			</ul>
    			<h1>&nbsp하이서울브랜드</h1>
    			<p id = "word">서울시와 서울산업진흥원(SBA)이 공동으로 지원하는 하이 서울브랜드 사업은 우수한 기술력과
    				상품력을 보유하고 있으나 고유브랜드 육성에 어려움을 겪고 있는 우수 기업들이 서울시가 인정한
    				중소기업 공동브랜드인 하이서울브랜드를 활용하여 제품 경쟁력을 강화할 수 있도록 각종 홍보 마케팅을 지원하는 사업입니다.</p>
    		</div>
    		<div id = "contentsright" style = "border-top-width: 0px;"></div>
    	</div>
    	

    	
    	<div id = "div3">
    		<div id = "fleft" style = "border-top-width: 0px;"></div>
    		<div id = "fcenter" style = "border-top-width: 0px;"></div>
    		<div id = "fright" style = "border-top-width: 0px;"></div>
    	</div>

    </body>
    </html>
    ```

- 4번 JSP 소스코드

    ```java
    import java.io.IOException;
    import java.io.PrintWriter;

    import javax.servlet.ServletException;
    import javax.servlet.annotation.WebServlet;
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;

    /**
     * Servlet implementation class StarPrint
     */
    @WebServlet("/StarPrint")
    public class StarPrint extends HttpServlet {
    	private static final long serialVersionUID = 1L;
           
        /**
         * @see HttpServlet#HttpServlet()
         */
        public StarPrint() {
            super();
            // TODO Auto-generated constructor stub
        }

    	/**
    	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
    	 */
    	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    		// TODO Auto-generated method stub
    		response.getWriter().append("Served at: ").append(request.getContextPath());
    	}

    	/**
    	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse response)
    	 */
    	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    		System.out.println("doPost");
    		
    		response.setContentType("text/html; charset = EUC-KR");
    		
    		String str = request.getParameter("star");
    		
    		PrintWriter writer = response.getWriter();
    		
    		writer.println("<html><head></head><body>");
    		
    		int temp = Integer.parseInt(str);
    		
    		for(int i=1 ; i<= temp ; i++) {
    			for(int j = 1; j<= i ; j++ ){
    				writer.print("*");
    			}
    			writer.println("<br/>");
    		}
    		writer.println("<h3>별완성!</h3>");
    		writer.println("<input type = button value = 돌아가기 onclick = history.back(-1)>");
    		writer.println("</body></html>");
    	}

    }
    ```

- 4번 결과

   ![12-30 4번답](https://user-images.githubusercontent.com/75012998/103348168-90f26f80-4adc-11eb-81fb-89a729c8707d.png)

![12-30 4-1답](https://user-images.githubusercontent.com/75012998/103348173-9485f680-4adc-11eb-81db-9d04dd866e16.png)

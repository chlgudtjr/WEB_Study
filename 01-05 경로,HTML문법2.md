# 21-01-05(경로, HTML문법2)

### 1. 절대경로와 상대경로에 대하여 설명하시오.

> 절대경로

- 컴퓨터 하드드라이브 이름부터 시작하여 1단계씩 하위의 폴더로 접근하는 방식
- / 을 붙이고 프로젝트명을 표기 해야한다.

**지정법**

[http://localhost:8282/-](http://localhost:8282/-)> "절대경로(/프로젝트명/폴더명/파일명)"

**EX)** /css_basic/0105/request_send.jsp

> 상대경로

- 현재 디렉토리 안의 파일의 위치로부터 다른 파일의 위치로의 경로
- 프로젝트 명은 생략이 가능하다.

**지정법**

[http://localhost:8282/프로젝트명/-](http://localhost:8282/%EC%BB%A8%ED%85%8D%EC%8A%A4%ED%8A%B8%EB%AA%85/-)> "상대경로((파일이 속한 폴더의 상위폴더) ../폴더명/파일명)"

**EX) ../**0105/request_send.jsp

---

### 2 .아래의 action 속성에 대하여 아래의 3가지 케이스에 대하여 테스트 하고 결론을 내려 보세요.

```java
0105/request_send.jsp
..0105/request_send.jsp
/0105/request_send.jsp
--------------------------------------------------------------
// 0104폴더에 있는 JspTest.jsp 소스코드

<form action="0105/request_send.jsp">
당신의 나이는 : <input type="text" name="age" size="5">
		<input type="submit" value="전송">
	</form>

--------------------------------------------------------------
// 0105폴더에 있는 request_send.jsp파일 소스코드

	<%!String uage; %>
	
	<% 
		uage = request.getParameter("age");
		int test = Integer.parseInt(uage);
		if(test >= 20){
	%>
		<%= uage%>살<br/>
		당신은 성인입니다.
	<%	
		}else{
	%>
		<%= uage%>살<br/>
		당신은 미성년자 입니다.		
	<% 		
		}
	%>
```

 Case 1 : 0105/request_send.jsp

**결과 :** 0105폴더의 상위 폴더를 지정해주지 않아 해당 파일을 찾을 수 없어 오류 발생

![Untitled](https://user-images.githubusercontent.com/75012998/103636052-c68bd280-4f8c-11eb-8c13-eba44e474cd9.png)

Case 2 : ../0105/request_send.jsp

**결과 :** ../는 현재 폴더의 부모 폴더를 지정하는 경로 표기법이다. 0105폴더의 부모폴더가 0104폴더이기 때문에 올바르게 경로 표기하였으므로 오류가 나지 않고 원하는 실행 값이 나왔다.

![Untitled 1](https://user-images.githubusercontent.com/75012998/103636098-da373900-4f8c-11eb-8dcf-534a72bdab1d.png)

Case 3 : /0105/request_send.jsp

**결과 :** 0105폴더를 절대 경로로 지정하여 상위 폴더를 찾지 못하고 0105폴더 안에서만 찾아 오류 발생. 

![Untitled 2](https://user-images.githubusercontent.com/75012998/103636089-d4d9ee80-4f8c-11eb-8316-2bdaa58ff057.png)

---

### 3. css에서의 position 의 4가지 설명하시오.

position이란?? HTML요소가 위치를 결정하는 방식이며, top,bottom,left, right 속성 값이 요소를 배치할 최종 위치를 결정 한다.

> static

- 초기 값으로 위치를 지정하지 않을 때와 같다.
- 앞에 설정된 position을 무시할 때 사용되기도 한다.
- top,bottom,left, right 속성 값이 적용되지 않는다.

> relative

- 위치를 계산할 때 static의 원래 위치부터 계산한다.
- top,bottom,left, right 속성 값을 같이 설정할 수 있다.

> absolute

- 포지션 static 속성을 가지고 있지 않은 부모를 기준으로 움직인다.
- 만약 부모중에 포지션이 relative, absolute, fixed인 태그가 없다면 가장 위의 태그가 기준이 된다.

> fixed

- 화면이 바뀌더라도 고정된 위치를 설정할 수 있다.
- 상위 요소에 영향을 받지 않는다.
- top,bottom,left, right 속성 값을 같이 설정할 수 있다.

**각 포지션 속성의 예**

![01-05 da8c5393aeba45cd9bed0dabb779e1e1](https://user-images.githubusercontent.com/75012998/103635992-b1af3f00-4f8c-11eb-8bce-b9b7504cc475.png)

---

### 4. float 속성에 대하여 설명하시오.

> float

- float는 단어로 '뜨다'라는 의미이며 웹페이지에서 블록을 띄워 요소들과 함께 배치하는 속성

**속성값**

 1. none : 띄우지 않음(기본값)

![float-none](https://user-images.githubusercontent.com/75012998/103636153-ef13cc80-4f8c-11eb-89fd-bc528257a3af.png)

 2. left : 왼쪽으로 띄움

![float-left](https://user-images.githubusercontent.com/75012998/103636140-ea4f1880-4f8c-11eb-940d-5e2e6e073a22.png)

 3. right : 오른쪽으로 띄움

![float-right](https://user-images.githubusercontent.com/75012998/103636165-f509ad80-4f8c-11eb-8a40-2841a2e21ed6.png)

---

### 5. 쿠키에 대하여 설명하시오.

> Cookie

- 클라이언트와 서버가 연결을 시도한 흔적을 남겼다가, 후에 또 연결을 시도 할 때 과거의 접속을 이어나가기 위해 흔적을 사용하는 방법

**동작방식**

 1. 쿠키 생성 : 웹 서버에서 쿠키를 생성하고 쿠키에 응답데이터를 담아서 웹브라우저에 전송한다.

 2. 쿠키 저장 : 웹 브라우저는 응답 데이터를 담고 있는 쿠키를 메모리나 파일로 저장한다.

 3. 쿠키 전송 : 웹 브라우저는 쿠키 요청이 있을 때마다 웹 서버에 전송한다.

- **ex)**

    ```java
    // 쿠키생성
    <%
    Cookie cookie = new Cookie("cookieN", "cookieV"); //(cookieName , cookieValue)
    cookie.setMaxAge(60 * 60); // 쿠키의 유효기간을 설정 - (1시간)
    respose.addCookie(cookie); // 클라이언트 응답에 쿠키를 추가
    %>

    // 쿠키에 저장된 정보를 읽어오기
    <%
    Cookie[] cookies = request.getCookies(); // 요청정보로부터 쿠키를 가져온다.

    for(int i=0 ; i < cookie.length ; i++){ // 쿠키배열을 반복문으로 실행
    	Strings str = cookie[i].getName(); // 쿠키에 저장된 배열의 길이를 가져온다.
    	if(str.equals("cookieN")){ // 배열 안에 쿠키이름이 포함되어 있다면..
    		out.println("cookies[" + i + "] name : " + cookies[i].getName() + "<br />"); // 쿠키의 이름을 출력.
    		out.println("cookies[" + i + "] value : " + cookies[i].getValue() + "<br />"); // 쿠키의 값을 출력.
    		out.println("=====================<br />");
    	}
    }
    %>

    // 설정된 쿠키를 모두 삭제하기
    <%
    Cookie[]cookie = request.getCookies(); // 요청정보로부터 쿠키를 가져온다.
    for(int i=0; i<cookies.length; i++) { // 쿠키 배열을 반복문으로 돌린다.
    			String str = cookies[i].getName(); // 쿠키에 저장된 배열의 길이를 가져온다.
    			if(str.equals("cookieN")) { // 배열 안에 쿠키이름이 포함되어 있다면..
    				out.println("name : " + cookies[i].getName() + "<br />"); // 쿠키의 이름을 출력
    				cookies[i].setMaxAge(0); // 특정 쿠키를 더이상 사용하지 못하게 쿠키의 유효시간을 만료시킨다.
    				response.addCookie(cookies[i]); // 해당 쿠키를 응답에 추가(수정)한다.
    			}
    		}
    %>
    ```

---

### 6. 액션 태그에 대하여 설명하시오.

> 액션태그

- JSP페이지내에서 어떤 동작을 지시하는 태그
- 사용법 : ("<jsp:>")

**태그종류**

 1. forward ("<jsp:forward>") : 현재 페이지에서 다른 특정페이지로 전환할 때 사용한다.

 2. include ("<jsp:include>") : 현재 페이지에 다른페이지를 삽입할 때 사용한다.

 3. param ("<jsp:param>") : forward 및 include태그에 데이터 전달을 목적으로 사용한다.

---

### 7. 아래 문제를 푸시오.

![1](https://user-images.githubusercontent.com/75012998/103636212-02269c80-4f8d-11eb-90ba-e38a6f5c3b09.png)

- HTML & CSS 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#nav{
    			border : 1px solid black;
    			width : 800px;
    			overflow : hidden;
    		}
    		
    		#nav div:nth-child(1){
    			background-color : green;
    			height : 60px;
    			font-weight : bold;
    		}
    		#nav div:nth-child(2){
    			background-color : yellow;
    			float : left;
    			font-weight : bold;
    			height : 550px;
    			padding-right : 20px;
    		}
    		#nav div:nth-child(3){
    			background-color : gray;
    			height : 550px;
    			float : right;
    			font-weight : bold;
    			padding-right : 20px;
    		}
    		#nav div:nth-child(4){
    			background-color : red;
    			font-weight : bold;
    			height : 550px;
    		}
    		#nav div:nth-child(5){
    			background-color : blue;
    			height : 50px;
    			font-weight : bold;
    		}	
    	</style>
    </head>
    <body>
    	<div id = "nav">
    		<div>헤더</div>
    		<div>컨텐츠 LEFT</div>	
    		<div>컨텐츠 RIGHT</div>
    		<div>컨텐츠 CENTER</div>
    		<div>푸터</div>
    	</div>
    </body>
    </html>
    ```

- 결과

    ![1 1](https://user-images.githubusercontent.com/75012998/103636217-03f06000-4f8d-11eb-9f19-8d40ae4009eb.png)

---

![2](https://user-images.githubusercontent.com/75012998/103636252-110d4f00-4f8d-11eb-883d-a7523c9f9ab7.png)

- HTML & CSS 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#big{
    			border : 1px solid #cccccc;
    			overflow : hidden;
    			width : 1000px;
    			
    		}
    		
    		#big #head{
    			border : 1px solid #cccccc;
    			margin : 10px;
    			height : 120px;
    			line-height : 120px;
    			text-align : center;
    			margin-bottom : 5px;
    			font-size : 20px;
    		}
    		
    		#big #nav{
    			border : 1px solid #cccccc;
    			margin : 10px;
    			height : 140px;
    			margin-top : 5px;
    			margin-bottom : 5px;
    		}
    		
    		#nav .menu{
    			border : 1px solid #cccccc;
    			height : 45px;
    			float : left;
    			line-height : 45px;
    			width : 170px;
    			position : relative;
    			left : 60px;
    			text-align : center;
    			font-weight : bold;
    		}
    		
    		#nav #nav2{
    			border : 1px solid white;
    			height : 75px;
    			line-height : 75px;
    			text-align : center;
    			font-size : 20px;
    		}
    		
    		#sec{
    			border : 1px solid #cccccc;
    			margin : 10px;
    			height : 400px;
    			margin-top : 5px;
    			margin-bottom : 5px;
    		}
    		
    		#sec .con{
    			border : 1px solid #cccccc;
    			margin : 10px;
    			height : 378px;
    			width : 740px;
    			float : left;
    			margin-right : 5px;
    			text-align : center;
    			font-size : 20px;
    		}
    		
    		#sec .ban{
    			border : 1px solid #cccccc;
    			margin : 10px;
    			height : 378px;
    			width : 200px;
    			float : right;
    			margin-left : 5px;
    			text-align : center;
    			font-size : 20px;
    		}
    		
    		#footer{
    			border : 1px solid #cccccc;
    			margin : 10px;
    			width : 978px;
    			height : 120px;
    			line-height : 120px;
    			margin-top : 5px;
    			text-align : center;
    			font-size : 20px;
    		}
    		
    	</style>
    </head>
    <body>
    	<div id = "big">
    		<div id = "head">HEADER</div>
    		<div id = "nav">
    				<div id = "nav2">NAVIGATION</div>
    				<div class = "menu">menu1</div>
    				<div class = "menu">menu2</div>
    				<div class = "menu">menu3</div>
    				<div class = "menu">menu4</div>
    				<div class = "menu">menu5</div>
    		</div>
    		
    		<div id = "sec">
    			<div class = "con">CONTENT</div>
    			<div class = "ban">BANNER</div>
    		</div>
    		
    		<div id = "footer">FOOTER</div>
    	</div>
    </body>
    </html>
    ```

- 결과

    ![2 1](https://user-images.githubusercontent.com/75012998/103636254-123e7c00-4f8d-11eb-87ed-c909e95c9f6d.png)

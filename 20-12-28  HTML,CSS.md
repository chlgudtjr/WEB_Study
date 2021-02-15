# 20-12-28(HTML,CSS)

### 1.html 이란 무엇인가?

> HTML(Hyper Text Markup Language)

- 웹문서를 기술하는 언어.
- 웹 페이지 콘텐츠 안의 꺾쇠(<>) 괄호에 둘러싸인 "태그"로 되어있는 HTML 요소 형태로 작성한다.

'태그'란? HTML문서를 구성하고 있는 요소, 웹페이지의 디자인과 기능을 결정하는데 사용된다.(이름과 속성이 있다.) 

---

### 2.css 란 무엇인가?

> CSS(Cascading Style Sheets)

- HTML문서를 디자인적으로 예쁘게 만들어 정보 전달을 효율적으로 하기 위해 만들어진 문서.
- 정보(HTML)와 디자인(CSS)을 분리하여 관리할 수있다.

---

### 3.아래의 태그에 대하여 설명하시오.

> <del>

- Text 한 가운데에 라인을 추가하여 삭제된 텍스트를 표현할 때 사용한다.

ex) <del>HELLO</del>

> <ins>

- 'ins'는 'del'과 반대 개념이다. Text 아래쪽에 라인을 추가하여 추가된 텍스트를 표현할 때 사용한다.

ex) <ins>HELLO</ins>

> <span>

- 어떠한 기능을 가지고 있는 태그가 아니지만 문자열을 원하는 부분만 선택해서 CSS와 함께 시각적 효과를 줄 수 있다.

ex) <span>HELLO</span>
---

### 4. block 태그와 non block 태그에 대하여 설명하시오.

> block tag

- 요소 안 내용 길이 상관 없이 요소 자체가 한 줄 전체를 차지하는 요소.

> non block tag (inline)

- 한 줄을 차지하지 않고 요소 공간만 차지하며, 개행 하지 않는다.

---

### 5.get 방식과 post 방식에 대하여 설명하시오.

> Get

- HTML내 form태그의 method속성이 get일 경우 호출 된다.
- 웹 브라우저의 주소창을 이용하여 servlet을 요청한 경우에도 호출된다.
- URL에 변수(데이터)를 포함시켜 요청한다.
- URL에 데이터가 노출되어 보안에 취약하다.

> Post

- html내 form 태그의 method속성이 post일 경우 호출 된다.
- URL에 변수(데이터)를 노출하지 않고 요청한다.
- 데이터를 Body(바디)에 포함시킨다.
- URL에 데이터가 노출되지 않아서 기본 보안은 되어있다.

---

### 6.컨텍스트 패스란 무엇인가?

> Context Path

- WAS에서 웹 어플리케이션을 구분하기 위한 path이다.
- 이클립스와 톰캣을 연동하여 웹 어플리케이션을 실행할 때 자동으로 server.xml이 추가된다.
- 각각의 프로젝트를 구분하기 위함.

---

### 7.아래의 객체에 대하여 설명하시오.

> HttpServletRequest

- Http프로토콜의 request 정보를 서블릿에게 전달하기 위한 목적으로 사용.
- Header정보, Parameter, Cookie, URI, URL 등의 정보를 읽어들이는 메소드를 가진 클래스.
- Body의 Stream을 읽어들이는 메소드를 가지고 있음.

> HttpServletReponse

- Servlet은 HttpServletResponse객체에 Content Type, 응답코드, 응답 메시지등을 담아서 전송함.

![리스폰퀘스트](https://user-images.githubusercontent.com/75012998/103208760-d1b78080-4944-11eb-898b-826a1eb6a3e1.png)

---

### 8. 아래 문제를 푸시오.

![1번 문제](https://user-images.githubusercontent.com/75012998/103208778-dbd97f00-4944-11eb-86f8-3d4de4c31615.jpg)

- HTML코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<table border = "1" width = 620;>
    	<tr>
    		<td>
    		<blockquote style = "margin-left: 0px; margin-right: 0px;">
    			<h1>제주 이색 여행지</h1>
    			<h3><b>야외 텐트를 닮은 건축물 "테쉬폰"</b></h3>
    			<p><h5>아일랜드 출신 임피제 신부가 1954년 제주에 오면서 목장 숙소로 짓기 시작한 후 사료공장, 성당으로 활용됐습니다.</h5>
    			<h5>제주에서 점차 다른 지방으로 보급됐지만 현재 제주에만 건축물이 남아있는데,
    			국내 근현대 건축사의 한 페이지를 보여주는 가치를 지닌다고 전문가들은 평가합니다.</h5>
    		</p>
    		</blockquote>
    		</td>
    	</tr>
    	<tr>
    		<td>
    			<blockquote>
    			<h5 style = "margin-top : 10px; margin-bottom: 10px">성이시들목장은 제주특별자치도 제주시 한림읍 금악리에 있는 목장이다. 특히 이
    			시들 목장은 제주지역 최초의 전기업목장(全企嶪牧場)으로 1961년 11월 말 제주시 한림읍
    			금악리에 세워 양돈 사업을 실시하였으며 면양을 사육하였던 것으로 알려져 있다. 이시들 목장의
    			특색있는 건축 양식으로 테쉬폰도 유명하다.(출처:향토문화전자대전)
    			</h5>
    			</blockquote>
    		</td>
    	</tr>
    	</table>
    	
    </body>
    </html>
    ```

- 답

    ![1번문제 답](https://user-images.githubusercontent.com/75012998/103208795-e136c980-4944-11eb-918b-6e2e58b60691.jpg)

![2번문제](https://user-images.githubusercontent.com/75012998/103208805-e72caa80-4944-11eb-95f9-0e32ad6658bf.jpg)

- HTML코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<table border = "1" width = "600">
    	<tr>
    		<td>
    			<blockquote style = "margin-left: 0px;">
    			<p>
    			<h1>제주 이색 여행지 - 이중섭 거리</h1>
    			<b>주말</b>마다 <b>'서귀포문화예술디자인시장'</b>이 열립니다.
    			<h4><i>'아트마켓'</i>이라고도 부르는데,<i>문화예술체험</i>이나<i>공연관람</i>을
    			할 수도 있고 작가들이 직접 만든 창작예술품 등을 판매하기도 합니다.</h4>
    			</p>
    			</blockquote>
    		</td>
    	</tr>

    	</table>		
    </body>
    </html>
    ```

- 답

    ![2번 답](https://user-images.githubusercontent.com/75012998/103208820-ed228b80-4944-11eb-9e65-d55f82daf86b.jpg)

![3번문제](https://user-images.githubusercontent.com/75012998/103208828-f1e73f80-4944-11eb-8db0-20c0925e5f2c.jpg)

- HTML코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<table border = "1" width = "670" height = "220">
    	<tr>
    		<td>
    			<blockquote style = "margin-left: 0px; margin-right: 0px;">
    			<p>
    			<h2>야외 텐트를 닮은 건축물 <span><mark>"테쉬폰"</mark></span></h2>
    			아일랜드 출신 임피제 신부가 1954년 제주에 오면서 목장 숙소로 짓기 시작한 후 사료공장, 성당으로 
    			활용됐습니다.제주에서 점차 다른 지방으로 보급됐지만 현재 제주에만 건축물이 남아있으며,
    			<span style = "color: blue;">국내 근현대 건축사의 한 페이지를 보여주는 가치를 지닌다</span>고
    			전문가들은 평가합니다.
    			</p>
    			</blockquote>
    		</td>
    	</tr>

    	</table>		
    </body>
    </html>
    ```

- 답

   ![3번 답](https://user-images.githubusercontent.com/75012998/103208838-f6135d00-4944-11eb-8267-6c1352465ce1.jpg)

![4번문제](https://user-images.githubusercontent.com/75012998/103208846-fad81100-4944-11eb-8e78-7152398ec14c.jpg)

- HTML코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<table border = "1" width = "500" height = "220">
    	<tr>
    		<td>
    			<blockquote style = "margin-left: 0px; margin-right: 0px;">
    			<p>
    			<h1>1박 2일 가족 여행 코스</h1>
    			<ul>
    				<li>1일차</li>
    					<ol type = "a"; start = "1">
    						<li>해녀 박물관</li>
    						<li>낚시체험</li>
    					</ol>
    				<li>2일차</li>
    					<ol type = "a"; start = "3">
    						<li>용눈이오름</li>
    						<li>만장굴</li>
    						<li>카약체험</li>
    					</ol>
    				</ul>
    			</p>
    			</blockquote>
    		</td>
    	</tr>

    	</table>		
    </body>
    </html>
    ```

- 답

   ![4번답](https://user-images.githubusercontent.com/75012998/103208854-fdd30180-4944-11eb-8a8f-fdaea47da443.jpg)

![5번문제](https://user-images.githubusercontent.com/75012998/103208861-01668880-4945-11eb-9ddf-9eb1f248af95.jpg)

- HTML코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<table border = "1" width = "500" height = "200">
    	<tr align = "center">
    		<td width = "80">이름</td>
    		<td></td>
    		<td width = "80">연락처</td>
    		<td></td>
    	</tr>
    	<tr align = "center">
    		<td>주소</td>
    		<td colspan = "3"></td>
    	
    	</tr>
    	<tr align = "center">
    		<td>자기<br/>소개</td>
    		<td colspan = "3"></td>
    	</tr>
    	</table>		
    </body>
    </html>
    ```

- 답

   ![5번답](https://user-images.githubusercontent.com/75012998/103208865-03c8e280-4945-11eb-9d06-76bbf3e757b3.jpg)

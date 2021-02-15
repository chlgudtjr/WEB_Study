
# 20-12-29(HTML,CSS문법1)

### 1. 선택자란?

> Selector

- html의 특정 태그를 선택하여, 해당 태그의 속성을 변경하는 기능이다.

-종류

1. Type Selector
- 태그명이 선택자와 같은 태그에게 속성이 적용된다.

 2. Universal Seletor

- html 모든 태그에 속성이 적용된다. 선택자는 (*)을 사용하여 나타냄.

 3. ID Selector

- 특정 태그가 id속성을 가질 때 속성이 적용된다. 선택자는 (#)을 사용하여 나타냄.
- 특정 하나의 태그만 속성을 적용하려 할 때 사용한다.

 4. Class Selector

- 특정 태그가 class속성을 가질 때 속성이 적용된다. 선택자는 (.)을 사용하여 나타냄
- 여러태그를 그룹화하여 속성을 적용할 때 사용한다.

-선언법

```html
1. Type Selector
<style>
	선택자(태그){
			 속성 : 속성값;
		}
</style>

2. Universal Seletor
<style>
	*선택자(태그){
			 속성 : 속성값;
		}
</style>

3. ID Selector
<style>
	#id이름(태그){
			 속성 : 속성값;
		}
</style>

4. Class Selector
<style>
	.class이름(태그){
			 속성 : 속성값;
		}
</style>
```

---

### 2. CSS 문법은?

> CSS(Cascading Style Sheets)

- 기본적으로 선택자와 선언부를 통해 구성된다.
- 무조건 style 태그 안에 정의 해야 한다.

```html
<style>
	선택자{
		선언부(속성명 : 속성값);
	}
</style>

1.선택자는 HTML Tag / elements가 온다.
2.선언부는 중괄호안에 위치하고 속성명과 속성값이 들어간다, 선언은 세미콜론으로 구분한다.
```

---

### 3. 시멘틱 태그에 대하여 설명하고,그 종류는?

> Semantic Tag

- 웹 페이지 구조를 쉽게 이해할 수 있도록 정의된 태그

-종류

 1. header

- 머리글, 제목,로고 등 지정하는 태그

 2. nav

- 주로 메뉴에 사용되는 태그

 3. section

- 주제별 콘텐츠의 영역, 제목으로 시작하는 컨텐츠를 그룹핑하기 위한 태그

 4. article

- 실제 콘텐츠 내용을 담는 태그

 5. aside

- 본문 이외의 내용 표시하는 태그 주로 광고나 링크를 지정한다.

 6. footer

- 주로 하단에 위치하여 제작정보, 회사소개, 약관 등을 포함하는 태그

![시멘틱태그](https://user-images.githubusercontent.com/75012998/103278921-f62c5f00-4a0f-11eb-94a2-9af8a8dc62d1.png)


---

### 4. bootstrap 에 대하여 설명하시오.

> Bootstrap

- 웹 사이트를 쉽게 만들 수 있게 도와주는 HTML, CSS, JS 프레임워크이다.
- 다양한 기능을 제공하여 사용자가 쉽게 웹사이트를 제작, 유지, 보수할 수 있도록 도와준다.

Bootstrap에 더 많은 정보를 알고 싶다면 [https://namu.wiki/w/Bootstrap(%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC)](https://namu.wiki/w/Bootstrap(%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC)) 에서 확인해보자!

---

### 5. overflow 에 대하여 설명하시오.

> Overflow

- 내용이 요소의 크기보다 커서 요소의 블록 서식 맥락에 맞출 수 없는 경우 어떻게 처리할지를 정하는 속성이다.

-종류

 1. visible

- 내용이 블록을 넘어가도 보여준다.

 2. hidden

- 블록을 넘어간 부분은 보여주지 않는다.

 3. scroll

- 내용이 블록을 넘어가던 넘지 않던 스크롤바를 노출한다.

 4. auto

- 내용이 블록을 넘어가면 스크롤바가 생기고 넘어가지 않으면 스크롤바가 생기지 않음.

---

### 6.class 와 id 선택자의 차이와 어떨때 사용하는가?

> class 선택자

- 문서 안 복수의 요소에 스타일을 적용하는 경우 사용된다.

> Id 선택자

- 문서 안 단 하나의 요소에 스타일을 적용하는 경우 사용한다.

---

### 7. servlet의 생명주기에 대하여 설명하시오.

![서블릿 생명주기](https://user-images.githubusercontent.com/75012998/103278927-fcbad680-4a0f-11eb-92b2-59130165f8ec.png)

---

### 8. 아래 문제를 푸시오.

![1번](https://user-images.githubusercontent.com/75012998/103278954-0d6b4c80-4a10-11eb-9b64-a5522112b85f.png)

- HTML 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    	<style>
    		#head{
    			width : 500px;
    			text-align : center;
    			background-color : yellow;
    			border : 1px solid #808080;
    		}
    		
    		#selec{
    			width : 500px;
    			border : 1px solid gray;
    			background-color : skyblue;
    			overflow: hidden;
    		}
    		
    		#cont{
    			width : 350px;
    			background-color : skyblue;
    			border : 1px solid #808080;
    			float : left;
    		}
    		
    		#banner{
    			border : 1px;
    			border : 1px solid #808080;
    			float : left;
    		}
    		
    		.m1{
    			color : blue;
    			font-weight : bold;
    			
    		}
    		
    		.m1, .m3,.m5{
    			font-size : 20px;
    		}
    		
    		#footer{
    			width : 500px;
    			text-align : center;
    			background-color : yellow;
    			border : 1px solid #808080;
    		}
    		
    	</style>

    </head>
    <body>
    	<div id = "head">
    		<h1>HEADER</h1>
    	</div>
    	
    	<div id = "selec">
    		<div id = "cont">
    			<h1 align = "center">CONTENTS</h1>
    			<ul>
    				<li class = "m1">menu1</li>
    				<li class = "m2">menu1</li>
    				<li class = "m3">menu1</li>
    				<li class = "m4">menu1</li>
    				<li class = "m5">menu1</li>
    			</ul>
    		</div>
    		<div id = "banner">
    			<h1>BANNER</h1>
    			<a href = "http://www.sba.seoul.kr" target = "_blank"><img src = "http://www.sba.seoul.kr/kr/images/footer/f_logo.png"></a>
    		</div>
    	</div>
    	
    	
    	<div id = "footer">
    		<h1>FOOTER</h1>
    	</div>
    	
    </body>
    </html>
    ```

- 결과

    ![1번답](https://user-images.githubusercontent.com/75012998/103278971-1825e180-4a10-11eb-878a-f146eeb1a1c4.png)

---

![2번](https://user-images.githubusercontent.com/75012998/103278979-1cea9580-4a10-11eb-80d4-b7a477c01f38.png)

![2-1번](https://user-images.githubusercontent.com/75012998/103278985-21af4980-4a10-11eb-98ab-b6cd1a0ea306.png)

- HTML 소스코드

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="EUC-KR">
    <title>Insert title here</title>
    </head>
    <body>
    	<form action ="formex" method = "post">
    		이름 : <input type = "text" name = "uname"><br/>
    		아이디 : <input type = "text" name = "uid"><br/>
    		비밀번호 : <input type = "password" name = "upw"><br/>
    		취미 : 독서<input type = "checkbox" name = "hobby" checked = "checked" value = "read">
    		요리<input type = "checkbox" name = "hobby" value = "cook">
    		조깅<input type = "checkbox" name = "hobby" value = "run">
    		수영<input type = "checkbox" name = "hobby" value = "swim">
    		취침<input type = "checkbox" name = "hobby" value = "sleep"><br/>
    		전공 : 국어<input type = "radio" name = "major" value = "kor">
    		수학<input type = "radio" name = "major" value = "math">
    		영어<input type = "radio" name = "major" value = "eng">
    		디자인<input type = "radio" name = "major" value = "design"><br/>
    		<select name = "pro">
    			<option>ftp</option>
    			<option>http</option>
    			<option>smtp</option>
    			<option>pop</option>
    		</select><br/>
    		<input type = "submit" value = "전송">
    		<input type = "reset" value = "초기화">
    	</form>
    </body>
    </html>
    ```

- 결과

    ![2번답2](https://user-images.githubusercontent.com/75012998/103279005-2b38b180-4a10-11eb-80c4-a8a3b8d3d1d1.png)

![2번답](https://user-images.githubusercontent.com/75012998/103278994-2673fd80-4a10-11eb-89f0-d05a8e8f086c.png)

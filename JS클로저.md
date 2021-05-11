# 2021-01-19(JS(클로저),SP(IOC))

### 1. 클로져란 무엇인가?

> 클로져

- 내부함수가 외부함수의 지역변수에 접근가능
- 외부함수는 외부함수의 지역변수를 사용하는 내부함수가 소멸될 때까지 소멸되지 않는 특성을 의미한다.
- 즉, 함수 밖에서 선언된 변수를 함수 내부에서 사용할 때이다.

**클로져의 예**

```jsx
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
</head>
<body>
	<script type = "text/javascript">
	function funName(x){
		var varName = ":: 요청한 " + x + "에 대한 구구단 ::";

		return function(){
			console.log(varName);
			for(var i=1 ; i < 10; i++){
					console.log(x + " x " + i + " = " + (x*i));
		}
	}
}
	</script>
```

---

### 2. js를 이용하여, 구구단 중 홀수단만 나오게 하시오.

```jsx
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
</head>
<body>
	<script type = "text/javascript">
	document.write("<table border = 1>");
		document.write("<tr>");
		for(var i=2 ; i <= 9 ; i++){
			if(i % 2 != 0){
				document.write("<td>"+ i +"단"+"</td>");
			}
		}
		document.write("</tr>");
		
		for(var i=1 ; i <=9 ; i++){
			document.write("<tr>");
			for(var j=2 ; j <= 9 ; j++){
				if(j % 2 != 0){
					document.write("<td>" + j + "x" + i + "=" + (j*i) + "</td>");
				}
			}
			document.write("</tr>");
		}
		document.write("</table>");
	</script>
```

---



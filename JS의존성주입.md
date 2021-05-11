# 21-01-20(JS-DI)

### 1. 아래를 설명하시오.

> DI(의존성 주입)

- 필요한 객체를 직접 생성하는 것이 아닌 외부로부터 필요한 객체를 받아서 사용하는것
- 객체간의 결합도를 줄이고 코드의 재활용성이 높아짐.

**의존성 주입 방법**

  1. 생성자를 통한 전달

  2. setter함수를 통한 전달

  3. 멤버 변수를 통한 전달

> IoC(제어의 역전)

- 의존관계의 제어를 개발자가 직접하지 않고 IoC 컨테이너로 넘어가 객체의 생성부터 생명주기의 관리까지 객체에 대한 제어권이 바뀐것

> Ioc 컨테이너

- 객체에 대한 생성 및 생명주기를 관리하는 기능을 제공한다.
- 객체의 생성을 책임지고 의존성을 관리한다.
- Bean 설정 소스로부터 Bean정의를 읽어들여 구성하고 제공하는 역할이다.

---

### 2. JS로 시간이 초단위로 갱신되는 페이지를 만드시오.

- 자바스크립트 소스코드

  ```jsx
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="EUC-KR">
  <title>Insert title here</title>
  </head>
  <body>
  <script type = "text/javascript">
  setInterval(function() {
  		var today = new Date();
  		var hours = today.getHours();
  		var min = today.getMinutes();
  		var sec = today.getSeconds();
  		document.write(hours + " : " + min + " : " + sec + "<br/>");
  	}, 1000);
  </script>
  </body>
  </html>
  ```

---

### 3. js 에서의 객체생성 방법은?

 **1. 기본적인 객체 생성방법**

```jsx
var 객체 변수명 = 
	{ key1 : value1,
		key2 : value2,
		key3 : value3,
		...
		key : value;
};
```

 **2. 함수를 이용한 객체 생성방법**

```jsx
function 함수명(){
	var 객체명 = {
		...
	};
	return 객체명;
};
```

 **3. 생성자를 이용한 객체 생성**

```jsx
function 생성자 함수명(){
	key1 : value1;
	key2 : value2;
	...
	key : value
};

new 생성자 함수명();
```

---

### 4. 아래를 자바 스크립트로 작성하시오.

```jsx
-변수 radius
-get set 함수 작성
-프롬프트로 숫자 입력값 받음
-set 함수를 radius 값 세팅
-객체 생성후 getArea() 함수 호출하면 원넓이 출력
```

- 자바스크립트 소스코드

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="EUC-KR">
  <title>Insert title here</title>
  </head>
  <body>
  	<script type = "text/javascript">
  	function Circle(){
  			var radius;
  		
  			this.setRadius = function(radius){
  				if(!isNaN(radius)){
  					this.radius = radius;
  				}else{
  					console.log("radius is NaN(Not a Number!)");
  				};
  			};
  			
  			this.getRadius = function(){
  				return this.radius;
  			}
  			
  			this.getArea = function(){
  				return this.radius * this.radius * 3.14;
  			}
  		}
  		
  		var circle = new Circle();
  		circle.setRadius(5);
  		console.log("원의 넓이 : " + circle.getArea());	
  	</script>
  </body>
  </html>
  ```

- 결과

  ![Untitled](https://user-images.githubusercontent.com/75012998/105166747-22dd1d80-5b5b-11eb-99ef-4cc9ce552dc0.png)

---

### 5. 위와 같은 방식으로 가위바위보 게임을 짜시오.

- 자바스크립트 소스코드

  ```jsx
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="EUC-KR">
  <title>Insert title here</title>
  </head>
  <body>
  	<script type = "text/javascript">
  		function Game(){
  			var player;
  			var com = Math.floor(Math.random()*3)+1;
  			
  			this.setPlayer = function(player){
  				if(player == 1){
  					if(com == 3){
  						console.log("user : 1");
  						console.log("com : " + com);
  						console.log("결과 : 승리!");
  					}else if(com == 2){
  						console.log("user : 1");
  						console.log("com : " + com);
  						console.log("결과 : 패배..");
  					}else{
  						console.log("user : 1");
  						console.log("com : " + com);
  						console.log("결과 : 무승부~");
  					};
  				}
  					else if(player == 2){
  					    if(com == 1){
  					    	console.log("user : 2");
  					    	console.log("com : " + com);
  					    	console.log("결과 : 승리!");
  						}else if(com == 3){
  							console.log("user : 2");
  							console.log("com : " + com);
  							console.log("결과 : 패배..");
  						}else{
  							console.log("user : 2");
  							console.log("com : " + com);
  							console.log("결과 : 무승부~");
  						};
  					}
  					    else if(player == 3){
  							if(com == 2){
  								console.log("user : 3");
  								console.log("com : " + com);
  								console.log("결과 : 승리!");
  							}else if(com == 1){
  								console.log("user : 3");
  								console.log("com : " + com);
  								console.log("결과 : 패배..");
  							}else{
  								console.log("user : 3");
  								console.log("com : " + com);
  								console.log("결과 : 무승부~");
  							};   
  					    }
  			};
  		}
  		
  		var play = new Game();
  		play.setPlayer(prompt("가위(1),바위(2),보(3)게임을 시작하겠습니다~ ","숫자를 입력해주세요!"));
  	</script>
  </body>
  </html>
  ```

- 결과

  ![Untitled 1](https://user-images.githubusercontent.com/75012998/105166760-253f7780-5b5b-11eb-90ab-f3dbc9a14d5a.png)

  ![Untitled 2](https://user-images.githubusercontent.com/75012998/105166759-24a6e100-5b5b-11eb-8137-2c45230ee8ad.png)

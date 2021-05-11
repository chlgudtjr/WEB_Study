# 2021.01.05 try&catch

### 1. 아래를 try catch 로 묶지 않으면 에러가 나는 이유를 설명하시오.

```sql
try {
			connection = dataSource.getConnection();
			String query = "insert into mvc_board (bId, bName, bTitle, bContent, bHit, bGroup, bStep, bIndent) values (mvc_board_seq.nextval, ?, ?, ?, 0, mvc_board_seq.currval, 0, 0 )";
			preparedStatement = connection.prepareStatement(query);
			preparedStatement.setString(1, bName);
			preparedStatement.setString(2, bTitle);
			preparedStatement.setString(3, bContent);
			int rn = preparedStatement.executeUpdate();
		} catch (Exception e) {
			// TODO: handle exception
			e.printStackTrace();
		}
```

전체적으로 DB의 값을 주고 받기 위해서 쓰는 3종 세트(connection, statement, resultSet)가 올바르게 실행되는지 확인하기 위해 try&catch문으로 묶어 관리하며 DB에 접근이 되었는지, DB에 쿼리 실행문이 제대로 삽입되었는지, DB에 값을 제대로 가져오는지 확인하고 예외상황을 방지하기 위해 사용하는것이다. 


---

### 2. 아래를 프로그래밍 하시오.

![11](https://user-images.githubusercontent.com/75012998/104832935-89063e00-58d8-11eb-82ef-660e33a85e5c.png)


**실행** 

[[http://localhost:8282/컨텍스트명/list.do](http://localhost:8282/%EC%BB%A8%ED%85%8D%EC%8A%A4%ED%8A%B8%EB%AA%85/list.do)]([http://localhost](http://localhost/)\:8282/컨텍스트명/list.do) 을 치면 위와같이 나오게 하면 된다.

**HINT**

여러분이 게시판 짜고 있는 소스코드에,sb admin 폴더에서 ,css 및 img 등등을 webcontent 아래로 복사해 넣으시고, tables.jsp를 분석 하신후, 위와 같이 나오도록 프로그래밍 해 봅니다.

- 결과
- 소스코드

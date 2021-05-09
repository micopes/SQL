# SQL Command

## SELECT
- 테이블에서 특정 column 선택

#### EX)
`SELECT * FROM Customers;`

`SELECT Address FROM Customers;`
<hr><br>

## DISTINCT
- 중복 제거(Unique)

#### EX)
`SELECT DISTINCT Country from Customers;` 
> Customers에서 Country를 뽑아내는데 중복되는 것은 한 번만 가져온다.
<hr><br>

## WHERE
- 특정 조건에 맞는 것만 출력

#### EX)
```
SELECT CustomerID, Address FROM Customers
WHERE CustomerID = 5;
```
> Customers에서 CustomerID가 5인 조건을 만족시키는 CustomerID, Address를 가져온다
<hr><br>

## ORDER BY
- 오름(ASC), 내림차순(DESC) 정렬 (Default는 오름차순)

#### EX)
```
SELECT * FROM Customers
ORDER BY CustomerID DESC;
```
<hr><br>

## INSERT INTO
1) 열, 값 모두 지정
2) 값만 적는 경우

#### EX)
##### 1) 
```
INSERT INTO Column1, Column2, ...
VALUES (Value1, Value2, ...
```
##### 2) 
```
INSERT INTO Table_name
VALUES (Value1, Value2, ...
```
<hr><br>

## NULL
- NULL
- NOT NULL

#### EX)
##### NULL
```
SELECT * FROM Customers
WHERE Address IS NULL
```
##### NOT NULL
```
SELECT * FROM Customers
WHERE Address IS NOT NULL
```
<hr><br>

## UPDATE
- 존재하는 Record를 수정

#### EX)
```
UPDATE Customers
SET ContactName = 'Alfred', City = 'Seoul'
WHERE CustomerID = 1
```
> CustomerID가 1인 경우 ContactName = 'Alfred', City = 'Seoul'로 수정
<hr><br>

## DELETE
- 존재하는 Record를 삭제

#### EX)
`DELETE FROM Table_name WHERE condition;`
<hr><br>

## SELECT TOP(MSSQL), LIMIT(MYSQL)
- 특정 개수만큼만 출력

#### EX)
```
SELECT * FROM Customers
ORDER BY CustomerID DESC
LIMIT 5
```
<hr><br>

## MIN/MAX/AVG/SUM/COUNT

#### EX)
`SELECT MIN(CustomerID) FROM Customers`

`SELECT MAX(CustomerID) FROM Customers`

`SELECT AVG(CustomerID) FROM Customers`

`SELECT SUM(CustomerID) FROM Customers`

`SELECT COUNT(CustomerID) FROM Customers`
<hr><br>

## LIKE
- 특정 Pattern 검색

#### EX) 
```
SELECT * FROM Customers
WHERE Address LIKE 'a%'
```
- 'a%' : 'a'로 시작하는 경우
- '%a' : 'a'로 끝나는 경우
- '%da%' : 어디에든 da가 끼어있는 경우
- '_r%' : 두 번째 문자 'r'
- a_% : a로 시작, 적어도 문자 2개
- a__% : a로 시작, 적어도 문자 3개
- a%o : a로 시작해서 o로 끝나는 경우

### WILDCARD
- '%' : 모든
- '_' : 빈 character
- '[]' : bracket에 있는 것 중 하나라도 포함
- '^' : NOT
- '-' : a-z이면 a부터 z까지.
<hr><br>

## IN
- WHERE에 있는 것 출력

#### EX) 
```
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France')
```
> Country가 ('Germany', 'France') 중에 해당되면 Customers의 *(모든 것) 출력
<hr><br>

## BETWEEN
- 사이 (WHERE 시 사용)

#### EX)
```
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
```
<hr><br>

## AS(Aliases)
- 이름 변경(별명) -> **해당 쿼리 동안만 유지된다.**

#### EX)
```
SELECT CustomerID AS ID, CustomerNAme AS Customer
FROM Customers
```
<hr><br>

## JOIN
- 테이블 간에 합치는 것.

종류 :
- INNER
- LEFT
- RIGHT
- FULL OUTER
- SELF

#### EX)
```
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```
<hr><br>

## UNION/UNION ALL
- UNION : A와 B의 합집합을 구해서 DISTINCT된 교집합을 출력
- UNION ALL : A와 B의 합집합을 구해서 교집합을 출력(DISTINCT X)
<hr><br>

## GROUP BY
- 해당 그룹에 해당하는 것을 보여줌.

#### EX)
```
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC
```
> 각 Country의 Customer 수, 정렬(내림차순)
<hr><br>

## HAVING
- WHERE은 집계함수 사용 불가. 주로 GROUP BY시 사용된다

#### EX)
```
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID)
```
<hr><br>

## EXISTS/NOT EXISTS
- 교집합에 해당하는 것을 골라내려고 하는 것.
- IN, NOT IN으로 대체 가능

#### EX)
SELECT * FROM Customers A
WHERE EXISTS (SELECT CustomerID FROM Customers B WHERE A.CustomerID = B.CustomerID)
<hr><br>

## ANY/ALL
- BOOL 값 반환
- 영어 단어 뜻 그대로 이해

#### EX)
```
SELECT ProductName FROM Products
WHERE ProductID = ANY(SELECT ProductID FROM OrderDetails WHERE Quantity > 10);
```
> 조건 만족하는 것 있으면 Products에서 ProductName 출력
<hr><br>

## SELECT INTO
- 복사

#### EX)
`SELECT * INTO CustomerBackup FROM Customers`
<hr><br>

## INSERT INTO ... SELECT

#### EX
```
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers;
```
> Suppliers의 Column 3항목을 Customers의 Column 3항목에 넣어준다.
<hr><br>

## Case .. WHEN

#### EX)
```
SELECT OrderID, Quantity
CASE
  WHEN Quantity > 30 THEN 'The quantity is greater than 30'
  WHEN Quantity = 30 THEN 'The quantity is 30'
  ELSE 'The quantity is under 30'
END AS QuantityText
```
> 추가 행(QuantityText)에 문자열이 각각 저장.
  

## Comment(주석)
`--`

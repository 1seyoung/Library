

## SELECT 문
기본적인 데이터 조회에 사용

```SQL
SELECT column1, column2 
FROM table_name 
WHERE condition;
```


## JOIN
여러 테이블의 데이터를 결합할 때 사용

```SQL
SELECT * 
FROM table1 
INNER JOIN table2 ON table1.id = table2.id;
```

SQL에는 여러 종류의 JOIN이 있음
1. INNER JOIN: 두 테이블에서 일치하는 행만 반환
2. LEFT (OUTER) JOIN: 왼쪽 테이블의 모든 행과 오른쪽 테이블의 일치하는 행을 반환
3. RIGHT (OUTER) JOIN: 오른쪽 테이블의 모든 행과 왼쪽 테이블의 일치하는 행을 반환
4. FULL (OUTER) JOIN: 양쪽 테이블의 모든 행을 반환하며, 일치하지 않는 경우 NULL 값으로 채움
5. CROSS JOIN: 두 테이블의 모든 가능한 조합을 반환 (카테시안 곱).
6. SELF JOIN: 동일한 테이블을 자신과 조인
7. NATURAL JOIN: 두 테이블에서 이름이 같은 모든 열을 기준으로 자동으로 조인
8. SEMI JOIN: 서브쿼리를 사용하여 조건을 만족하는 행만 반환 (EXISTS 사용).
9. ANTI JOIN: 서브쿼리 조건을 만족하지 않는 행만 반환 (NOT EXISTS 사용).

## GROUP BY와 집계 함수
데이터를 그룹화하고 요약할 때 사용

```SQL
SELECT category, COUNT(*) as count 
FROM products 
GROUP BY category 
HAVING COUNT(*) > 10;
```

## 서브쿼리
쿼리 내에 또 다른 쿼리를 넣을 때 사용

```SQL
SELECT name 
FROM employees 
WHERE department_id IN (SELECT id FROM departments WHERE location = 'New York');
```

## 윈도우 함수
행들의 그룹에 대한 계산을 수행

```SQL
SELECT name, salary, 
	RANK() OVER (ORDER BY salary DESC) as salary_rank 
FROM employees;
```

## CASE 문
조건에 따라 다른 결과를 반환할 때 사용

```SQL
SELECT name, 
	CASE 
		WHEN age < 18 THEN 'Minor' 
		ELSE 'Adult' 
	END AS age_category
FROM customers;
```

## 문자열 함수
문자열을 조작할 때 사용

```SQL
SELECT CONCAT(first_name, ' ', last_name) AS full_name, 
	UPPER(email) AS email_upper 
FROM users;
```

## 날짜 함수
날짜와 시간을 다룰 때 사용

```SQL
SELECT order_date, 
	EXTRACT(YEAR FROM order_date) AS order_year 
FROM orders;
```

## UNION과 INTERSECT
여러 쿼리 결과를 결합하거나 교집합을 찾을 때 사용

```SQL
SELECT product_id FROM orders_2023 
UNION 
SELECT product_id FROM orders_2024;
```

## WITH 절 (CTE)

복잡한 쿼리를 간단하게 만들 때 사용

```SQL
WITH high_value_orders AS ( 
	SELECT * FROM orders WHERE total_amount > 1000 
) 
SELECT customer_id, AVG(total_amount) 
FROM high_value_orders 
GROUP BY customer_id;
```

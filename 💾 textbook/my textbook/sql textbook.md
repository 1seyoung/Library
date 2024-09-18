SQL(Structured Query Language)은 관계형 데이터베이스에서 데이터를 관리하고 조작하는 표준 언어입니다. 데이터 엔지니어는 SQL을 사용해 데이터베이스를 설계, 관리, 최적화하며, 데이터를 효율적으로 쿼리할 수 있어야 합니다. 이 문서에서는 SQL의 핵심 개념과 문법을 자세하게 설명합니다.

# 1. SQL의 기본 개념

## 1.1 데이터베이스와 테이블

- **데이터베이스**는 여러 테이블의 집합이며, 테이블은 행(Row)과 열(Column)로 구성된 2차원 데이터 구조입니다.
- **행(Row)**: 데이터의 한 레코드.

- **열(Column)**: 데이터의 속성이나 필드.

```sql
CREATE DATABASE company;
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    position VARCHAR(50),
    salary DECIMAL(10, 2)
);
```

# 2. 데이터 조회: SELECT

SQL의 가장 기본적인 명령어는 데이터를 조회하는 SELECT입니다. 다양한 조건과 필터링을 통해 데이터를 추출할 수 있습니다

## 2.1 기본 SELECT 문법

```sql
SELECT column1, column2 FROM table_name;
```

- **column1**, **column2**: 선택하고자 하는 테이블의 열.
- **table_name**: 데이터를 조회할 테이블.

예시
```sql
SELECT name, position FROM employees;
```

## 2.2 WHERE 절를 통한 조건 검색

WHERE 절은 특정 조건에 맞는 데이터를 필터링할 때 사용됩니다.

```sql
SELECT column1, column2 FROM table_name WHERE condition;
```

예시
```sql
SELECT name, salary FROM employees WHERE salary > 50000;
```

**2.3 AND, OR, NOT 연산자**

복합 조건을 정의할 때 사용합니다

- **AND**: 두 조건 모두 참일 때.

- **OR**: 두 조건 중 하나라도 참일 때.

- **NOT**: 조건이 거짓일 때.

예시:
```sql
SELECT name, position FROM employees
WHERE position = 'Manager' AND salary > 70000;
```

## 2.4 ORDER BY: 정렬

ORDER BY 절을 사용하여 데이터를 오름차순(ASC) 또는 내림차순(DESC)으로 정렬할 수 있습니다.

```sql
SELECT column1, column2 FROM table_name ORDER BY column1 [ASC|DESC];
```
\
예시
```sql
SELECT name, salary FROM employees ORDER BY salary DESC;
```


## 3. 데이터 조작: INSERT, UPDATE, DELETE


## 3.1 INSERT INTO: 데이터 삽입

테이블에 새로운 데이터를 추가할 때 사용합니다.

```sql
INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);
```

예시
```sql
INSERT INTO employees (employee_id, name, position, salary)
VALUES (1, 'John Doe', 'Manager', 80000);
```

## 3.2 UPDATE: 데이터 업데이트

기존 데이터를 수정할 때 사용합니다.

```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```

예시
```sql
UPDATE employees SET salary = 85000 WHERE employee_id = 1;
```


## 3.3 DELETE: 데이터 삭제

특정 조건에 맞는 데이터를 삭제할 때 사용합니다.

```sql
DELETE FROM table_name WHERE condition;
```

```sql
DELETE FROM employees WHERE employee_id = 1;
```

# 4. 집계 함수와 그룹화: GROUP BY, HAVING


## 4.1 집계 함수

SQL에는 데이터를 요약하는 다양한 집계 함수가 있습니다.

- **COUNT()**: 행의 개수를 계산.
- **SUM()**: 값들의 합을 계산.
- **AVG()**: 평균을 계산.
- **MIN()**: 최소값을 반환.
- **MAX()**: 최대값을 반환.

## 4.2 GROUP BY: 그룹화

GROUP BY 절은 동일한 값을 가진 행을 그룹으로 묶고, 집계 함수를 적용할 때 사용됩니다.

```sql
SELECT column1, COUNT(*) FROM table_name GROUP BY column1;
```

예시
```sql
SELECT position, AVG(salary) FROM employees GROUP BY position;
```

## 4.3 HAVING: 그룹화된 데이터 필터링

HAVING 절은 GROUP BY 절과 함께 사용되어 집계된 결과에 필터를 적용합니다.

```sql
SELECT column1, COUNT(*) FROM table_name GROUP BY column1 HAVING COUNT(*) > value;
```

예시
```sql
SELECT position, COUNT(*) FROM employees
GROUP BY position HAVING COUNT(*) > 2;
```

# 5. JOIN: 테이블 간 데이터 결합

**JOIN**은 두 개 이상의 테이블을 결합할 때 사용합니다.

**5.1 INNER JOIN**

두 테이블에서 공통된 값이 있는 행만 반환합니다.
```sql
SELECT column1, column2
FROM table1
INNER JOIN table2 ON table1.column = table2.column;
```

```sql
SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments ON employees.department_id = departments.department_id;
```


## 5.2 LEFT JOIN

왼쪽 테이블의 모든 행을 반환하고, 오른쪽 테이블과 일치하지 않는 경우 NULL을 반환합니다.

```sql
SELECT column1, column2
FROM table1
LEFT JOIN table2 ON table1.column = table2.column;
```

예시
```sql
SELECT employees.name, departments.department_name
FROM employees
LEFT JOIN departments ON employees.department_id = departments.department_id;
```


## 5.3 RIGHT JOIN


오른쪽 테이블의 모든 행을 반환하고, 왼쪽 테이블과 일치하지 않는 경우 NULL을 반환합니다.
```sql
SELECT column1, column2
FROM table1
RIGHT JOIN table2 ON table1.column = table2.column;
```

## 5.4 FULL OUTER JOIN

두 테이블에서 일치하는 값이 없더라도 모든 행을 반환합니다.
```sql
SELECT column1, column2
FROM table1
FULL OUTER JOIN table2 ON table1.column = table2.column;
```

# 6. 서브쿼리와 CTE (Common Table Expressions)


## 6.1 서브쿼리

서브쿼리는 다른 쿼리 내에 포함된 쿼리로, 주 쿼리의 조건을 정의하거나 데이터를 제한할 수 있습니다.
```sql
SELECT column1
FROM table_name
WHERE column2 = (SELECT MAX(column2) FROM table_name);
```

예시
```sql
SELECT name FROM employees WHERE salary = (SELECT MAX(salary) FROM employees);
```


## 6.2 CTE (Common Table Expressions)

CTE는 임시 결과를 정의하는 방법으로, 복잡한 쿼리를 더 읽기 쉽게 만듭니다.
```sql
WITH cte_name AS (
    SELECT column1, column2
    FROM table_name
)
SELECT * FROM cte_name;
```


예시
```sql
WITH high_salary_employees AS (
    SELECT name, salary FROM employees WHERE salary > 60000
)
SELECT * FROM high_salary_employees;
```



# 7. 인덱스와 성능 최적화

  
데이터베이스에서 빠른 검색을 위해 **인덱스**를 사용하는 것이 중요합니다. 인덱스는 테이블의 특정 열에 대해 검색 속도를 향상시킵니다.
```sql
CREATE INDEX index_name ON table_name(column_name);
```

예시:
```sql
CREATE INDEX idx_employee_salary ON employees(salary);
```

인덱스는 데이터를 읽을 때 속도를 크게 향상시키지만, 데이터를 삽입하거나 수정할 때는 성능 저하가 발생할 수 있으므로 적절히 사용하는 것이 중요합니다.


# 결론


SQL은 데이터 엔지니어가 데이터를 효율적으로 처리하고 관리하는 데 필수적인 도구입니다. 데이터를 조회하고 조작하는 기본 쿼리 문법부터 테이블 간 데이터를 연결하는 JOIN, 집계 함수, 성능 최적화를 위한 인덱스까지 SQL의 다양한 기능을 이해하고 활용하는 것이 중요합니다.
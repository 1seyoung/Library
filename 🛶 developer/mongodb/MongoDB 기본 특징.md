
MongoDB 는 기존의 테이블 기반 관계형 데이터베이스 구조가 아닌 문서 지향 데이터 모델을 사용하는 교차 플랫폼 오픈 소스 데이터베이스

비필수 스키마와 함께 JSON과 같은 문서를 사용하여 대량의 데이터를 저장하는 NoSQL 데이터베이스, 유연한 데이터 저장 모델을 통해 사용자는 쿼리를 더 쉽게 작성할 수 있고, 또한 개발자도 데이터베이스를 더 쉽게 관리 가능

## 관계형 DB와 MongoDB 차이
| 관계형 DB    | MongoDB         |
| ------------ | --------------- |
| Table        | Collection      |
| Row          | Document        |
| Column       | Field           |
| Primary Key  | Object_id Field |
| Relationship | Embedded & Link |

- MongoDB와 MySQL 에서 동일한 데이터를 가지고 CRUD 를 수행할 때, 대부분의 결과가 MongoDB가 빠르게 나옴
- MongoDB의 경우 , Single Node 와 Multi Node 간에 성능 차이는 거의 없음(Delete 연산을 제외하고 대부분 Multi Node 가 근소하게 빠름)
- MongoDB Multi Node의 Insert 연산 중에 연산 실패가 일어나는 경우 발생
- 분산을 목적으로 DBMS 선택할 경우, RDBMS에 비해 낮은 비용과 빠른 성능을 제공하는 MongoDB 유리

## MongoDB 특징
### 🧩 MongoDB 장점
- Schema-less 구조
	- 다양한 형태의 데이터 저장 가능
	- 데이터 모델의 유연한 변화 가능
- Read/Write 성능이 뛰어남
- Scale Out 구조
	- 많은 데이터 저장이 가능
	- 장비 확장이 간단함
- JSON 구조 : 데이터를 직관적으로 이해 가능
- 사용 방법이 쉽고, 개발이 편리
 
### 🧩 MongoDB 단점
- 데이터 업데이트 중 장애 발생 시, 데이터 손실 가능
- 많은 인덱스 사용 시 , 메모리 확보 문제
- 데이터 공간 소모가 RDBMS 에 비해 많음(비효율적인 중복 key 입력)
- 복잡한 JOIN 사용 시 성능 제약이 따름
- 트랜잭션 지원이 미약
- 제공되는 MapReduce 작업이 Hadoop에 비해 성능 떨어짐

#### MongoDB 불안정성
데이터의 양이 많을 경우 문제가 생긴다
- 일부 데이터가 손실 가능성 존재
- 샤딩의 비정상적인 동작 가능성
- 레플리카 프로세스의 비정상 동작 가능성


### 🧩 빅데이터 처리 특화
- [[Memory Mapped]](데이터 쓰기 시에 OS 의 가상 메모리에 데이터를 넣은 후 비동기로 디스크에 기록하는 방식)을 사용
- 방대한 데이터를 빠르게 처리 가능
- OS 의 메모리를 활용하기 때문에 메모리가 차면 하드디스크로 데이터 처리하여 속도가 급격히 느려짐
- 하드웨어적인 측면에서 투자 필요

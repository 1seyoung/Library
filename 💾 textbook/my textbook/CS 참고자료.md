# 1-1 Development Common Sense

## ▶ OOP: Object Oriented Programming
- **객체 지향 프로그래밍**: 인간 중심적 프로그래밍, 재사용성, 디버깅이 쉽고 유지보수에 용이
- **SRP (Single Responsibility Principle)**: 단일 책임 원칙
- **OCP (Open/Closed Principle)**: 개방-폐쇄 원칙
- **LSP (Liskov Substitution Principle)**: 리스코프 치환 원칙
- **ISP (Interface Segregation Principle)**: 인터페이스 분리 원칙
- **DIP (Dependency Inversion Principle)**: 의존관계 역전 원칙

### SRP (Single Responsibility Principle): 단일 책임 원칙
한 클래스는 하나의 책임, 변경이 있을 때 파급 효과가 적으면 단일 책임 원칙을 잘 따른 것. 클래스는 단 하나의 책임을 가져야 하며, 클래스를 변경하는 이유는 단 하나의 이유여야 한다.

### OCP (Open/Closed Principle): 개방-폐쇄 원칙
확장에 열려있으나 변경에 닫혀 있어야 한다. 다형성 활용, 역할과 구현의 분리.  
> **문제점**: 구현 객체를 변경하려면 클라이언트 코드 변경이 필요, 객체를 생성하고 연관관계를 맺어주는 별도의 조립, 설정자 필요.

### LSP (Liskov Substitution Principle): 리스코프 치환 원칙
프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 함. 상위 타입의 객체를 하위 타입으로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 한다.

### ISP (Interface Segregation Principle): 인터페이스 분리 원칙
특정 클라이언트를 위한 인터페이스 여러 개가 범용 인터페이스 하나보다 나음.  
예시: 자동차 인터페이스 -> 운전 인터페이스/정비 인터페이스로 분리.

### DIP (Dependency Inversion Principle): 의존관계 역전 원칙
추상화에 의존해야지, 구체화에 의존하면 안 된다. 클라이언트 코드가 구현 클래스가 아닌 인터페이스만 바라봐야 한다. 고수준 모듈은 저수준 모듈의 구현에 의존해서는 안 된다.

---

## ▶ RESTful API
- **REpresentational State Transfer**
  
### REST 6 원칙
- Uniform Interface
- Stateless
- Caching
- Client-Server
- Hierarchical System
- Code on demand

### RESTful하게 API를 디자인한다는 것은?
리소스와 행위를 명시적이고 직관적으로 분리한다. 리소스는 URI로, 행위는 HTTP Method로 표현.

- **GET**: 조회
- **POST**: 생성
- **PUT**: 기존 Entity 전체 수정
- **PATCH**: 기존 Entity 일부 수정
- **DELETE**: 삭제

### REST API 장점
- Open API 제공 쉬움
- 멀티플랫폼 지원 및 연동 용이
- 원하는 타입으로 데이터 주고받기
- 기존 앱 인프라(HTTP)를 그대로 사용할 수 있음

### REST API 단점
- 메소드 한정적
- 분산환경에 부적합
- HTTP 통신 모델에 한정되어 지원

---

## ▶ TDD: Test-Driven Development
짧은 개발 사이클의 반복에 의존하는 소프트웨어 개발 프로세스. 기능을 추가하기 전 테스트를 먼저 작성하며, 요구사항과 명세를 이해한 후 개발.

### TDD 장점
- 요구사항에 집중할 수 있도록 함.
- 리팩토링 과정에서 테스트 코드가 중심을 잡아줌.  
- 객체 지향적이고 확장이 가능한 코드, 디버깅 시간이 단축.

### TDD 단점
- 코드량 증가
- 빠른 생산성이 요구되는 경우 걸림돌이 될 수 있음.
- 모든 상황에 대한 테스트 코드 작성 시 진입장벽 존재.

---

## ▶ 함수형 프로그래밍

### Immutable vs Mutable
- **Immutable**: 변경 불가. 값이 변경될 경우 새로운 객체 생성 후 반환.

### First-class citizen
- 함수형 프로그래밍에서 함수는 일급 객체로 간주. 함수를 변수에 할당하거나, 인자로 전달하거나, 반환 가능.

### First-class 함수 특성
- 함수 할당: 함수를 변수에 할당할 수 있음.
- 함수 인자: 함수를 다른 함수의 인자로 전달할 수 있음.
- 함수 반환: 함수에서 다른 함수를 반환할 수 있음.
- 데이터 구조 내 저장: 함수를 배열, 리스트, 딕셔너리 등 데이터 구조 내 저장 가능.

### 장점
- 재사용성이 높음.






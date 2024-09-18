

[super driven ui(1)](https://techblog.yogiyo.co.kr/%EC%9A%B0%EB%8B%B9%ED%83%95%ED%83%95-server-driven-ui-%EA%B0%9C%EB%B0%9C%EA%B8%B0-b1b80f47760b)

[super driven ui(2)](https://blog.udon.party/posts/Server-Driven-UserInterface/)

- 계속해서 공부하고 회사가 사용하는 기술 및 언어를 사용할 줄 알아야함
- 장기간 목표를 위해서 기술을 익혀야 함

### 추천하는 개발 관련 자료

- Developer Trend Report
- Developer Survey
- Google Trend
- Hype Cycle for Engineer : [gartner.com](http://gartner.com)
    - 데이터 확인 시 이전 자료도 함께 봐야함

## 직무별 중요성

### 백엔드

중장기적 설계, 안정성, 성능

개발 결과물에 대한 기능 테스트, 성능 모니터링,

what if ? 중장기적으로 좋은 구현인가? process logic as date

_**하드코딩 금물**_

### 프론트엔드

결과물을 어떻게 사용하는지에 가장 높은 관심

UX 디자인, Userability

템플릿 기반 O , _**하드코딩 금물**_

### 임베디드

꼼꼼함, 끈기

하드웨어와 소프트웨어의 통합 능력

제약된 환경에서 효율적인 개발

→ 자신만의 프레임워크 구축

→ 기능, 성능 모니터링 방법 구축

## 개발자 취업을 위한 준비

Github → 꾸준하고 다양한 프로젝트, 의미있는 프로젝트

## 취업 이후

- 기반 기술 강화
- 지속적 자기계발
- 커뮤니케이션, 경험, 커리어 관리
- 적절한 근무기간 유지(최소 8개월)

---

## **배운점 정리**

- 10년 뒤까지 살아남는 기술은 없다, 일을 하면서 끊임없이 자기 개발이 필요하다
- 기술 혹은 현재 상황에 안주하지 말 것 , 유동적인 기술 스택을 가질 수 있도록 할 것
- 컴퓨터공학과(혹은 공대) 장점을 가져갈 수 있는 직무를 고를 것
    - FE → 비전공자의 비율 높음 , 접근성이 높다

## wavve의 대규모 트래픽 대응법

- [**Super-Driven UI**](https://www.notion.so/Super-Driven-UI-dbc8cb3feae94679aedfab9cf7cb0deb?pvs=21)
    - 백엔드 데이터에 의해 변화하는 UI
    - 앱 업데이터 없이 유저에게 변경된 UI 제공 가능
    - ABTest 에 용이하다
- Web : Vue.js
- Android : Native
- iOS : Native

## 대규모 트래픽을 처리하는 시스템에서 확장성과 성능의 개선

### 웹스케일 기반의 플랫폼 구축

- Cloud
- Docker, Kubernetes, API Gateway, Autoscale
- Microservice
- NoSQL

## 백엔드 개발에서 데이터베이스 선택 기준

필요한 기능에 따라 다르다

- RDBMS : 정규화가 필요한 원장 데이터
- DocumentDB : 캐시, 비정규화, 비표준 필드
- GraphDB : 데이터 연관성이 중요, 연관성에 property 부여
- key-value storage : 가장 간단하고 빠른 시스템
- Wide-column : RDB와 유사하지만, row가 아니라 wide-column에 저장

## 보안을 고려한 백엔드 시스템

- REST API 호출에 pre-generated security token 사용
- 보안이 필요한 개인정보 관련 데이터는 별도의 VP에 저장하고, gateway를 통해서만 접근가능하도록 구축, 모든 호출/응답을 로그로 저장(개인정보는 해시처리)
- 고도의 보안 필요 → Challenge-response 방식으로 구축
- (중요)플랫폼 내부에서 흔히 사용하는 고객번호(user_id, user_number, 단순 일련번호)도 개인정보로 간주 → Hash 값 사용하는 것 권장

## 백엔드 개발에서의 성능 최적화를 위해 고려할 사항

- Auto scale, Micriservice, Kubernetes, NoSQL 등 고성능 기술을 적용
- 꼭 필요한 경우에만 접근
    - Redis Cache 적극 활용
    - Rest Call, Database Access
- 의미 없는 대량의 데이터 전송/ 수신 지양
    - 필요한 필드만 주고 받도록 프로토콜 설계
- DB query 를 사용하는 경우 개발사에 반드시 Index 적용 여부 확인
    - 레코드가 늘어나면 문제 발생
- 모니터링
    - 로깅






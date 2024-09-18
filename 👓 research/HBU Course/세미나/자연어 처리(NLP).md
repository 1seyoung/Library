## 정의
### Natural Language Processing(NLP)
- 컴퓨터가 인간의 언어를 이해/모사 하도록 하는 학문
- 이를 바탕으로 각종 정보처리
- 언어학 + 컴퓨터공학 + 인공지능
- for 구조화 되지 않은 비정형 텍스트 데이터
### NLU(Natural Language Understanding)
- 자연어 형태의 문장을 이해하는 기술
- 문서 분류 , 개체명 인식, 형태소 분석

### NLG(Natural Language Generation)
- 자연어 문장의 생성하는 기술
- 번역, 문서 요약, 챗봇


## NLP for General Domian
- BERT(Pre-training of Deep Bidirectional Transformers for Language Understanding)
	- 대용량 데이터와 Transformer 의 Encoder을 이용한 언어 모델
	- 특정 분야에 국한된 기술이 아니라 모든 자연어 응용 분야에서 좋은 성능을 내는 범용 모델
	- 많은 자연어 처리 분야(GLUE)에서 기존 모델들 보다 우수한 성능을 보임


## NLP for specific Model
대부분의 텍스트 비정형 데이터는 general domain LM로 해결 가능
하지만 특정 분야(Specific Domain) (의료, 제약, 법률, 특허, 보안 ) 다른 방법이 필요함

방대한 데이터는 대부분 중복 정보/필요없는 정보가 대부분임
소수의 중요한 정보는 대부분 필요없는 정보에 가려 활용되지 못하고 있음


---

# Domain Specific Language Modeling(BERT)

## Embedding
- 컴퓨터는 인간이 사용하는 언어를 그대로 이해하는게 아니다
- 표현력이 무한한 언어를 벡터(숫자의 나열)로 변형하여 계산 -> 임베딩
- 품질이 좋은 임베딩은 좋은 성능을 야기하고 학습 수렴도 빠르다

### 단어 수준의 임배딩과 문장 수준의 임베딩
- 단어 수준의 정보, 예측 기반 임베딩(Word2Vec, FastText) 행렬 분해 방법(Glove/Swivel)
- 하지만 같은 단어도 문맥에 따라 다른 의미가 될 수 있음
	- 동의어 문제, 문맥상 의미 차이는 해결 불가함
- 문장 수준의 임베딩이 필요함(Elmo,Bert, Electra, GPT 등)

## Bert 
- 구글 + Wikipidia 대용량 데이터로 언어 학습
- 학습 방법
	1. 빈칸 맞추기 문제(Masked Language Modeling)
		- 전체 단어에서 15%를 랜덤하게 삭제 후 빈칸 맞추기

	2. 연속 대화 여부 (Next Sentence Prediction)
		- 두 문장이 연속된 문장인지, 상관없는 문장인지 맞추기
	
- 많은 데이터로 학습하고 일반 NLP에서 좋은 성능을 내지만 특정 분야에서까지 가능하지는 않았음
- ex : 보안 분야 자연어 처리의 어려움 -> 보안분야의 전문 단어, 16진수. 코드, 파일명, 

- General 하게 다양한 도메인을 커버 하는 모델도 좋지만 사용환경에 따라 특정 도메인만을 위한 NLP필요
---

특정 도메인을 위한 데이터 준비 방법 및 결과에 대한 부분 추후 작성

세미나 정보 : 국가보안기술 연구소 고우영님 "인공지능 기반 자연어처리 기술"



# MongoDB  M1 에서 사용하기

## 0. Homebrew 설치 및 업데이트

Homebrew 를 최신 버전으로 업데이트

```bash
brew update
```


## 1. MongoDB Homebrew Tap 추가

```bash
brew tap mongodb/brew
```

## 2. MongoDB Install

```shell
brew install mongodb-community@5.0
```

## 3. MongoDB 실행 및 중지

**실행**
```shell
brew services start mongodb-community@5.0
```

**중지**

```shell
brew services stop mongodb-community@5.0
```


## 4. MongoDB 연결 및 사용
MongoDB 를 실행 시킨 후 "**mongosh**" 명령어를 입력하면 Mongo Shell 이  터미널에서 실행됨


**Shell Instructions (쉘 명령어)**  
  
**show databases (=show dbs)**  
- 현재 MongoDB에 생성된 데이터베이스들의 이름과 크기를 출력한다.  
  
**show collections**  
- 현재 데이터베이스에 생성된 Collection들의 이름을 출력한다.  
  
**use <database_name>**  
- <database_name> 데이터베이스를 선택한다.  
  
**db.createCollection("<collection_name>")**  
- 현재 데이터베이스에 <collection_name> Collection을 생성한다.  
- {"ok" : 1} 메시지가 출력되면 Collection이 정상적으로 생성된 것이다.
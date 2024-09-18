
# Upstream 설정 이유
* Fork 한 repository를 최신으로 동기화하는 경우 필요함
* Fork를 하게 되면 자신의 github 레포지토리를 가르키기 때문에 git pull을 해도 자기 계정 repository로부터 데이터를 가져오게 됨
* 따라서 fork 한 대상(upstream)으로부터 최신 수정 사항을 받아오고 자신(origin)의 레포지토리에 반영하고 싶은 경우가 발생할 수 있음

# Upstream 설정
## 원본 레포지토리 설정
* 원본 레포지토리를 remote repository로 설정함
```git
~/ git remote add upstream https://github.com/ORIGINAL_PROJ/ORIGINAL_REPO.git
```

## 원본 레포지토리로부터 최신 수정사항 반영
```git
~/ git fetch upstream
```

## 로컬 브랜치에 upstream 내용 반영(main branch로 가정)
```git
~/ git checkout main 
~/ git merge upstream/main 
```

## 원격 브랜치에 upstream 내용 반영
```git
~/ git push origin main
```

# Python 기본

## 변수와 데이터 타입
python 에서는 변수를 선언할 때 타입을 명시적으로 지정할 필요가 없음
변수에 값을 할당하면 자동으로 타입이 결정됨

```python
x = 5 # 정수 
y = 3.14 # 부동소수점 
name = "Python" # 문자열 
is_true = True # 불리언
```

## 기본 연산자
python 은 다양한 연산자를 제공함

### 산술 연산자

```python
print(5 + 2) # 덧셈: 7 
print(5 - 2) # 뺄셈: 3 
print(5 * 2) # 곱셈: 10 
print(5 / 2) # 나눗셈: 2.5 
print(5 // 2) # 정수 나눗셈: 2 
print(5 % 2) # 나머지: 1 
print(5 ** 2) # 거듭제곱: 25
```

### 비교 연산자

```python
print(5 > 2) # True 
print(5 < 2) # False 
print(5 >= 5) # True 
print(5 <= 5) # True 
print(5 == 5) # True 
print(5 != 5) # False
```


## 조건문
Python에서는 `if`, `elif`, `else`를 사용하여 조건문을 작성

```python
x = 10 
if x > 0: 
	print("양수입니다") 
elif x < 0: 
	print("음수입니다") 
else: print("0입니다")
```

## 반복문
Python에서는 `for`와 `while` 루프를 사용
### for

```python
for i in range(5): 
	print(i) # 0부터 4까지 출력
```

### while

```python
count = 0 
while count < 5: 
	print(count) 
	count += 1
```


## 함수

`def` 키워드를 사용하여 정의 

```python
def greet(name): 
	return f"안녕하세요, {name}님!" 
	
print(greet("Python")) # 안녕하세요, Python님!
```


# Python 자료 구조 

## 리스트(List)
리스트는 순서가 있는 [[Python의 변경 가능한(mutable) 자료구조|변경 가능한 컬렉션]], 대괄호 `[]` 사용

### 인덱싱과 슬라이싱
- 인덱싱 : 리스트에 있는 값에 접근, 상대적인 주소를 사용하여 접근
- 슬라이싱 : 인덱스를 사용하여 리스트의 일부를 잘라내어 반환

**슬라이싱 기본 문법**

```python
변수명[시작 인덱스 : 마지막 인덱스]
```

- 리버스 인덱스 : 인덱스를 마지막 값부터 시작
![[Pasted image 20240913135740.png]]

- 증가값(step)
	- 증가값은 한 번에 건너뛰는 값의 개수
	- 슬라이싱 시 증가값을 넣을 수 있음

```python
변수명[시작 인덱스 : 마지막 인덱스 : 증가값]
```

### 리스트 연산
- 덧셈 : color1 + color2
- 곱셈 : color * 2
- in 연산 : 특정 값이 해당 리스트에 있는 지 확인

### 리스트 추가 및 삭제

- append() : 새로운 값을 기존 리스트의 맨 끝에 추가
- extend() : 새로운 리스트를 기존 리스트에 맨 끝에 추가
- insert() : 기존 리스트의 i 번째 인덱스에 새로운 값 추가
	- `color.insert(0,"orange")`
- remove() : 리스트 내의 특정 값을 삭제
- 인덱스의 재할당
- 인덱스 삭제 : del 
	- `del color[0]`

### 패킹과 언패킹
패킹 : 한 변수에 여러 개의 데이터를 할당하는 것
언패팅 : 한 변수의 데이터를 각각의 변수로 반환하는 것
![[Pasted image 20240913140325.png]]

### 이차원 리스트
대괄호 `[[]]`
- 이차원 리스트를 행렬로 본다면 [0]은 행, [2]는 열을 뜻함
![[Pasted image 20240913140445.png]]
### 리스트의 특징
- 다양한 형태의 변수가 하나의 리스트에 들어갈 수 있음 
- 중첩 리스트 가능
- 리스트의 메모리 저장
	- 파이썬에서는 리스트를 저장할 때 값이 위치한 메모리 주소 저장
	- == 은 값을 비교 is 는 메모리 주소를 비교하는 연산

![[Pasted image 20240913140659.png]]

![[Pasted image 20240913140714.png]]

### 리스트 관련 함수
- sort()
- reverse()
- index()
- pop()
- count()


## 튜플


Call by Value와 Call by Reference는 함수에 인자를 전달하는 두 가지 주요 방식이다. 함수의 매개변수에서 값을 복사하느냐 주소값을 참조하느냐에 대한 관점 차이다.


## Call by Value 
- 함수 호출 시 인자의 값이 복사되어 전달
- 함수 내에서 매개변수 값을 변경해도 원본의 변수에는 영향을 주지 않음
- 메모리 사용량이 많지만 원본 데이터를 보호할 수 있음

## Call by Reference
- 함수 호출 시 이자의 메모리 주소가 전달됨
- 함수 내에서 매개변수를 통해 원본 변수의 값을 직접 변경할 수 있음
- 메모리 사용량 적고 큰 객체를 효율적으로 전달할 수 있지만, 원본 데이터 변경될 수 있음

## Call by Value vs Call by Reference

| **항목**     | **Value**             | **Reference**                |
| ---------- | --------------------- | ---------------------------- |
| **데이터 접근** | 복사본을 사용하여 접근          | 원본에 직접 접근                    |
| **메모리 사용** | 값을 복사하므로 추가 메모리를 사용   | 주소만 전달하므로 메모리 사용이 효율적        |
| **부작용**    | 원본을 보호하는 데 유리         | 원본을 수정할 수 있으므로 부작용이 발생할 수 있음 |
| **성능**     | 작은 값일 경우 성능 차이가 크지 않음 | 큰 객체의 경우 더 효율적일 수 있음         |

## [Java] Call by Value vs Call by Reference

==**Call by Value 방식을 사용하지만 기본 타입과 참조 타입에 따라 동작이 다르게 보일 수 있음**==
### 기본 타입(Primitive Type)
기본 타입(int, char, boolean 등)을 매개변수로 전달할 때는 값의 복사본이 전달

```Java
public static void modifyValue(int x) { 
x = 20; 
} 

public static void main(String[] args) { 
int num = 10; 
modifyValue(num); 
System.out.println(num); // 출력: 10 
}
```
메소드 내에서 매개변수 값을 변경해도 원본 변수에는 영향을 주지 않음


## 참조 타입(Reference Type)
참조 타입(객체, 배열 등)을 매개변수로 전달할 때는 참조값의 복사본이 전달


```java
public static void modifyObject(Person person) { 
	person.setName("Jane"); 
}

public static void main(String[] args) {
	Person p = new Person("John"); 
	modifyObject(p);
	System.out.println(p.getName()); // 출력: Jane 
}
```
객체의 참조값이 복사되어 전달되므로 메소드 내에서 객체의 상태를 변경하면 원본 객체에도 영향

### Java에서 Call by Value와 Call by Reference가 유사하게 보이지만 실제로는 다른 이유
- 모든 전달은 Call by Value 
	- Java 는 항상 값을 복사하여 전달, 기본 타입의 경우 값 자체를 참조 타입의 경우 참조값(메모리 주소)을 복사
	- 참조값 동작
		- 객체를 전달할 때 객체의 참조값이 복사되어 전달도미
		- 이로 인해 메소드 내에서 객체의 상태를 변경하면 원본 객체에 영향을 미침
		- 이 동작이 call by reference 와 유사해보이지만 실제로는 참조값을 복사하여 전달하는 것
	- 기보 타입과 참조타입의 저장 위치 차이
		- 기본 타입 -> 스택 저장
		- 참조 타입 -> 힙에 객체 저장, 스택엔느 그 객체의 참조가 저장


## [Python] Call by Reference? Call by Value?

파이썬 공식문서에 따르면 둘 다 아니다
**Call by Assignment(Call by object-referecnce)**

Python 에서는 모든 것이 객체이며 변수는 객체에 대한 참조 저장


### 불변 객체(Immutable Objects) / 가변 객체(Mutable Objects)

#### 불변 객체
정수 , 문자열, 튜플 등의 불변 객체는 값을 직접 변경할 수 없음

#### 가변 객체
리스트, 딕셔너리, 집합 등의 가변 객체는 내용을 변경할 수 있음![[스크린샷 2024-09-24 오후 1.08.41.png]]
  
함수 내에서 리스트를 수정하면 원본 리스트도 변경

### python 고유 특징
1. **객체 참조 전달**: Python은 항상 객체에 대한 참조를 전달
2. **객체의 가변성에 따른 동작**: 객체가 가변인지 불변인지에 따라 동작이 달라짐
3. **재할당의 영향**: 함수 내에서 매개변수에 새 객체를 할당해도 원본 변수는 영향을 받지 않음
4. 


## Python vs Java

- Python은 모든 것을 객체로 취급하며, 변수는 항상 객체에 대한 참조를 저장함
- Java와 달리 Python에서는 기본 타입과 참조 타입의 구분이 없음
- Python의 가변 객체는 Java의 참조 타입과 유사하게 동작하지만, 불변 객체는 Java의 기본 타입과 유사하게 동작합니다.

Python의 이러한 특성으로 인해 "Call by Object Reference" 방식은 Call by Value와 Call by Reference의 특징을 모두 가지고 있으면서도, 고유한 동작 방식을 보여줌
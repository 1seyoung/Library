
## 1. 질문
- **질문 내용**: Call by reference란 무엇이고 보통 어떻게 쓰이나요?
  - 포인트 
	  - Call by reference <-> Call by Value

## 2. 답변
(**개요**) Call by reference는 함수 호출 시 인자의 메모리 주소를 전달하여 원본 데이터를 직접 조작할 수 있게 하는 매개변수 전달 방식입니다.
(**서술**) 이 방식은 주로 큰 객체를 효율적으로 전달하거나 함수 내에서 여러 값을 변경해야 할 때 사용됩니다. 또한 메모리 사용을 줄이고 성능을 향상시킬 수 있지만, 원본 데이터가 의도치 않게 변경될 수 있는 위험이 있으므로 주의가 필요합니다.
(**경험**)Python에서는 가변 객체를 함수에 전달할 때 마치 Call by Reference처럼 동작하여 원본 객체를 쉽게 수정할 수 있었지만, Java에서는 모든 경우에 Call by Value를 사용하므로 객체의 참조를 전달하더라도 함수 내에서 새 객체를 할당하면 원본 변수에 영향을 주지 않는 차이를 경험했습니다.

## 3. 관련 개념
![[Call by Value 와 Call by Reference]]


  
## 4. 관련 꼬리질문
1. [[Call by reference와 Call by value의 주요 차이점은 무엇인가요?]]
2. [[Java에서 객체를 전달할 때 왜 Call by value라고 하는 건가요? 객체의 참조가 전달되는 것 아닌가요?]]
3. [[Python에서 가변 객체와 불변 객체를 함수에 전달할 때의 차이점은 무엇인가요?]]
4. [[Call by reference의 장단점에 대해 더 자세히 설명해주실 수 있나요?]]
5. [[다른 프로그래밍 언어들은 Call by reference를 어떻게 구현하나요?]]
6. [[Call by reference를 사용할 때 발생할 수 있는 부작용을 방지하는 방법은 무엇인가요?]]
7. [[ 함수형 프로그래밍에서는 Call by reference를 어떻게 다루나요?]]
8. [[Call by reference와 포인터의 관계에 대해 설명해주실 수 있나요?]]
9. [[멀티스레딩 환경에서 Call by reference를 사용할 때 주의해야 할 점은 무엇인가요?]]
10. [[Call by reference가 성능에 미치는 영향에 대해 더 자세히 설명해주실 수 있나요?]]
## 5. 추가 학습 필요 사항
- Call by value와 Call by reference의 세부적인 구현 방식과 메모리 사용 차이
- Java의 객체 전달 방식과 참조 복사에 대한 깊이 있는 이해
- Python의 가변 객체와 불변 객체의 동작 방식 차이
- 다양한 프로그래밍 언어에서의 Call by reference 구현 방식
- Call by reference 사용 시 발생할 수 있는 부작용과 그 방지 방법
- 함수형 프로그래밍에서의 매개변수 전달 방식과 상태 변경 관리
- 포인터와 Call by reference의 관계 및 차이점
- 멀티스레딩 환경에서 Call by reference 사용 시 고려해야 할 동시성 문제
- Call by reference가 프로그램 성능에 미치는 영향과 최적화 방법
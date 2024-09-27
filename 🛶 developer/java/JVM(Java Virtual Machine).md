JVM(Java Virtual Machine)은 자바 프로그램을 실행하기 위한 가상 머신
JVM은 자바 바이트코드를 해석하고 실행하는 소프트웨어

## 목적
- 자바 프로그램의 플랫폼 독립성 제공
- 자바 코드를 기계어로 변환하여 실행
- 메모리 관리 및 최적화 수행

## 작동 방식

1. 자바 소스코드(.java)를 컴파일하여 바이트코드(.class)로 변환
2. 클래스 로더가 바이트코드를 JVM 메모리에 로드
3. 실행 엔진이 바이트코드를 해석하고 실행[](https://hoehen-flug.tistory.com/46)[](https://doozi0316.tistory.com/entry/1%EC%A3%BC%EC%B0%A8-JVM%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%B4%EB%A9%B0-%EC%9E%90%EB%B0%94-%EC%BD%94%EB%93%9C%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%8B%A4%ED%96%89%ED%95%98%EB%8A%94-%EA%B2%83%EC%9D%B8%EA%B0%80)

## 주요 구성 요소

**클래스 로더**

- 바이트코드를 JVM 메모리에 로드하고 링크하는 역할[](https://jh2021.tistory.com/11)

**실행 엔진**

- 인터프리터: 바이트코드를 한 줄씩 해석하여 실행
- JIT 컴파일러: 반복되는 코드를 기계어로 변환하여 성능 향상
- 가비지 컬렉터: 사용하지 않는 메모리를 자동으로 정리[](https://jh2021.tistory.com/11)[](https://doozi0316.tistory.com/entry/1%EC%A3%BC%EC%B0%A8-JVM%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%B4%EB%A9%B0-%EC%9E%90%EB%B0%94-%EC%BD%94%EB%93%9C%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%8B%A4%ED%96%89%ED%95%98%EB%8A%94-%EA%B2%83%EC%9D%B8%EA%B0%80)

**런타임 데이터 영역**

- 메서드 영역, 힙 영역, 스택 영역 등으로 구성된 메모리 공간[](https://doozi0316.tistory.com/entry/1%EC%A3%BC%EC%B0%A8-JVM%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%B4%EB%A9%B0-%EC%9E%90%EB%B0%94-%EC%BD%94%EB%93%9C%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%8B%A4%ED%96%89%ED%95%98%EB%8A%94-%EA%B2%83%EC%9D%B8%EA%B0%80)

## 장점

- 플랫폼 독립성: "Write Once, Run Anywhere" 실현
- 자동 메모리 관리: 가비지 컬렉션을 통한 효율적인 메모리 관리
- 보안: 샌드박스 모델을 통한 안전한 실행 환경 제공[](https://hoehen-flug.tistory.com/46)[](https://roadofdevelopment.tistory.com/9)
- 
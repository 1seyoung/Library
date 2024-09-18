1. **힙 기반 구현**:
    
    `PriorityQueue`의 특징
    
    - 내부적으로 힙 자료구조를 사용하여 요소를 관리합니다. 기본적으로 최소 힙으로 구현됩니다.
2. **자동 정렬**:
    
    - 요소가 삽입될 때마다 자동으로 정렬되어 우선순위가 가장 높은 요소가 먼저 처리됩니다.
3. **동적 크기**:
    
    - `PriorityQueue`는 동적으로 크기를 조정하므로, 요소의 수에 제한이 없습니다.

## 자바에서의 `PriorityQueue`

### 최소 힙(Min-Heap)

기본적으로 `PriorityQueue`는 최소 힙으로 동작합니다. 즉, 우선순위가 가장 낮은 요소가 먼저 처리

```java
import java.util.PriorityQueue;

public class MinHeapExample {
    public static void main(String[] args) {
        // 최소 힙을 구현하기 위해 PriorityQueue 사용
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();

        // 요소 추가
        minHeap.add(10);
        minHeap.add(4);
        minHeap.add(15);
        minHeap.add(2);
        minHeap.add(20);

        // 최소값 조회 (루트 노드)
        System.out.println("Minimum value: " + minHeap.peek());  // 출력: 2

        // 최소값 추출 (루트 노드 제거)
        System.out.println("Extracted minimum value: " + minHeap.poll());  // 출력: 2

        // 최소값 조회 (추출 후)
        System.out.println("Minimum value after extraction: " + minHeap.peek());  // 출력: 4

        // 모든 요소 출력
        System.out.println("All elements in the min-heap: " + minHeap);
    }
}

```

### 최대 힙(Max-Heap)

최대 힙을 구현하려면 `PriorityQueue`에 역순으로 정렬하는 `Comparator`를 제공 필요. 이를 위해 `Collections.reverseOrder()`를 사용

```java
import java.util.Collections;
import java.util.PriorityQueue;

public class MaxHeapExample {
    public static void main(String[] args) {
        // 최대 힙을 구현하기 위해 Collections.reverseOrder()를 사용
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());

        // 요소 추가
        maxHeap.add(10);
        maxHeap.add(4);
        maxHeap.add(15);
        maxHeap.add(2);
        maxHeap.add(20);

        // 최대값 조회 (루트 노드)
        System.out.println("Maximum value: " + maxHeap.peek());  // 출력: 20

        // 최대값 추출 (루트 노드 제거)
        System.out.println("Extracted maximum value: " + maxHeap.poll());  // 출력: 20

        // 최대값 조회 (추출 후)
        System.out.println("Maximum value after extraction: " + maxHeap.peek());  // 출력: 15

        // 모든 요소 출력
        System.out.println("All elements in the max-heap: " + maxHeap);
    }
}

```
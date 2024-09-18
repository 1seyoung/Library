---
link: https://www.acmicpc.net/problem/11557
algType:
  - 구현
  - 정렬
---
# Yangjojang of The Year

`브론즈1` | 구현 | 정렬

타교와의 조인트 엠티를 기획하려는 당신은 근처에 있는 학교 중 어느 학교가 술을 가장 많이 먹는지 궁금해졌다.

학교별로 한 해동안 술 소비량이 주어질 때, 가장 술 소비가 많은 학교 이름을 출력하여라.

## 입력

입력의 첫 줄에는 테스트 케이스의 숫자 T

매 입력의 첫 줄에는 학교의 숫자 정수 N(1 ≤ N ≤ 100)이 주어진다.

이어서 N줄에 걸쳐 학교 이름 S(1 ≤ |S| ≤ 20, S는 공백없는 대소문자 알파벳 문자열)와 해당 학교가 지난 한 해동안 소비한 술의 양 L(0 ≤ L ≤ 10,000,000)이 공백으로 구분되어 정수로 주어진다

```java
2
3
Yonsei 10
Korea 10000000
Ewha 20
2
Yonsei 1
Korea 10000000
```

## 출력

같은 테스트 케이스 안에서 소비한 술의 양이 같은 학교는 없다고 가정한다.

```java
Korea
Korea
``` 

## 답안

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.HashMap;
import java.util.Map;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        Map<String, Integer> map = new HashMap<>();


        String schoolName;
        Integer drink;
        String[] str;

        int T = Integer.parseInt(br.readLine().trim());
        String[] result = new String[T];
        while (T-- > 0) {
            int N = Integer.parseInt(br.readLine().trim());
            for (int i = 0; i < N; i++) {
                str = br.readLine().split(" ");
                schoolName = str[0];
                drink = Integer.parseInt(str[1]);

                map.put(schoolName, map.getOrDefault(schoolName, 0) + drink);
            }
            // 최대 값을 가진 키 찾기
            String maxKey = null;
            int maxValue = Integer.MIN_VALUE; // 초기 최대 값을 Integer의 최소 값으로 설정 -> gpt 가 그렇다네요

            for (Map.Entry<String, Integer> entry : map.entrySet()) {
                if (entry.getValue() > maxValue) {
                    maxValue = entry.getValue();
                    maxKey = entry.getKey();
                }


            }
            result[T] = maxKey;
            map.clear();
        }
        //for (int i = 0; i < T; i++) {
        //    System.out.println(result[i]);
        //}
        for (String res : result) {
            System.out.println(res);
        }


    }
}
```

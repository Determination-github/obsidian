# Do it! 알고리즘 코딩 테스트 - 자바편
---

날짜: 2023-11-28
태그:
메모:

1억번 연산
- 약 1초 정도 소요

연산 횟수
- 연산 횟수 = 알고리즘 시간 복잡도 * 데이터의 크기

디버깅하는 법
- 디버깅을 하는 방법은 코드에서 디버깅하고자 하는 줄에 중단점을 설정

자료형
- 자료형은 처음부터 long형으로 선언
- 가장 하기 쉬운 실수가 자료형 범위 오류
- 대부분의 코딩 테스트에서 계산된 값들은 long형 안에서 표현할 수 있으니 변수를 선언할 때는 처음부터 long형으로 선언

배열
- 배열은 메모리의 연속 공간에 값이 채워져 있는 형태의 자료구조
- 배열의 값은 인덱스를 통해 참조할 수 있다.
- 선언한 자료형의 값만 저장할 수 있음
- 새로운 값을 삽입하거나 특정 인덱스에 있는 값을 삭제하기 어렵다. 값을 삽입하거나 삭제하려면 해당 인덱스 주변에 있는 값을 이동시키는 과정이 필요하다.
- 배열의 크기는 선언할 때 지정할 수 있으며, 한 번 선언하면 크기를 늘리거나 줄일 수 없다.

리스트
- 리스트는 값과 포인터를 묶은 노드라는 것을 포인터로 연결한 자료구조
- 인덱스가 없으므로 값에 접근하려면 Head 포인터부터 순서대로 접근해야 한다. 다시 말해 값에 접그한는 속도가 느리다.
- 포인터로 연결되어 있으므로 데이터를 삽입하거나 삭제하는 연산 속도가 빠르다.
- 선언할 때 크기를 별도로 지정하지 않아도 된다. 다시 말해 리스트의 크기는 정해져 있지 않으며, 크기가 변하기 쉬운 데이터를 다룰 때 적절
- 포인터를 저장할 공간이 필요하므로 배열보다 구조가 복잡하다.

>노드
>컴퓨터 과학에서 값, 포인터를 쌍으로 갖는 기초 단위를 부르는 말

> Q. 숫자의 합 구하기
> N개의 숫자가 공백 없이 써 있다. 이 숫자를 모두 합해 출력하는 프로그램을 작성하시오.

A. 코드
```java
import java.util.Scanner;  
  
public class codingTest {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        int N = sc.nextInt();  
  
        // 입력 값을 String형 변수 sNum에 저장한 후 char[]형 변수로 변환하기  
        String sNum = sc.next();  
        char[] cNum = sNum.toCharArray();  
  
        int sum = 0;  
        for (int i = 0; i < N; i++) {  
            // char[]형 변수 cNum의 각 자리수를 int형으로 변환하여 sum에 더하기  
            sum += cNum[i] - '0';  
        }  
  
        System.out.println(sum);  
    }  
}
```
- char 문자를 숫자로 변환하는 방법? 
	- - '0'을 넣어주는 것
	- 아스키코드로 문자 1은 49
	- 아스키코드로 문자 0은 48
	- 때문에 char문자를 숫자로 변환할 때 '0'을 빼주면 원하는 숫자로 변환됨\

투포인터
- 시간복잡도가 O(N)
- 시작 인덱스랑 종료 인덱스를 설정(투 포인터)
- 백준문제 2018, 1940, 1253

예시)
백준 1940번

문제
> 주몽은 철기군을 양성하기 위한 프로젝트에 나섰다. 그래서 야철대장을 통해 철기군이 입을 갑옷을 만들게 하였다. 야철대장은 주몽의 명에 따르기 위하여 연구에 착수하던 중 아래와 같은 사실을 발견하게 되었다.
> 
> 갑옷을 만드는 재료들은 각각 고유한 번호를 가지고 있다. 갑옷은 두 개의 재료로 만드는데 두 재료의 고유한 번호를 합쳐서 M(1 ≤ M ≤ 10,000,000)이 되면 갑옷이 만들어 지게 된다. 야철대장은 자신이 만들고 있는 재료를 가지고 갑옷을 몇 개나 만들 수 있는지 궁금해졌다. 이러한 궁금증을 풀어 주기 위하여 N(1 ≤ N ≤ 15,000) 개의 재료와 M이 주어졌을 때 몇 개의 갑옷을 만들 수 있는지를 구하는 프로그램을 작성하시오.

시간제한
- 2초

출력
- 첫째 줄에 갑옷을 만들 수 있는 개수를 출력한다.

예제
```
- 입력 -
6
9
2 7 4 1 5 3

- 출력 -
2
```

풀이
- 시간 복잡도를 고려해야 한다. N의 최대 범위가 15,000이므로 O(nlogn) 시간 복잡도 알고리즘을 사용해도 괜찮다.
- N의 최대 범위가 15,000이므로 O(nlogn) 시간 복잡도 알고리즘을 사용해도 괜찮다. 즉, 정렬을 사용해도 된다.
```java
import java.io.BufferedReader;  
import java.io.IOException;  
import java.io.InputStreamReader;  
import java.util.Arrays;  
import java.util.StringTokenizer;  
  
public class baekjoon_1940 {  
    public static void main(String[] args) throws IOException {  
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));  
        StringTokenizer st = new StringTokenizer(br.readLine());  
  
        int N = Integer.parseInt(st.nextToken());  
        st = new StringTokenizer(br.readLine());  
        int M = Integer.parseInt(st.nextToken());  
  
        int[] c = new int[N];  
        st = new StringTokenizer(br.readLine());  
        for (int i = 0; i < N; i++) {  
            c[i] = Integer.parseInt(st.nextToken());  
        }  
  
        Arrays.sort(c);  
        int count = 0;  
        int start = 0;  
        int end = N - 1;  
  
        while (start < end) {  
            if (c[start] + c[end] == M) {  
                count++;  
                start++;  
                end--;  
            } else if (c[start] + c[end] < M) {  
                start++;  
            } else {  
                end--;  
            }  
        }  
  
        System.out.println(count);  
    }  
}
```



슬라이딩 윈도우
- 2개의 포인터로 범위를 지정한 다음 범위(window)를 유지한 채로 이동(sliding)하며 문제를 해결
- 투 포인터 알고리즘과 매우 비슷

예시
- 백준 12891번
![[baekjoon_12891.png]]
- 예제 입력
```
9 8
CCTGGATTG
2 0 1 1
```

- 예제 출력
```
0
```


결과 코드
```java


```


출처:
연결문서

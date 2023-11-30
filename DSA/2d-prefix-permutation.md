# 2차원 구간합 배열

## 정의

2차원행렬에서 구간합배열을 이용하여 구간합을 구하는 알고리즘이다.
1차원과 마찬가지로 구간합을 구할 때의 시간복잡도를 낮춘다.

## 공식

~~~text
1. D[i][1], D[1][j]를 우선 구하기
2. D[i][j] = D[i-1][j] + D[i][j-1] + A[i][j] 를 이용해 원소 계산하기
~~~

구간합배열의 원소는 다른 원소와 본래 배열의 원소와 위의 관계를 가진다.

## 구현
### 전체 알고리즘
~~~java
import java.io.*;
import java.util.StringTokenizer;

public class Main {
    public static void main(String[] args) throws IOException {
        // 입력값 받기
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());
        int N = Integer.parseInt(st.nextToken()); // 행렬크기

        int[][] A = new int[N + 1][N + 1]; // 1부터 인덱스 시작 설정위함
        for (int i = 1; i <= N; i++) {
            st = new StringTokenizer(br.readLine());
            for (int j = 1; j <= N; j++) {
                A[i][j] = Integer.parseInt(st.nextToken());
            }
        }

        // 구간합배열 구하기
        int[][] S = new int[N + 1][N + 1];

        for (int i = 1; i <= N; i++) {
            for (int j = 1; j <= N; j++) {
                S[i][j] = S[i - 1][j] + S[i][j - 1] - S[i - 1][j - 1] + A[i][j];
            }
        }

        // 특정 구간의 합 구하기
        // 입력값을 받을 때 순서 주의하기!
        st = new StringTokenizer(br.readLine());
        int x1 = Integer.parseInt(st.nextToken());
        int y1 = Integer.parseInt(st.nextToken());
        int x2 = Integer.parseInt(st.nextToken());
        int y2 = Integer.parseInt(st.nextToken());
        int answer = S[x2][y2] - S[x1 - 1][y2] - S[x2][y1 - 1] + S[x1 - 1][y1 - 1];
        
    }
}
~~~

1. 2차원 구간합 배열 생성하기
~~~java
        int[][] S = new int[N + 1][N + 1];

        for (int i = 1; i <= N; i++) {
            for (int j = 1; j <= N; j++) {
                S[i][j] = S[i - 1][j] + S[i][j - 1] - S[i - 1][j - 1] + A[i][j];
            }
        }
~~~

2. 구간합 구하기
~~~

~~~
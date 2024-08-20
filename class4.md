## LIS
```
내용: 배열의 최장 증가 부분수열을 구함
시복: O(NlogN)
메모리: N
방법: 원래 배열 순차탐색 -> LIS 배열에서 현재 원소의 위치 이분탐색 후 삽입
```
## LCS
```
- 길이 구하기
내용: 두 배열의 최장 공통 부분배열의 길이를 구함
시복: O(N^2)
메모리: N
방법: A[i] == B[j] ? dp[i][j] = dp[i-1][j-1] + 1 : dp[i][j] = max( dp[i-1][j], dp[i][j-1] )
	*dp맵은 두줄만 필요하므로 N^2의 메모리를 사용할 필요 없음
	*비트셋 이용으로 시간복잡도를 1/(문자 개수)로 줄일 수 있음

- 배열 구하기
내용: 두 배열의 최장 공통 부분배열을 구함
시복: O(N^2)
메모리: N^2
	*히르쉬버그로 N에 해결 가능
	->분할정복
방법: dp 맵 백트래킹
```

## 다익스트라
```
내용: 최단거리 구하기
	*간선 추가시 경로 비용 단조증가
시복: O(VlogE)
방법: pq에서 최소 간선 pop -> 파생 간선 탐색 -> dist[e] = min(dist[e], dist[s] + d)
```

## 밸만포드
```
내용: 최단거리
시복: O(VE)
방법: 모든 간선 갱신 -> V-1번 ->한번 더 해서 갱신되면 사이클 존재
```

## 플로이드 와샬
```
내용: 모든점에서 모든 점 최단거리
시복: O(V^3)
방법: 브루트포스
```

## 배낭문제
```
내용: N종류의 물건(무게/가치/개수(K)) -> 총 무게 M이하 최대 가치 구하기
시복: O(NMK)
	*K를 이진분할해서 NMlogK로 처리 가능
방법: 총 무게 인덱스로 dp
```
# LIS

- LIS(longest increasing subsequence) 가장 긴 부분 증가수열(의 길이 또는 수열)을 구하는 알고리즘
- LIS 길이 구하기 $O(NlogN)$
- LIS 배열 구하기

## LIS 길이 구하기

- 증가하는 수열 형태의 dp배열을 이용
1. 원본 배열 순차탐색
2. dp배열에서 탐색중인 원소보다 크거나 같은 가장 작은 원소 찾기 (dp가 증가수열이므로 이분탐색 $logN$)
3. 해당 위치에 원소 삽입
4. 크거나 같은 원소가 없다면 dp의 뒤에 삽입
5. dp의 크기가 LIS 길이임

```cpp
#include <bits/stdc++.h>
using namespace std;

int n;
vector<int> v,lis;

void init(){
	cin>>n;
	v.resize(n);
	for(int &x: v){
		cin>>x;	
	} 
}

int f(){
	for(int x: v){
		int ind = lower_bound(lis.begin(),lis.end(),x)-lis.begin();
		if(ind == lis.size()){
			lis.push_back(x);
		}
		else{
			lis[ind] = x;
		}
	}
	
	return lis.size();
}

int main(){
	init();
	cout<<f();
}
```

## LIS 배열 구하기

- LIS tree를 이용

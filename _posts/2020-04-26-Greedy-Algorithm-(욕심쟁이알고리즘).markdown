---
layout: single
title:  "Greedy Algorithm (욕심쟁이알고리즘)"
date:   2020-04-26 21:19:40 +0900
categories: jekyll update
---

### 탐욕알고리즘 (욕심쟁이 알고리즘)

#### 그리디 알고리즘은 현재 상태에서 가장 최선의 선택(근시안적인 선택)을 하는 알고리즘 기법입니다.

##### 그리디 알고리즘의 특성
	1. 한 번 선택한 부분해는 번복하지 않는다.
	2. 제한적인 문제만 가능하다
	3. 문제의 최적해 속에 부분 문제의 최적해가 포함 - **최적 부분 구조/최적성 원칙**

#### *문제점! 항상 최적화 된 결과값만 제공하지는 않아요*



### 그리디 알고리즘의 대표적인 예시

1. **동전 거스름돈(Coin Change)**
	- 가장 큰 금액을 나타내는 동전부터 선택하여 거스름돈의 최소 동전 수를 찾아낸다.
	- 관련 프로젝트는 이전 포스팅 팀프로젝트1에서 GUI를 사용한 자판기 예시로 볼 수 있다.
	
2. **최소신장트리(Minimum Spanning Tree)**
   - 가중치 그래프에서 모든점을 연결시킨 선분들의 가중치 합이 최소인 트리
   - 1개의 연결컴포넌트로 된 가중치 그래프를 입력
     - Kruskal 알고리즘
         - 선분이 1개씩 T에 추가되는 것을 반복하여 1개인 트리 T를 생성
         - n개의 트리가 합쳐져 1개의 Spanning Tree 생성
         - 시간복잡도 : $$ O(nlogn) $$ 
           n : 입력 그래프에 있는 선분의 수
     - Prim 알고리즘 (그래프)
         - 최소의 가중치로 만들어진 트리에 연결되는 선분을 트리에 추가시킨다.
         - 시간복잡도 : $$(n-1) O(n) = O(n^2)$$
           n = 그래프의 노드 개수



3. **최단 경로 찾기(Dijkstra)**
   - 출발점으로부터 최단거리가 확정되지 않은 점들 중 가장 가까운 점 추가
     - 시간복잡도 : $$ O(n^2)$$

4. **부분배낭문제 (Fractional Knapsack)**
   - 단위 무게당 가장 값나가는 물건을 계속해서 배당에 담는다. 
     - 마지막엔 넣을 수 있을 만큼만 투입

     - 시간복잡도 : $$ O(nlogn)$$

5. **집합 커버 문제 (Set Cover)**
   - N개의 원소로 이로어진 집합 U
   - U의 집합으로 구성된 F
     F의 부분잡합으로 U 구성하기
   - 시간복잡도 : $$ O(n^3)$$
6. **작업 스케줄링(Job Scheduling)**
   - 빠른 시작시간 작업 먼저 배정
     - 시간복잡도 : $$ O(nlogn) + O(mn)$$
       n : 작업 수 , m : 기계 수 

7. **허프만 코딩(Huffman)**
   - Heap 정렬과 우선순위 Queue 를 이용한다.
     - 시간복잡도 : $$ O(nlogn)$$



-------------------------------------------

### 그리디 알고리즘 문제 예시

---------------

#### 출처 : 백준 [2352번 문제](https://www.acmicpc.net/problem/2352)

[![noInputGUI](https://github.com/GowoonJ/GowoonJ.github.io/blob/master/assets/image/baekjoon_2352_problem.jpg)](https://github.com/GowoonJ/GowoonJ.github.io/blob/master/assets/image/baekjoon_2352_problem.jpg)


> 입력
>
> > 첫째 줄에 정수 n(1<= n <= 40,000) 입력
> > 1번 포트와 연결되어야 하는 포트번호 ... n번 포트와 연결되어야하는 포트번호

> 출력
>
> > 최대 연결 개수를 출력

#### **선정이유** 
- 백준에서 그리디 알고리즘을 이용하는 문제로 분류되어있으나, LIS(최장 증가수열)알고리즘을 이용하여 해결 가능하기 때문
	- LIS Algorithm
		- 부분적으로 증가하는 수열 중 가장 긴 것을 찾아내는 알고리즘
			- 왼쪽에서 오른쪽으로 이어졌을 때, 꼬이지 않고 가장 길게 연결된 것을 찾아내야한다.
			- 시간복잡도 : $$O(n^2)$$
		
	- 또한 LIS Algorithm 은 DP(동적계획알고리즘)을 이용하여 접근 가능하다.

- LIS 알고리즘을 이용하여 풀었기 때문에 시간복잡도는 O(n^2)가 되어야한다고 생각하겠지만, O(nlog(n))으로 한 번 더 줄일 수 있다. 

#### 풀이 코드 - C++
~~~~
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;
typedef pair<int, int> pii;
vector<int> v;
vector<int>::iterator iter;
int main(void)
{
	ios_base::sync_with_stdio(0);
	cin.tie(0);
	cout.tie(0);

	int n;
	cin >> n;
	for (int i = 1; i <= n; i++)
	{
		int a;
		cin >> a;
		iter = lower_bound(v.begin(), v.end(), a);
		if (iter == v.end())
		{
			v.push_back(a);
		}
		else
		{
			*iter = a;
		}
	}
	cout << v.size();
	return 0;
}
~~~~

**thx to [ryuspace](https://github.com/ryuspace)**

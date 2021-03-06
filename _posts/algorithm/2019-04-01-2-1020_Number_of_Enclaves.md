---
title:  1020. Number of Enclaves
categories:
 - Algorithm
tags: [Algorithm, 프로그래밍, 자바, java, dfs, medium]
---
[1020. Number of Enclaves](https://leetcode.com/problems/number-of-enclaves/)
Acceptance 53.5%

### NOTE
블로그라기 보다는 생각나는 생각나는 대로 두서없이 적는 낙서장이라고 보면 될것 같다.

## 2019년 4월 1일 20:53~21:30
### 문제
1. 배열이 주어지고
2. 0은 바다, 1은 육지
3. 육지에서 사방으로 움직일 수 있음
4. 이때 배열의 경계에 갈 수 없는 고립 된 1의 개수 리턴

### 생각 흐름 - 무식하게 풀기
1. DFS네...
2. 그냥 [0,0]부터 [m-1,n-1]까지 돌면서 1을 만날 때마다 경계에 갈 수 있는지 판별하면 됨
3. 시간 복잡도는 경계는 움직일 필요없고, 나머지 는 4방향으로 움직이는 거니깐, $4^{(m-2)(n-2)}$? 뺑뻉이 돌다 결국 못나가는 상황이 최악.
4. 육지가 이어져있다면, 어차피 지나가니깐 한군데만 나갈 수 있다는 것을 알면 지나갔던 길은 다 판별 가능 - Lazy Initialization 하면 계산량 줄이는 것이 가능

## 2019년 4월 2일 13:20~14:15
{% gist karlbishnu/8c3604c30e62e44b7adf8cc4c546230f %}

1. 무식하게 짜봤는데.... 당연히 타임아웃 남
2. 어제 4.에서 Lazy Initialization이 가능할 것이라 했는데... 어렵다;; 왜냐하면, 육지가 여러 갈레로 갈라졌을 때, 한 가지의 결과가 다른 가지로 전파되는 것에는 방문 순서에 따라 달라지기 때문이다.
3. 생각을 달리 하기로 했다.
4. 배열의 경계에 있는 1부터 타고 들어가면서 육지를 끊어버리면 나중에는 고립된 육지만 남을 것이다.
5. 다시 한 번 순회해서 1의 개수만 세면 끝

{% gist karlbishnu/fbe12670dd85e582863d1ac2f173975a %}

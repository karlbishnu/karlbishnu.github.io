---
title:  Joined Longest Increasing Subsequence
categories:
 - Algorithm
tags: [Algorithm, 프로그래밍, 자바, java, array, dp, dynamic programming, Algorithm 풀이 해결 전략, 구종만]
---

### NOTE
블로그라기 보다는 생각나는 생각나는 대로 두서없이 적는 낙서장이라고 보면 될것 같다.

## 2019년 4월 9일 14:20~15:30
### 문제
1. [LIS]({% post_url algorithm/2019-04-08-1_300_Longest_Increasing_Subsequence %}) 후속 문제


### 생각 흐름 - 무식하게 풀기
1. Leet Code에 비슷한 문제가 있음 좋겠는데 없는 듯....

```
Input: A=[1,2,4], B=[3,4,7]
Output: 5 //[1,2,3,4,7]

Input: A=[1,2,3], B=[4,5,6]
Output: 6 //[1,2,3,4,5,6]

Input: A=[10,20,30,1,2], B=[10,20,30]
Output: 5 //[1,2,10,20,30]  

Input: A=[4], B=[4]
Output: 1 //[4]
```

2. 걍 무식하게 A와 B의 특정 원소의 max값을 저장하고, 각각의 배열의 값이 max값보다 클 때, 해당 인덱스값들 부터 재귀적으로 훑어가면서 되지 않을까?
3. 라고 생각했지만. 잘 안되네...
4. 책에서는 코드를 비슷하게 보이려고 두 배열에 같은 값이 있는 상황을 무시했는데...
{% gist karlbishnu/0bafdf2afb3bdc8b7dd54a17c1ca86d7 %}

## 2019년 4월 10일 10:15~10:40
1. 책 코드를 손으로 디버그해도,  제대로 결과값이 안나오는데;;
{% gist karlbishnu/c1caea0544b6f36b7f62ad1ea713bedc %}

```
Input: A=[1,4], B=[3,7]
Expected: 4
Output: 5
```
2. 아무래도 배열 하나씩을 각각 메모를 구하고, 다시 순회를 해봐야겠다.

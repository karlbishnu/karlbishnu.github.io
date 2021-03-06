---
title:  10. Regular Expression Matching
categories:
 - Algorithm
tags: [Algorithm, 프로그래밍, 자바, java, dp, dynamic programming, string, hard]
---
[10. Regular Expression Matching](https://leetcode.com/problems/regular-expression-matching/)
Acceptance 25.1%

### NOTE
블로그라기 보다는 생각나는 생각나는 대로 두서없이 적는 낙서장이라고 보면 될것 같다.

## 2019년 4월 1일 14:40~17:00
### 문제
1. 문제 제목은 정규표현식이지만, 실제로는 살짝 다름
2. '.'는 단일 문자
3. '\*'는 바로앞의 문자가 0자리이거나 그 이상의 연속 된 문자
4. '\*'의 역할이 일반적인 정규표현식보다 대폭 축소 됨

### 생각 흐름 - 무식하게 풀기
1. 문자를 하나씩 비교하자.
2. 패턴에서 현재의 다음이 '\*'이라면, '\*'과 그 앞의 문자를 포함해서 대상과 비교한 결과와 이를 '\*'와 그 앞 문자열을 무시하고 대상과 비교한 결과의 OR 결과를 리턴하면 된다.
3. 이때 2.의 두 조건은 substring으로 재귀적으로 호출하면 된다.
5. 재귀적의 기저 조건으로 패턴의 길이가 0이면 대상 문자열도 길이가 0이어야한다.
6. 시간복잡도는.... '\*'이 없을 때는, s가 대상문자열 길이이고 p가 패턴의 길이일 때, $O(s+p)$
7. '\*'이 하나라도 있으면, 패턴을 무시하여 호출하는 $s+p-2$ 한 번, 패턴과 S를 substring하여 비교하는 $s-1+p$ 한 번이 호출 됨. 최악은 $p/2$가 '\*'인 경우로 재귀 호출은 $p/2$ 이므로, 대략 $O((s+p)2^{2s+p-3})$. 음...맞나??

{% gist karlbishnu/8d671ce88bb47e97aec40e4b94d65592 %}

## 2019년 4월 1일 20:02~20:30
### DP
1. $s*p$ 크기의 메모에 계산했던 결과를 남기고,
2. substring 없이 배열의 인덱스만 넘겨서 될 것인가?
3. 코드 거의 안 바꾸고 패스

{% gist karlbishnu/f14cda0c2ee862e5fa50ee91895452f9 %}

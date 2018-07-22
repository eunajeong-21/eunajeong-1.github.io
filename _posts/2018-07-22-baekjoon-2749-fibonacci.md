---
layout: post
title: "[백준2749]피보나치 수와 피사노 주기, Fibonacci numbers and Pisano period"
date: 2018-07-22
excerpt: "피사노 주기를 이용하여 N번째 피보나치 수를 1,000,000으로 나눈 나머지 구하기"
tag:
- Baekjoon
- Algorithm
- Fibonacci
feature: https://png93.github.io/assets/img/title/puzzle.jpg
comments: true
---

_백준 2749번 문제를 풀면서 공부한 내용입니다. (▼클릭하면 이동▼)_

<a href = "https://www.acmicpc.net/problem/2749"><img src = "https://png93.github.io/assets/img/title/baekjoon.PNG"></a>

<br/>

## 피보나치 수
피보나치 수는 앞에 있는 두 수의 합이 현재의 수가 되는 규칙을 가지는 수이다.

| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7  | 8  | 9  | 10 |...|
|:---|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|---:|
| 0 | 1 | 1 | 2 | 3 | 5 | 8 | 13 | 21 | 34 | 55 |...|
{: rules="groups"}

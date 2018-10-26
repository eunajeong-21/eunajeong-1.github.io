---
layout: post
title: "[취준] 필기테스트 대비"
date: 2018-10-21
excerpt: "데이터베이스, 통신, 알고리즘 등"
tag:
- 취준
comments: true
---

## 데이터베이스 관련

### 정규화 (Normalization)

**정규화란?**  
__"이상현상(Anomaly)"과 "함수적 종속"에 의한 문제를 해결하기 위해 여러개의 릴레이션으로 분해하는 과정__  

[이상(Anomaly) 현상]  
- _참조 무결성, 개체 무결성_ 제약조건을 어기게 될 시 데이터의 중복과 종속으로 인해 발생하는 현상이다.
- 종류: 삭제, 삽입, 갱신 이상

  1. 삭제 이상 : 원하지 않는 자료까지 삭제가 되는 현상  
  2. 삽입 이상 : 원하지 않는 자료가 삽입되거나, 자료가 부족하여 삽입 되지 않는 현상 (개체무결성을 해친다.)  
  3. 갱신 이상 : 정확하지 않거나 일부 튜플만 갱신되는 현상

_개체 무결성: 기본키는 NULL이거나 중복값이 될 수 없다._  

[함수적 종속(Functional Dependency)]  
- 속성 A와 B에 대해, A의 값이 B값을 결정하는 경우 B는 A에 함수적으로 종속되었다고 한다.  

> 'A → B' : A = 결정자, B = 종속자  

- 종류: 완전 / 부분 / 이행적
  1. 완전 함수 종속 : '기본키'에만 종속되는 경우
  2. 부분 함수 종속 : 합성키의 일부 또는 기본키가 아닌 속성에 종속되는 경우
  3. 이행적 함수 종속 : 한다리 걸쳐서 종속되는 경우  
    A → B , B → C , A → C


[__정규화 (Normalization)__]  
- 종류: 1NF / 2NF / 3NF / BCNF / 4NF / 5NF (총 6단계)

1. 제 1 정규형 (1NF)  
테이블의 모든 도메인이 __원자값__ 만으로 구성 되도록 테이블을 분해한다.  

2. 제 2 정규형 (2NF)  
__부분함수종속을 제거__ 하기 위해 테이블을 분해한다.  

3. 제 3 정규형 (3NF)  
__이행함수종속을 제거__ 하기 위해 분해.  

4. BCNF (Boyce Codd Normal Form)  
__모든 결정자가 후보키가 되도록 분해하는 과정__  
==> 어떤 릴레이션에서 결정자가 후보키가 아닐 경우 수행한다.  

5. 제 4 정규형 (4NF)  
__다치종속 제거__  
_다치 종속 (MultiValued Dependency): 하나의 속성값이 속성의 집합을 결정하는 종속관계_  

6. 제 5 정규형 (5NF)  
__조인 종속__ 이 후보키를 통해서만 성립 되도록 한 정규형.  
_조인 종속: 원래의 릴레이션을 분해한 뒤 자연 조인한 결과가 원래의 릴레이션과 같은 결과가 나오는 종속성._  

cf) 역정규화 : 정규화를 진행하다가 테이블이 너무 많이 분해 되었을 경우, 검색을 수행하게 되면 분해된 만큼 조인 연산을 수행하므로 성능이 저하된다. 이러한 문제를 해결하기 위해 이상현상이나 종속이 일어나지 않는 부분까지 테이블을 다시 합치는 것을 '역정규화' 라고 한다.  

<br/>

#### 뷰(View)

정의: 테이블 또는 다른 뷰를 기초로 하는 논리적인 테이블.  
사용 목적:  
- 뷰를 사용하면 DB에서 선택적으로 데이터를 보여줄 수 있기 때문에 접근을 제한 할 수 있다.
- 복잡한 질의문으로 부터 결과를 검색하기 위한 단순한 질의를 만들 수 있다.  

#### 시퀀스(Sequence)

정의: 여러 사용자들이 공유하는 데이터베이스 객체. 호출 될 때마다 중복되지 않은 고유한 숫자를 리턴한다.  
_기본키 속성에 사용할 값을 발생시킬 때 사용한다._  
> 시퀀스명.NEXTVAL - 추출
> 시퀀스명.CURRVAL - 참조

~~~sql
CREATE SEQUENCE emp_seq
INCREMENT BY 1
START WITH 100
MAXVALUE 9999
NOCACHE
NOCYCLE;
~~~


#### 인덱스(Index)
정의: 테이블에서 '행 = 튜플 = 레코드'를 검색할 때 검색 속도를 높이기 위해서 Oracle 서버가 사용하는 스키마 객체.  
- 인덱스를 사용하면 디스크의 I/O를 감소시킬 수 있다.
- 해당 테이블과 논리적으로 독립적이다.
- Oracle 서버에 의해 자동으로 관리된다.
- 테이블을 삭제하면 관련 인덱스는 자동으로 삭제된다.  
~~~sql
CREATE INDEX emp_ename_idx ON emp(ename);
~~~

<br/>

## 알고리즘 / 자료구조 관련

### 시간복잡도
- Big O : 알고리즘의 최악의 경우 성능을 의미
  - 최악의 경우 = __아무리 나빠도 이정도 성능을 보장__ 한다는 뜻이기 때문에 빅오 표현법을 가장 많이 사용한다.
- Big Omega : 최선의 경우
- Big Theta : 최악과 최선의 평균  

[빅오 표기법]  

> O(증가함수)


[자주 쓰이는 증가함수]  
_증가함수: 데이터의 크기 n에 대해 알고리즘 수행시간이 증가하는 비율_  


 \\(O(1)\\) - 해시 테이블  
 \\(O(logN)\\) - __이진 탐색__  
 \\(O(N)\\)    - 순차 탐색  
 \\(O(NlogN)\\) - __퀵 정렬, 병합 정렬__  
 \\(O(N^{2})\\) - __거품 정렬, 삽입 정렬__  
 \\(O(N^{3})\\) - 행렬 곱셈  
 \\(O(2^{N})\\)  

<br/>

### 정렬 알고리즘

#### 1. 거품 정렬 (Bubble Sort)

- 데이터 집합을 순회하면서 이웃 요소끼리 비교와 교환을 수행한다.
- 한번 순회가 끝날 때마다 가장 큰 값이 마지막에 위치하게 되며, 순회 할 범위가 1씩 줄어든다.  

거품 정렬의 비교횟수 = (n-1) + (n-2) + (n-3) + ... + 1 =
\\( \frac{(n-1)n}{2} \\)  〓▶ \\(O(N^{2})\\)  

~~~java
void bubbleSort(int[] data, int len) {

  for(int i = 0; i < len - 1 ; i++) {
    for ( int j = 0; j < len - (i+1); j++){
      if(data[j] > data[j+1]){
        int temp = data[j+1];
        data[j+1] = data[j];
        data[j] = temp;
      }
    }
  }

}
~~~

<br/>

#### 퀵 정렬
1. 데이터 집합 내에서 기준 요소(Pivot) 하나를 선택한다.
2. 집합을 순회하면서 Pivot 보다 작은 값은 왼편에 큰 값은 오른편에 위치시킨다.
3. 더이상 나눌 수 없을 때 까지 왼쪽, 오른쪽으로 집합을 나누면서 1,2를 수행한다.  

~~~java
void quickSort(int[] data, int left, int right){

  if( left >= right) return;

  int pivot = (left + right) / 2;
  int first = left;
  int end = right;

  int temp = 0;

  while(left <= right) {
    while(data[left] <= data[pivot] && left < right)
      left++;

    while(data[right] > data[pivot] && left <= right)
      right--;

    if(left < right) {
      if(left == pivot) pivot = right;
      else if(right == pivot) = pivot = left;

      temp = data[left];
      data[left] = data[right];
      data[right] = temp;
    } else {
      break;
    }
  }

  temp = data[right];
  data[right] = data[pivot];
  data[pivot] = temp;

  quickSort(data, first, right-1);
  quickSort(data, right+1, end);

}
~~~

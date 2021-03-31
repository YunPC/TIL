# 정렬 알고리즘 (Sort Algorithms)

## 정렬 알고리즘이란
---

- 정렬 알고리즘의 조건
    + 정렬 알고리즘의 출력은 비 내림차순이다(중복을 허용한다!). 즉, 이전 원소는 다음 원소보다 작지 않다
    + 정렬 알고리즘의 출력은 입력을 재배열하여 만든 순열이다.
    
- 알고리즘의 핵심 개념 설명에 용이
    + 점근 표기법
    + 분할 정복 알고리즘 (Divide & Conquer)
    + 최악의 경우, 최선의 경우, 평균적인 경우

## 정렬 알고리즘의 종류
---

- In-place 알고리즘: 정렬을 수행하는 데에 추가 메모리가 O(logN) 이하로 사용되는 알고리즘
- Stable 알고리즘: 동일 값의 정렬 전후에 순서가 유지되는 알고리즘
    + Stable한 알고리즘이어야 여러 키 값을 기준으로 정렬할 수 있다!

## 기본 정렬 알고리즘
---

### 버블 정렬 (Bubble Sort)
- 알고리즘
    + 인접한 두 원소를 검사하여 정렬한다.
    + 마지막 원소를 제외하고 위 동작을 반복한다
- 공간 복잡도: O(1)
- 시간 복잡도
    + 최악의 경우: O(n^2)
    + 최선의 경우: O(n)
    + 평균적인 경우: O(n^2)
    
```python
def bubble_sort(x):
    length = len(x)-1
    for i in range(length):
        swapped = False
        for j in range(length-i):
            if x[j] > x [j+1]:
                swapped = True
                x[j], x[j+1] = x[j+1], x[j]
        if swapped is False:
            break
    return x
```

### 삽입 정렬 (Insertion Sort)

- 알고리즘
    + 앞 부분의 이미 정렬된 영역과, 아직 정렬되지 않은 영역으로 나눈다.
    + 정렬되지 않은 영역의 값을 정렬된 영역의 적절한 위치에 하나씩 삽입한다.
- 공간 복잡도:O(1)
- 시간 복잡도
    + 최악의 경우 : O(n^2)
    + 최선의 경우 : O(n)
    + 평균적인 경우: O(n^2)
    
```python
def insert_sort(x):
    for i in range(1, len(x)):
        j = i - 1
        key = x[i]
        while x[j] > key and and j >= 0:
            x[j+1] = x[j]
            j = j -1
        x[j+1] = key
    return x
```

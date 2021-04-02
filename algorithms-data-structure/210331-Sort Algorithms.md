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

### 선택 정렬(Selection Sort)

- 알고리즘 
    + 주어진 리스트 중 최소 값을 찾아, 맨 앞의 값과 교체한다.
    + 맨 처음 위치를 제외하고 위 동작을 반복한다.
- 공간복잡도: O(1)
- 시간 복잡도
    + 최악의 경우 O(n^2)
    + 최선의 경우 O(n^2)
    + 평균적인 경우 O(n^2)
    
```python
def selection_sort(x):
    length = len(x)
    for i in range(length-1):
        index_min = i
        for j in range(i+1, length):
            if x[index_min] > x[j]:
                index_min = j
        x[i], x[index_min] = x[index_min], x[i]
    return x
```

## 심화 정렬 알고리즘

---

### 합병 정렬 (Merge Sort)

- 알고리즘
    + 정렬되지 않은 리스트는 두 부분 리스트로 나눈다.
        - 길이가 1인 부분 리스트는 정렬된 부분 리스트로 본다.
    + 두 부분 리스트를 합병하여 정렬된 임시 배열에 저장한다
    + 임시 배열에 저장된 결과를 원래 배열로 복사한다.

- 공간 복잡도: O(n)
- 시간 복잡도
    + 최악의 경우: O(nlogn)
    + 최선의 경우: O(nlogn)
    + 평균적인 경우 : O(nlogn)
    
### 퀵 정렬 (Quick Sort)

- 알고리즘
    + 리스트에서 하나의 pivot을 선택한다.
    + pivot을 기준으로 좌측에서 더 큰 값을, 우측에 더 큰 값을 배치한다.
    + pivot의 좌측과 우측에 대해서 재귀적으로 반복한다.
- 공간복잡도 : O(logn)
- 시간복잡도
    + 최악의 경우 : O(n^2)
    + 최선의 경우: O(nlogn)
    + 평균적인 경우: O(nlogn)
    
    
## 하이브리드 정렬 알고리즘

--- 

팀소트 (Timsort)

- Java SE 7, Android, GNU Octave, Chrome V8, Swift, Rust, Python 등에 적용된 정렬 알고리즘
- Insertion Sort와 Merge Sort를 결합하여 만든 알고리즘
    + 작은 영역에 대해서 Insertion Sort를 수행하고, 이것을 Merge Sort하여 최적화
- 공간복잡도: O(n)
- 시간복잡도
    + 최악의 경우 : O(nlogn)
    + 최선의 경우 : O(n)
    + 평균적인 경우: O(nlogn)

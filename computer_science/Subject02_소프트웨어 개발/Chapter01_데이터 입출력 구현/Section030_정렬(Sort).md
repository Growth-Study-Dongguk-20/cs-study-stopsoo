## CS Study - Section030 정렬(Sort)
### ✏️ Study
#### 💡 삽입 정렬(Insertion Sort)
- 가장 간단한 정렬 방식.
- 이미 순서화된 파일에 새로운 하나의 레코드를 순서에 맞게 삽입시켜 정렬.
- 과정
  - 1️⃣ 두 번째 키와 첫 번째 키를 비교해 순서대로 나열.
  - 2️⃣ 세 번째 키를 첫 번째, 두 번째 키와 비교해 순서대로 나열.
  - 3️⃣ 계속해서 n번째 키를 앞의 (n-1)개의 키와 비교하여 알맞은 순서에 삽입하여 정렬.
- 시간 복잡도
  - `평균` : $O(n^2)$
  - `최악` : $O(n^2)$
<br>

#### 💡 쉘 정렬(Shell Sort)
- 삽입 정렬을 확장한 개념.
- 입력 파일을 어떤 `매개변수(h)`의 값으로 서브 파일을 구성, 각 서브 파일을 삽입 정렬 방식으로 배열하는 과정을 반복하는 정렬 방식.
- 보통 $h = n^{1/3}$
- 입력 파일이 부분적으로 정렬되어 있는 경우에 유리한 방식.
- 시간 복잡도
  - `평균` : $O(n^{1.5})$
  - `최악` : $O(n^2)$
<br>

#### 💡 선택 정렬(Selection Sort)
- n개의 레코드 중에서 `최소값`을 찾아 첫 번째 위치에 놓고, 나머지 (n-1)개 중에서 다시 `최소값`을 찾아 두 번째 레코드 위치에 놓는 방식을 반복하며 정렬하는 방식.
- 시간 복잡도
  - `평균` : $O(n^2)$
  - `최악` : $O(n^2)$
<br>

#### 💡 버블 정렬(Bubble Sort)
- **인접한 두 개의 레코드 키 값을 비교**하여 그 크기에 따라 레코드 위치를 서로 교환하는 정렬 방식.
- 계속 정렬 여부를 플래그 비트(f)로 결정.
- 시간 복잡도
  - `평균` : $O(n^2)$
  - `최악` : $O(n^2)$
<br>

#### 💡 퀵 정렬(Quick Sort)
- 하나의 파일을 부분적으로 나누어 가면서 정렬하는 방법.
- 키를 기준으로 작은 값은 왼쪽에, 큰 값은 오른쪽 서브파일로 분해시키는 방식으로 정렬.
- 위치에 관계 없이 임의의 키를 분할 원소로 사용 가능.
- **정렬 방식 중에서 가장 빠른 방식.**
- `스택(Stack)` 사용.
- `분할(Divide)`과 `정복(Conquer)`을 통해 자료를 정렬.
  - 분할(Divide) : 기준값인 피봇(Pivot)을 중심으로 정렬할 자료들을 2개의 부분집합으로 나눔.
  - 정복(Conquer) : 부분집합의 크기가 더 이상 나누어질 수 없을 때까지 분할과 정복을 반복 수행.
- 시간 복잡도
  - `평균` : $O(nlogn)$
  - `최악` : $O(n^2)$
<br>

#### 💡 힙 정렬(Heap Sort)
- `전이진 트리(Complete Binary Tree)`를 이용한 정렬 방식.
- 구성된 전이진 트리를 Heap Tree로 변환하여 정렬.
- 과정
  - 1️⃣ 주어진 파일의 레코드들을 전이진 트리로 구성.
  - 2️⃣ 전이진 트리의 노드의 역순으로 자식 노드와 부모 노드를 비교하여 큰 값을 위로 올림.
  - 3️⃣ 교환된 노드들을 재검토하여 위의 과정을 반복.
- 시간 복잡도
  - `평균` : $O(nlogn)$
  - `최악` : $O(nlogn)$
<br>

#### 💡 2-Way 합병 정렬(Merge Sort)
- 이미 정렬되어 있는 두 개의 파일을 한 개의 파일로 합병하는 정렬 방식.
- 과정
  - 1️⃣ 두 개의 키들을 한 쌍으로 하고, 각 쌍에 대해 정렬.
  - 2️⃣ 순서대로 정렬된 각 쌍의 키들을 합병하여 하나의 정렬된 서브리스트로 만듬.
  - 3️⃣ 정렬된 서브리스트들을 하나의 정렬된 파일이 될 때까지 반복.
- 시간 복잡도
  - `평균` : $O(nlogn)$
  - `최악` : $O(nlogn)$
<br>

#### 💡 기수 정렬(Radix Sort) = Bucket Sort
- `큐(Queue)`를 이용하여 자릿수(Digit)별로 정렬하는 방식.
- 레코드의 키 값을 분석하여 같은 수 또는 같은 문자끼리 그 순서에 맞는 버킷에 분배하였다가 버킷의 순서대로 레코드를 꺼내어 정렬.
- 시간 복잡도
  - `평균` : $O(dn)$
  - `최악` : $O(dn)$

# List

## Static Array(정적 배열)
- 크기가 정해진 배열로써, 메모리를 연속적으로 할당해서 데이터를 저장한다.

- 메모리를 연속적으로 할당하기 때문에, 각 데이터 접근시 랜덤 액세스가 가능해서 접근할 때의 시간복잡도는 O(1)이다.

- 그러나 크기가 고정되어 있어 배열이 가득 찼을때 데이터를 추가할 경우 스택 오버플로우가 발생할 위험이 있다.

## Dinamic Array(동적 배열)
- 정적 배열은 선언 이후에 size를 변경할 수 없지만, 동적 배열은 size를 늘릴 수 있다.
 
- 현재 할당된 크기가 다 차면, 더블링이라는 방법을 이용해 사이즈를 키운다.
 
- 더블링은 기존 배열의 크기의 2배만큼 큰 배열을 새로 생성해 데이터를 새로운 배열에 옮긴다.
 
- 그렇기 때문에 기존의 데이터를 삽입할 때에는 시간복잡도가 O(1), 리사이징이 필요할 때의 삽입 과정만 O(n)이다.(데이터를 옮겨야 하기때문)

## 파이썬에서의 Array

- 파이썬의 리스트는 기본적으로 동적 배열의 구조를 하고 있다.

|동작|시간복잡도|
|-|-|
|access / update|O(1)|
|insert_back| amotized O(1)|
|delete_back| O(1)|
|insert_at| O(n)|
|delete_at| O(n)|

## 활용


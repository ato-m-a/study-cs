# 퀵 정렬

퀵 정렬은 빠른 정렬 속도를 자랑하는 <U>분할 정복 알고리즘</U> 중 하나로, 평균적으로 O(nlogn)이며, Worst Case는 O(n^2)의 시간복잡도를 가집니다.

기준점(pivot)을 정해서 기준점보다 작은 데이터는 왼쪽(left), 큰 데이터는 오른쪽(right)으로 모으는 함수를 작성합니다.

각 왼쪽(left), 오른쪽(right)은 재귀용법을 사용해서 다시 동일 함수를 호출하여 위 작업을 반복합니다.

함수는 왼쪽(left) + 기준점(pivot) + 오른쪽(right) 을 반환합니다.

<br>

## 구현 예제

```javascript
const quickSort = arr => {
  if (arr.length <= 1) return arr;

  const pivot = arr.at(0);
  const left = [];
  const right = [];

  for (let i = 1; i < arr.length; i++) {
    if (arr.at(i) < pivot) left.push(arr.at(i));
    else right.push(arr.at(i));
  }

  return quickSort(left).concat(pivot, quickSort(right));
}
```
오름차순으로 정렬.
1. pivot item을 정함. 어떤 원소도 가능.
2. pivot item 보다 작은 원소들은 pivot item 앞으로.
3. pivot item 보다 큰 원소들은 pivot item 뒤로.
4. pivot item 앞뒤 원소들을 sorting.

```javascript
let arr = [15, 22, 13, 27, 12, 10, 20, 25];

function partition (low, high, pivotPoint) {
    let i, j;
    let pivotItem = arr[low];
    j = low;

    for (i = low+1; i <= high; i++) {
        if (arr[i] < pivotItem) {
            j++;
            [arr[i], arr[j]] = [arr[j], arr[i]];
        }
    }

    pivotPoint = j;
    [arr[low], arr[pivotPoint]] = [arr[pivotPoint], arr[low]];
}

function quicksort (low, high) {
    let pivotPoint=low;

    if (high > low) {
        partition(low, high, pivotPoint);
        quicksort(low, pivotPoint-1);
        quicksort(pivotPoint+1, high);
    }
}
```
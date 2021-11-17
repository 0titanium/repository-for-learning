조건: 배열이 오름차순으로 정렬되어 있을 것.
x: 찾는 수.
<br />
x가 배열 중간 원소(middle)이면 종료.
<br />
1. 배열을 [0, ..., middel-1], [middle+1, ..., arr.length-1]로 나눔.
   x가 middle보다 작으면 왼쪽 배열을 선택, x가 middle보다 크면 오른쪽 배열을 선택.
2. x가 나눈 배열의 middle이면 종료. 아니면 나눈 배열로 1을 실행.
<br />
-recursive

```javascript
let arr = [10, 12, 13, 14, 18, 20, 25, 27, 30, 35, 40, 45, 47];
let x = 18;
let low = 0, high = arr.length-1;

function locationx (low, high) {
    let mid;

    if (low > high) {
        return 0;
    } else {
        mid = Math.floor((low + high) / 2);

        if (x === arr[mid]) {
            return mid;
        } else if (x < arr[mid]) {
            return locationx(low, mid-1);
        } else {
            return locationx(mid+1, high);
        }
    }
}

console.log(locationx(low, high)); // 4
```
<br />

-iterative

```javascript
let arr = [10, 12, 13, 14, 18, 20, 25, 27, 30, 35, 40, 45, 47];
let x = 18;
let len = arr.length-1;
let locationz = 0;

function binsearch (len, arr, x) {
    let low = 0, mid, high = len;

    while (low <= high && locationz === 0) {
        mid = Math.floor((low+high)/2);

        if (x === arr[mid]) {
            locationz = mid;
        } else if (x < arr[mid]) {
            high = mid-1;
        } else {
            low = mid+1;
        }
    }
}
binsearch(len, arr, x);
console.log(locationz); // 4
```
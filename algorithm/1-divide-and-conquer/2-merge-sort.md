오름차순으로 정렬.
1. 배열을 둘로 나눔.
2. 나뉜 배열들을 두 수가 남을 때가지 나눔.
3. sorting.
4. 나눈 배열들을 합침.

<br />

```javascript
let arr = [27, 10, 12, 20, 25, 13, 15, 22];
let n = arr.length;

function merge(h, m, u, v, arr) {
  let i = 1,
    j = 1,
    k = 1;

  while (i <= h && j <= m) {
    if (u[i - 1] < v[j - 1]) {
      arr[k - 1] = u[i - 1];
      i++;
    } else {
      arr[k - 1] = v[j - 1];
      j++;
    }
    k++;
  }

  if (i > h) {
    let copied = v.slice(j - 1, m);
    arr.splice(k - 1, copied.length, ...copied);
  } else {
    let copied = u.slice(i - 1, h);
    arr.splice(k - 1, copied.length, ...copied);
  }
  console.log(arr);
}

function mergesort(n, arr) {
  if (n > 1) {
    let h = Math.floor(n / 2);
    let m = n - h;
    let u = arr.slice(0, h);
    let v = arr.slice(m, n); 
    mergesort(h, u); 
    mergesort(m, v); 
    merge(h, m, u, v, arr);
  }
}

console.log(arr); // [10, 12, 13, 15, 20, 22, 25, 27]
```
<br />

mergesort(8, [27, 10, 12, 20, 25, 13, 15, 22]);
<br />
    -mergesort(4, [27, 10, 12, 20]);
    <br />
        -mergesort(2, [27, 10]);
        <br />
            -mergesort(1, [27]);
            <br />
            -mergesort(1, [10]);
            <br />
            -merge(1, 1, [27], [10], [27, 10]);
            <br />
        -mergesort(2, [12, 20]);
        <br />
            -mergesort(1, [12]);
            <br />
            -mergesort(1, [20]);
            <br />
            -merge(1, 1, [12], [20], [12, 20]);
            <br />
        -merge(2, 2, [10, 27], [12, 20], [10, 27, 12, 20]);
        <br />  
    -mergesort(4, [25, 13, 15, 22]);
    <br />
        -mergesort(2, [25, 13]);
        <br />
            -mergesort(1, [25]);
            <br />
            -mergesort(1, [13]);
            <br />
            -merge(1, 1, [25], [13], [25, 13]);
            <br />
        -mergesort(2, [15, 22]);
        <br />
            -mergesort(1, [15]);
            <br />
            -mergesort(1, [22]);
            <br />
            -merge(1, 1, [15], [22], [15, 22]);
            <br />
        -merge(2, 2, [13, 25], [15, 22], [13, 25, 15, 22]);
        <br />
    -merge(4, 4, [10, 12, 20, 27], [13, 15, 22, 25], [10, 12, 20, 27, 13, 15, 22, 25]);

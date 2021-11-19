n! / k!\*(n-k)!

```javascript
function bin2(n, k) {
  let arr = Array(n + 1)
    .fill()
    .map(() => Array(k + 1).fill(0));

  for (let i = 0; i <= n; i++) {
    for (let j = 0; j <= Math.min(i, k); j++) {
      if (j === 0 || j === i) {
        arr[i][j] = 1;
      } else {
        arr[i][j] = arr[i - 1][j - 1] + arr[i - 1][j];
      }
    }
  }
  return arr[n][k];
}

bin2(4, 2);
```

0 0 0   
<br />
0 0 0
<br />
0 0 0
<br />
0 0 0
<br />
0 0 0

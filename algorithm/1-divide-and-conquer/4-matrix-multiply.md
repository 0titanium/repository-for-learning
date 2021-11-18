행렬곱셈.

```javascript
let mat1 = [[1, 2], [3, 4]];
let mat2 = [[5, 6], [7, 8]];
let n = mat1.length;
let c = Array(n).fill().map(() => Array(n).fill(0));

function matrixMulti (n, mat1, mat2) {
    for (let i = 0; i < n; i++) {
        for (let j = 0; j < n; j++) {
            for (let k = 0; k < n; k++) {
                c[i][j] = c[i][j] + (mat1[i][k]*mat2[k][j]);
            }
        }
    }
}
matrixMulti(n, mat1, mat2);
console.log(c);
```
  0 1 0 1
  <br />
0 1 2 5 6
<br />
1 3 4 7 8

0 0 0
<br />
c[0][0] = c[0][0] + (mat1[0][0]*mat2[0][0]) = 0 + 1*5 = 5
<br />
0 0 1
<br />
c[0][0] = c[0][0] + (mat1[0][1]*mat2[1][0]) = 5 + 2*7 = 5 + 14 = 19
<br />
0 1 0
<br />
c[0][1] = c[0][1] + (mat1[0][0]*mat2[0][1]) = 0 + 1*6 = 6
<br />
0 1 1
<br />
c[0][1] = c[0][1] + (mat1[0][1]*mat2[1][1]) = 6 + 2*8 = 6 + 16 = 22
<br />
1 0 0
<br />
c[1][0] = c[1][0] + (mat1[1][0]*mat2[0][0]) = 0 + 3*5 = 15
<br />
1 0 1
<br />
c[1][0] = c[1][0] + (mat1[1][1]*mat2[1][0]) = 15 + 4*7 = 15 + 28 = 43
<br />
1 1 0
<br />
c[1][1] = c[1][1] + (mat1[1][0]*mat2[0][1]) = 0 + 3*6 = 18
<br />
1 1 1
<br />
c[1][1] = c[1][1] + (mat1[1][1]*mat2[1][1]) = 18 + 4*8 = 18 + 32 = 50
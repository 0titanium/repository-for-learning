Array 배열

특정 수의 원소들이 연속적인 형태로 구성된 구조.

배열의 각 원소들은 인덱스를 통해 접근할 수 있다.
```javascript
let arr = [1, 2, 3];
consolge.log(arr[0]); // 1 출력
```

배열 맨 끝에 원소 추가하기
```javascript
let arr = [1, 2, 3];
arr.push(4); // arr [1, 2, 3, 4]
```

배열 맨 끝 원소 제거하기
```javascript
let arr = [1, 2, 3];
arr.pop(); // arr [1, 2]
```

배열 맨 앞에 원소 추가하기
```javascript
let arr = [1, 2, 3];
arr.unshift(0); // arr [0, 1, 2, 3]
```

배열 맨 앞 원소 제거하기
```javascript
let arr = [1, 2, 3];
arr.shift(); // arr [2, 3]
```

배열 중간 원소 하나 추가하기
```javascript
let arr = [1, 2, 4];
arr.splice(2, 0, 3) // arr [1, 2, 3, 4], Array.splice(index, deleteCount, item0, item1, ..., itemN);
```

배열 중간 원소 하나 제거하기
```javascript
let arr = [1, 2, 8, 3];
arr.splice(2, 1); // arr [1, 2, 3]
```
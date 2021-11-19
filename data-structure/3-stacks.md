last in first out.
스택의 맨 위에서만 추가 제거가 이루어질 수 있다.
pop, push, isEmpty, peek, size.

```javascript
class Stack {
  constructor() {
    this.stack = [];
    this.size = 0;
  }

  isEmpty() {
    if (this.size === 0) {
      return true;
    } else {
      return null;
    }
  }

  pop() {
    if (this.size > 0) {
      let val = this.stack[this.size - 1];
      this.stack = [...this.stack.slice(0, this.size - 1)];
      this.size--;
      return val;
    } else {
      return null;
    }
  }

  // pop() {
  //   if (this.size > 0) {
  //     let val = this.stack[this.size - 1];
  //     this.stack.pop();
  //     this.size--;
  //     return val;
  //   } else {
  //     return null;
  //   }
  // }

  push(data) {
    this.stack[this.size] = data;
    this.size++;
  }

  // push(data) {
  //   this.stack.push(data);
  //   this.size = this.stack.length;
  // }

  peek() {
    if (this.size > 0) {
      let val = this.stack[this.size - 1];
      return val;
    } else {
      return null;
    }
  }

  getSize() {
    return this.size;
  }
}

let stack = new Stack();
stack.push(1);
stack.push(2);
```

first in first out.
rear에서 들어와서 front로 나간다.
enque, deque.

```javascript
class Queue {
  constructor() {
    this.queue = [];
    this.size = 0;
  }

  enqueue(data) {
    this.queue[this.size] = data;
    this.size++;
  }

  //   enqueue(data) {
  //       this.queue.push(data);
  //       this.size = this.queue.length;
  //   }

  dequeue() {
    if (this.size > 0) {
      let val = this.queue[0];
      this.queue = [...this.queue.slice(1, this.size)];
      this.size--;
      return val;
    } else {
      return null;
    }
  }

  //   dequeue() {
  //       if(this.size > 0) {
  //           this.size--;
  //           return this.queue.shift();
  //       } else {
  //           return null;
  //       }
  //   }
}

let queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
```

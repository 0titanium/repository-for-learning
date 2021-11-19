다음 원소와 링크에 의해 연결된 각 원소들이 차례로 나열된 원소들의 연속적인 구조.
listked list = head -> node[data, next] -> ... -> tail

```javascript
class Node {
  constructor(data, next = null) {
    this.data = data;
    this.next = next;
  }
}

class LinkedList {
  constructor(head = null) {
    this.head = head;
  }

  insertAtHead(data) {
    this.head = new Node(data, this.head);
  }

  insertAtTail(data) {
    let node = this.head;

    while (node) {
      if (node.next === null) {
          node.next = new Node(data, null);
          break;
      }

      node = node.next;
    }
  }

  insertAfter(data) {

  }

  deleteHead() {

  }

  deleteTail() {

  }

  deleteAfter() {
      
  }

  getSize() {
    let count = 0;
    let node = this.head;

    while (node) {
      count++;
      node = node.next;
    }

    return count;
  }

  clearList() {
    this.head = null;
  }
}

let node1 = new Node(1);
let node2 = new Node(2);
let node3 = new Node(3);
node1.next = node2;
node2.next = node3;
let list = new LinkedList(node1);
```

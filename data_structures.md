# Linked Lists 

A linked list is a series of linked node where each node points to the next node in the list.

- `push`, `pop`, `getIndex`, `deleteIndex`, `isEmpty`

- Doubly-linked lists exist that point to both the next and previous nodes in the list: these are bit better for deleting.

# Stacks

- Use stacks when you want to block off or discourage accessing items added to the structure earlier, like a stack of plates.

- `pop`, `push`, and `peek` are signature stack methods.

## Pros

- Constant time (0(1)) adding and removing of the top item

## Cons

- Not great at the accessing or writing to other items

```javascript
class Stack {
  constructor() {
    this.stack = []
  }

  get length() {
  return this.stack.length;
}

push(item) {
  return this.stack.push(item);
}

pop() {
  return this.stack.pop();
}

peek() {
  return this.stack[this.length - 1];
}

isEmpty() {
  return this.length === 0;
}
}
```

# Queues

Queues are similar to stacks, but operate on a FIFO basis. Use queues when you want to emulate this behavior, like a line at the movie theater.

- `enqueue`, `dequeue`, and `peek` are signature queue methods.

```javascript
export default class Queue {
  constructor() {
    this.queue = []
  }
  get length() {
    return this.queue.length
  }
  enqueue(item) {
    this.queue.push(item)
  }
  dequeue() {
    return this.queue.shift()
  }
  peek() {
    return this.queue[0]
  }
  isEmpty() {
    return this.length === 0
  }
}
```


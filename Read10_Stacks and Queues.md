# Stacks and Queues
- FILO: First In Last Out - Stacks
- FIFO: First In First Out - Queues
- LILO: Last In Last Out - Queues

## What is a Stack
-  Data structure that consists of nodes. Each node references the next node in the stack, but does not refernce its previous.
- Follows LIFO, first in last out, structure.
- Really cool because when it is implemented correctly it is an O(1) operation.

- push: Node or items that are put into the stack.
- pop: Node or items that are removed from the stack are popped. Exceptoin empty
- top: top of the stack.
- peek: means you will view the value of the top Exceptoin empty
- isEmpty: returns true when stack isEmpty or false when not empty.
- FILO: First In Last Out - the first item added in the stack will be the last item popped out of the stack.

- Push O(1) 
```
// INPUT <-- value to add, wrapped in Node internally
ALOGORITHM push(value)
   node = new Node(value)
   node.next <-- Top
   top <-- Node
```

- Pop O(1) 
```
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty
ALGORITHM pop()
   Node temp <-- top
   top <-- top.next
   temp.next <-- null
   return temp.value
```
- Peek O(1) 
```
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty
ALGORITHM peek()
   return top.value
```
- isEmpty O(1) - checks is the stack is empty.

```
// OUTPUT <-- boolean
ALGORITHM isEmpty()
return top = NULL
```
## What is a Queue
- Very similar to Stacks but the opposite.
- Follow FILO, first in last out.
- Front: first Node of the queue.
- Rear: rear/last Node of the queue.
- Peek: view the value of the front Node in the queue. Exception queue is empty.
- isEmpty: returns true when queue is empty or flase when it is not empty.

## Enqueue O(1)
- add an item to a queue
```
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
   node = new Node(value)
   rear.next <-- node
   rear <-- node
```
## Dequeue O(1)
- remove an item from the queue.
```
ALGORITHM dequeue()
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty
   Node temp <-- front
   front <-- front.next
   temp.next <-- null
   return temp.value
```
## Peek O(1)
- you will be inspecting the front Node of the queue. Check isEmpty beforehand.

```
ALGORITHM peek()
// OUTPUT <-- value of the front Node in Queue
// EXCEPTION if Queue is empty
   return front.value
```
## IsEmpty O(1)
- check is the queue is empty
```
ALGORITHM isEmpty()
// OUTPUT <-- boolean
return front = NULL
```

[Resources](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)
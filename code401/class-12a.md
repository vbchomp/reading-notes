# Class 12a - Stacks and Queues

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

[Stacks and Queues](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)

## Additional Resources

## Videos

## Vocab

## Bookmark/Skim

- Which 3 things had you heard about previously and now have better clarity on?
- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?
- What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- curried functions

- Class notes

- Stacks
- FILO and LIFO

- Call Stack: Learned in 201
  - Start() is the FILO, then once all the functions/methods finish, start pops off
  - Greeting() then finishes and pops off
  - form() then finishes and pops off stack
  - Goodbye() finishes then pops

- Push 
- Big O(1)
  - Will always take this long to add a node

- TOP Method
  - Where is the TOP?
  - Need to have a node that you are adding.
  - Change newTop = old to newTop = new

- Pop
- Big O(1)
  - Will always take this long to take off a node

- TOP Method
  - Assign Temp to TOP node.
  - Move TOP to next lowest node.
  - Pop the temp node
  - Clear the next from temp node. So temp.next = '';

- Peek
- Big O(1)

- TOP Method
  - Check if TOP is empty
  - If not empty, return TOP.value.

- Queues
- FIFO and LILO
  - Front has the next value of the value behind node
  - Rear has the null value

- Enqueue like Push
  - Big O(1)
  - Insert new node at end of queue.
  - Set next of the current rear to node behind last node. 
  - Set next of new rear to null after inserting new node.

- Dequeue like Pop
  - Big O(1)
  - Check next isEmpty
  - Create temp, assign front to front node
  - Assign old front to second in line
  - Taking off one node at front of queue.
  - Clear temp next, temp.next = '';

- Peek
  - Big O(1)
  - Check if queue isEmpty
  - if not, return front.value


stack.js
'use strict'

class Stack {

    constructor() {
        this.storage = new Array(); // can't use this .storage
        this.top = null;
    }

    push(value) {
        // not using built in methods
        this.storage.unshift(value);  // can't use this
        this.top = value;
    }

    pop() {
        // temp var to reassign top
        // reassign temp next to empty
        // return top
        let temp = this.storage.shift(); // can't use this
        this.top = this.storage[0]  // can't use this
    }

    peek() {
        //check if empty
        if (this.isEmpty) {
            return this.top;

        }
    }

    isEmpty() {}

}

module.exports = Stack;



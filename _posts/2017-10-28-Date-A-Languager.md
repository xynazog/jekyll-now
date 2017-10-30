---
layout: post
title: "TLDR version of SessionStack's Blog on JS."
published: true
---

### "I throw balls far. You want good words, date a languager." - Brad, Rick Portion #9, S01E06.

## TLDR Version of How JavaScript works by SessionStack
For full version, you can check [How JavaScript works  by SessionStack](https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf).

### Simplified version of JavaScript Engine
![JavaScript Internal Breakdown](https://cdn-images-1.medium.com/max/1600/1*OnH_DlbNAPvB9KLxUCyMsA.png)
Two major components: 
- Memory Heap (Here memory allocation happens)
- Call Stack (Frames are stacked here as the code executes)

### Simplifying the complicated reality?
![JavaScript Internal Breakdown with external parts](https://cdn-images-1.medium.com/max/1600/1*4lHHyfEhVB0LnQ3HlhSs8g.png)

> Reality = JavaScript Internals(Memory Heap + Call Stack) + Web APIs + Event Loop + Callback Queue

The APIs being used in daily life like EventListener is part of the **Web APIs**. These are provided by the browsers. 
The remaining parts are: **Event loop** and **Callback Queue**. (Remember Callback Hell? 😈)

### The Call Stack
JS is a single threaded programming language, meaning it has a single call stack.

Call Stack is a DS that records where in the program we are. Step into a function? Push it top of the stack. Return from a function? Pop it off the stack. 
<script src="https://gist.github.com/xynazog/b4ea215a844392a2d680a9b58feb30d4.js"></script>

![How does the Call stack work?](https://cdn-images-1.medium.com/max/1600/1*Yp1KOt_UJ47HChmS9y7KXw.png)

- Step 1: Call printSquare(5), push printSquare(5) onto the stack
- Step 2: Call multiply(5,5), push multiply(5,5) onto the stack
- Step 3: Return result of multiply(5,5), pop off multiply(5,5), Call console.log(), Push it onto the stack
- Step 4: Return the value of console.log(), pop it off the stack
- Step 5: Return the printSquare(5) function and pop it off the stack

Each entry in the stack is called a **Stack Frame**. Stack Frames are used to create Stack traces when an exception is thrown.

![Stack Trace Error!](https://cdn-images-1.medium.com/max/1600/1*T-W_ihvl-9rG4dn18kP3Qw.png)

#### Blowing the Stack? 😂
Reached maximum stack size? You have blown the stack. Happens easily (especially during recursion). 
<script src="https://gist.github.com/xynazog/4ebebdfe84d05c48056f4da9509240fa.js"></script>
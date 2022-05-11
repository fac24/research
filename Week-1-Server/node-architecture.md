# Node architecture 
Minju, Asmahan & Alex

---

## How does Node handle lots of requests despite running on a single processor thread?

---

Node, like JS, is single-threaded (i.e. it only looks at one task at a time), but it can hand over tasks to be dealt with elsewhere in the operating system and then it handles them only when they - and Node - are ready. It does this using the Message Queue and Job Queue.

---

## What is the event loop?

---

The event loop is the pattern in which Node deals with events. The event loop listens out for events and decides how to manage them.  

It takes the notice of the events one at a time, in the order they appear in the call stack, but it doesn't necessarily complete tasks in the order they appear there.

---

![](https://i.imgur.com/HIULffJ.png)

---

![](https://i.imgur.com/QlcGOq9.png)

---

![](https://i.imgur.com/FtdN0Tt.png)

---

Callback functions are put in the *Message Queue* - this is where user-initiated events and DOM events are queued. Tasks in the Message Queue are sent to the end of Node's call stack.

There is (since ES6) a *Job Queue*. While the Message Queue sets tasks to the end of Node’s call stack, the Job Queue fast-tracks them. 

---

## Why should we prefer asynchronous code? 

---

Asynchronous code avoids having to wait a long time for one piece of code to finish before starting on the next.

---

## What would happen if we had slow blocking code in our request handlers?

---

For these kind of situation, the delayed operation will be pushed back from the stack, and the execution of that process continues parallel to further execution of the main code. And the pushed back callback function will be continued asynchronously.

---

## How does Node use callbacks to manage asynchronous code?

---

Sometimes fetch data takes a while to load, blocking the program.

Node's solution? Callbacks! 

Callbacks => functions that run at the completion of another task.

In the case of errors, it's standard practice to follow the error callback convention- the callback runs after the function. There are two parameters- the error value and the callback:

---

![](https://i.imgur.com/93ZOPib.png)

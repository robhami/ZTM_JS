# ZeroToMastery

#### How JS works ####

A program needs to: 
  1. allocate memory
  2. parse and execute
  
  Javascript engine consists of two parts:
  
  1. Memory heap: memory allocation happens 
  2. Call stack: code read and executed, tells where u r in program
 
 Memory used by assigning variables
 ```
  const a=1;
  const b=10;
  const a=100;
```

Memory leaks happen due unused just laying around, e.g. glovbal variables not cleaned up can cause this. 

Call stack

Reads and executes in order of code then removes line after it executes:

```
console.log('1');
console.log('2');
console.log('3');

```

```
const one =()=>{
  const two = () => {
    console.log('4');
  }
  two();
}
 ```
 
 If call one then:
 
 ```
 >one();
 
 <4
 ```
 
 Call stack first ran one function, then we run two function which runs console.log('4'). 
 Then removes console.log(4), two and one functions in that order. then call stack is empty now. 
 
 Javascript is a single threaded language that is non blocking-
 
 Single threaded means it only has one call stack- it can only do one thing at a time. A call stack is first in last out.
 
 Multithreaded can cause issues (e.g. deadlocks).
 
 Synchronous programming means each line get executed at one time. 
 
 Stack overflow is where stack gets full. below is eg of recursion. 
 Recursion is where a function calls itself. This will cause a stack overflow by continuosly adding foo to call stack. 
 
 ```
 function foo() {
  foo()
 }
 
 foo()
 
 ```

Need asynchronous to overcome tasks that take too long and hold up call stack. Eg would be 'set timeout'.

First parameter is what we want to timeout, second parameter is hwo long we want it to timeout for in milliseconds. 
```
console.log('1');
setTimeout(() => {
  console.log('2');
  }, 2000)
console.log('3');

```

This gives:

```
1
3
2
```
The 2 take 2 secs to appear. 

We also need Javascript Run_time Environment (part of browser) in addition to callstack and memory heap. JS RT Env includes:

Web API's (e.g. Timeout (setTimeOut), AJAX, DOM)
Callback queue
Event Loop

Not technical JS but gives ability to do asynchronous programming.

Call stack
4. console.log('2'); - when callback pushes it here
3. console.log('3');
2.setTimeout(() => {
  console.log('2');
  }, 2000) - this triggers web API and waits 2 secs but takes it out of stack and moves to next 
1. Console.log('1');

Web API
setTimeout(), 2000

Callback queue
callBack() - this holds then calls the timedout function. Then pushes it to call stack when Event loop tells it to

Event loop
checks Call Stack and Callback queue and assigns anything in there

Everything empties after its run. 


If run it with 0 seconds delay, it still changes order because console.log(2) is pushed to the callback queue.
```
console.log('1');
setTimeout(() => {
  console.log('2');
  }, 0)
console.log('3');

```

This gives:

```
1
3
2
```

Another example: 

```
element.addEventListener('click',()=> {
  console.log('click')
})

```

This sits in calback queue until click occurs then it gets pushed to the callstack. 

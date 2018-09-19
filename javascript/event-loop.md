## The Event Loop

TLDR: The event loop continuously checks the call stack to see if there’s any function that needs to run. While doing so, it adds any function call it finds to the call stack and executes each one in order.

The event loop is the term given to the process of the waiting for the queue to receive a message synchronously. The increment that the event loop moves in is called a ‘tick’, and every time it ‘ticks’ it checks if the call stack is empty, if so , it adds the top function in the event queue to the call stack and executes it. Once it is finished processing this function it starts ticking again. 

## The Event Table

Every time you call a setTimeout function or you do some async operation — it is added to the Event Table. This is a data structure which knows that a certain function should be triggered after a certain event. Once that event occurs (timeout, click, mouse move) it sends a notice. Bear in mind that the Event Table does not execute functions and does not add them to the call stack on it’s own. It’s sole purpose is to keep track of events and send them to the Event Queue.

## The Event Queue

The Event Queue is a data structure similar to the stack — again you add items to the back but can only remove them from the front. It kind of stores the correct order in which the functions should be executed. It receives the function calls from the Event Table, but it needs to somehow send them to the Call Stack? This is where the Event Loop comes in.

##  Blocking The Event Loop
Any JavaScript code that takes too long to return back control to the event loop will block the execution of any JavaScript code in the page, even block the UI thread, and the user cannot click around, scroll the page, and so on.
Almost all the I/O primitives in JavaScript are non-blocking. Network requests, Node.js filesystem operations, and so on. Being blocking is the exception, and this is why JavaScript is based so much on callbacks, and more recently on promises and async/wait.

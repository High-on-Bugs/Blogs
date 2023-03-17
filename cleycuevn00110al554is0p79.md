---
title: "Getting into Node.js"
datePublished: Tue Mar 07 2023 14:37:03 GMT+0000 (Coordinated Universal Time)
cuid: cleycuevn00110al554is0p79
slug: nodejs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678194626769/94b743da-75f7-4b83-ad28-c9c65faff760.webp
tags: javascript, nodejs, node, event-loop, asynchronous-programming

---

Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that is built on Chrome's V8 JavaScript engine. It was created by Ryan Dahl in 2009 and is maintained by the Node.js Foundation. Node.js is used to build fast, scalable network applications and web servers, and its popularity has been growing rapidly since its inception.

Node.js was created to address the need for a non-blocking, event-driven I/O model that can handle large amounts of data and connections with high performance. Node.js uses an event loop that listens for incoming requests and responds to them asynchronously, which makes it ideal for handling real-time, data-intensive applications.

Node.js is built on top of Google's V8 JavaScript engine, which compiles JavaScript code into native machine code that can be executed directly by the computer's processor. This means that Node.js can execute JavaScript code much faster than other interpreted languages like PHP or Ruby.

**NOTE: Nodejs is not a framework. It is a runtime environment that is the basis for other frameworks like Express.**

### Features

Some features of Nodejs are:

1. **Asynchronous and event-driven**: Node.js is built on an event-driven, non-blocking I/O model that makes it lightweight and efficient. (more on this later)
    
2. **Cross-platform**: Node.js is built to work on a variety of platforms, including Windows, Mac OS X, and Linux.
    
3. **Fast**: Node.js is built on the V8 JavaScript engine, which is known for its high performance and speed.
    
4. **Scalable**: Node.js is designed to handle large-scale applications with ease, thanks to its non-blocking I/O model and event-driven architecture.
    
5. **Extensible**: Node.js has a large ecosystem of modules and libraries that can be easily installed and used in your applications.
    
6. **Server-side scripting**: Node.js is often used for server-side scripting, allowing developers to build powerful server-side applications using JavaScript.
    
7. **Easy to learn**: With its simple syntax and extensive documentation, Node.js is easy to learn for developers who are familiar with JavaScript.
    
8. **Community-driven**: Node.js has a large and active community of developers, who are constantly contributing to the development of new tools, modules, and libraries.
    
9. **Open source**: Node.js is an open-source platform, which means that anyone can contribute to its development and use it for free.
    

### Nodejs Architecture

Let us have a look at the Nodejs architecture, which will help us understand quite a lot of its features.

![Node.js Architecture From A to Z. Use Cases, Advantages, Big Players |  LITSLINK Blog](https://litslink.com/wp-content/uploads/2021/07/Node.js-Architecture-Chart.png align="left")

Node.js architecture is based on an event-driven, non-blocking I/O model that makes it highly efficient and scalable. The architecture consists of several components:

1. V8 Engine: Node.js uses the Google V8 JavaScript engine to execute JavaScript code. This engine compiles JavaScript into native machine code that can be executed directly by the CPU, making it faster than traditional interpreters.
    
2. Libuv: Node.js uses the Libuv library to provide an event loop and other asynchronous I/O capabilities. This library is also responsible for handling file system operations, networking, and other system-level functions.
    
3. Node.js APIs: Node.js provides a number of built-in APIs for interacting with the file system, networking, and other system-level functions. These APIs are written in C/C++ and are exposed to JavaScript via bindings.
    
4. Node.js Runtime: The Node.js runtime is the environment in which Node.js applications run. It provides a JavaScript execution environment, as well as access to system resources such as the file system, network, and operating system.
    
5. Operating System: Node.js applications run on top of an operating system, such as Linux, Windows, or macOS. The operating system provides access to hardware resources, such as the CPU, memory, and network interfaces.
    

Node.js uses an event loop to handle incoming requests and execute non-blocking I/O operations. The event loop is a loop that constantly checks for events and executes the associated callback functions. When a new request comes in, it is added to the event queue, and when the event loop reaches that event, it executes the associated callback function. This means that Node.js can handle many requests simultaneously, without blocking the execution of other requests.

Node.js achieves this by offloading time-consuming I/O operations, such as reading or writing to the file system or making network requests, to a separate thread pool. When an I/O operation is requested, Node.js adds it to a queue and sends it to the thread pool, freeing up the main thread to continue processing other requests. When the operation is complete, the thread pool returns the result to the main thread, which then executes the callback function.

Although Node.js uses a thread pool to offload I/O operations, it is still considered single-threaded because all user code runs on a single thread, and the thread pool is managed internally by Node.js. Additionally, because Node.js uses non-blocking I/O operations, the thread pool is only used for time-consuming tasks, and most operations can be handled by the main event loop.

%[https://www.youtube.com/watch?v=6YgsqXlUoTM] 

Check out this video if you want to know about the event loop in detail. Or if you have half an hour you can go for the one provided below.

%[https://www.youtube.com/watch?v=8aGhZQkoFbQ] 

### What are Events?

Events in Node.js are a mechanism used to handle and respond to actions or signals that occur asynchronously in a program. In Node.js, the `EventEmitter` class is used to implement the event-driven architecture. The EventEmitter allows developers to create custom events and handle them with corresponding listeners.

Events in Node.js work on a publisher-subscriber model, where publishers emit events and subscribers listen to those events. When an event is emitted, all subscribers to that event are notified and can respond accordingly. This makes it possible for Node.js applications to be highly responsive to user input and other events that occur in the system.

Node.js has a built-in `events` module that provides the EventEmitter class and other related utilities for working with events. The `events` module can be used to implement complex event-driven systems such as web servers, real-time chat applications, and other systems that need to handle multiple concurrent connections.

### The Non-Blocking model

This is one of the features of the Nodejs architecture. Let us first understand what blocking code vs non-blocking code is from GeeksforGeeks.

**Blocking:** It refers to the blocking of further operations until the current operation finishes. Blocking methods are executed synchronously. Synchronously means that the program is executed line by line. The program waits until the called function or the operation returns.

**Example:** The following example uses the [**readFileSync()**](https://www.geeksforgeeks.org/node-js-fs-readfilesync-method/) function to read files and demonstrate Blocking in Node.js

```javascript
const fs = require('fs');

const filepath = 'text.txt';

// Reads a file in a synchronous and blocking way
const data = fs.readFileSync(filepath, {encoding: 'utf8'});

// Prints the content of file
console.log(data);

// This section calculates the sum of numbers from 1 to 10
let sum = 0;
for(let i=1; i<=10; i++){
	sum = sum + i;
}

// Prints the sum
console.log('Sum: ', sum);
```

On running the **index.js** file use the following command:

```bash
node index.js
```

**Output:**

```bash
This is from text file.
Sum:  55
```

**Non-Blocking:** It refers to the program that does not block the execution of further operations. Non-Blocking methods are executed asynchronously. Asynchronously means that the program may not necessarily execute line by line. The program calls the function and moves to the next operation and does not wait for it to return.

**Example:** The following example uses the [**readFile()**](https://www.geeksforgeeks.org/node-js-fs-readfile-method/) function to read files and demonstrate Non-Blocking in Node.js

Run the **index.js** file using the following command:

```javascript
const fs = require('fs');

const filepath = 'text.txt';

// Reads a file in a asynchronous and non-blocking way
fs.readFile(filepath, {encoding: 'utf8'}, (err, data) => {
	// Prints the content of file
	console.log(data);
});


// This section calculates the sum of numbers from 1 to 10
let sum = 0;
for(let i=1; i<=10; i++){
	sum = sum + i;
}

// Prints the sum
console.log('Sum: ', sum);
```

On running the **index.js** file use the following command:

```bash
node index.js
```

**Output:**

```bash
Sum:  55
This is from text file.
```

In the non-blocking program, the sum actually prints before the content of the file. This is because the program does not wait for the readFile() function to return and move to the next operation. And when the readFile() function returns it prints the content.

### How does Nodejs handle this?

Node.js uses an event-driven, non-blocking I/O model to handle both blocking and non-blocking code. When a blocking operation is called, Node.js delegates the operation to the system kernel, which frees up the event loop to handle other tasks. Once the operation is complete, Node.js will handle the callback function in the event loop. This allows Node.js to execute other code while waiting for the operation to complete.

On the other hand, non-blocking code is executed immediately, and the result is passed to the callback function when the operation is complete. This allows Node.js to continue executing other code while waiting for the non-blocking operation to complete.

Node.js also has a thread pool that is used for some built-in modules like `crypto`, `zlib`, and `fs` module synchronous functions. These functions are executed outside of the main event loop to prevent blocking the execution of other code.

In summary, Node.js handles blocking and non-blocking code by delegating blocking operations to the system kernel and executing non-blocking code immediately while passing the result to a callback function. The thread pool is used to offload blocking synchronous functions from the main event loop to prevent blocking other code.

### A step-by-step explanation.

Thanks to Andrew Mead for explaining this in his course.

![](https://miro.medium.com/v2/resize:fit:875/1*BBlPbUjGVtfSPd7BHa1LHw.png align="left")

1. Push `main()` onto the call stack.
    
2. Push `console.log()` onto the call stack. This then runs right away and gets popped.
    
3. Push `setTimeout(2000)` onto the stack. `setTimeout(2000)` is a Node API. When we call it, we register the event-callback pair. The event will wait 2000 milliseconds, then the callback is the function.
    
4. After registering it in the APIs, `setTimeout(2000)` gets popped from the call stack.
    
5. Now the second `setTimeout(0)` gets registered in the same way. We now have two Node APIs waiting to execute.
    
6. After waiting for 0 seconds, `setTimeout(0)` gets moved to the callback queue, and the same thing happens with `setTimeout(2000)`.
    
7. In the callback queue, the functions wait for the call stack to be empty because only one statement can execute at a time. This is taken care of by the event loop.
    
8. The last `console.log()` runs and the `main()` gets popped from the call stack.
    
9. The event loop sees that the call stack is empty and the callback queue is not empty. So it moves the callbacks (in a first-in-first-out order) to the call stack for execution.
    

### How is Nodejs different from normal Javascript?

JavaScript (JS) and Node.js are both based on the same programming language, but they have some key differences:

1. **Environment**: JS runs in a browser, while Node.js runs in a server-side environment.
    
2. **Modules**: JS has a limited module system, whereas Node.js has a powerful module system that enables developers to write modular and reusable code.
    
3. **APIs**: JS has a set of APIs for manipulating the Document Object Model (DOM), while Node.js has APIs for file system operations, networking, and more.
    
4. **Global objects**: JS has a set of global objects that are available in the browser environment, such as "window" and "document". Node.js has a different set of global objects that are available in the server-side environment, such as "process" and "console".
    
5. **Threading**: JS is single-threaded, which means it can only execute one task at a time. Node.js is also single-threaded, but its sophisticated architecture helps it to handle more concurrent connections.
    
6. **Performance**: JS is designed to run in a browser environment, so it is optimized for handling user interactions and rendering web pages. Node.js is optimized for handling I/O operations and network requests, so it is faster and more efficient for server-side tasks.
    

These points may also lead to the question, "what's the difference between CommonJS and ES6?"

Let us have a look at CommonJS vs ES modules in depth:

<table><tbody><tr><td colspan="1" rowspan="1" colwidth="206"><p><strong><em>Basis</em></strong></p></td><td colspan="1" rowspan="1"><p><strong><em>CommonJS&nbsp;</em></strong></p></td><td colspan="1" rowspan="1"><p><strong><em>ES Module</em>&nbsp;</strong></p></td></tr><tr><td colspan="1" rowspan="1" colwidth="206"><p>Functionality&nbsp;</p></td><td colspan="1" rowspan="1"><p>Works with the Node.js platform&nbsp;</p></td><td colspan="1" rowspan="1"><p>Works with the web browser environment&nbsp;</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="206"><p>Compilation&nbsp;</p></td><td colspan="1" rowspan="1"><p>Compiled into AMD modules&nbsp;</p></td><td colspan="1" rowspan="1"><p>Does not require a module loader like AMD</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="206"><p>Dependencies&nbsp;</p></td><td colspan="1" rowspan="1"><p>All dependencies are listed in the same file&nbsp;</p></td><td colspan="1" rowspan="1"><p>Reference any other module in the same package available on the global namespace&nbsp;</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="206"><p>Type<strong>-</strong>checking&nbsp;</p></td><td colspan="1" rowspan="1"><p>No type-checking capabilities&nbsp;</p></td><td colspan="1" rowspan="1"><p>Robust typing support via imports</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="206"><p>Dependency Packaging&nbsp;</p></td><td colspan="1" rowspan="1"><p>Packaging up functionality into small pieces&nbsp;</p></td><td colspan="1" rowspan="1"><p>Declare dependencies between modules&nbsp;</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="206"><p>File Structure&nbsp;</p></td><td colspan="1" rowspan="1"><p>Flat files&nbsp;</p></td><td colspan="1" rowspan="1"><p>References to other modules&nbsp;</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="206"><p>Export&nbsp;</p></td><td colspan="1" rowspan="1"><p>Exports in the same file<strong>&nbsp;</strong></p></td><td colspan="1" rowspan="1"><p>Exports scattered through the codebase&nbsp;</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="206"><p>Import&nbsp;</p></td><td colspan="1" rowspan="1"><p>No import functionality&nbsp;</p></td><td colspan="1" rowspan="1"><p>Must use a require statement to access exported functions and properties</p></td></tr></tbody></table>

**NOTE: In JavaScript, a module is a self-contained unit of code that defines a set of related functions, objects, and data. A module system is a way to organize and manage these modules in a codebase. CommonJS, ES6, and AMD are all module systems.**

### Why is Nodejs Scalable?

Node.js is scalable because of the non-blocking I/O model (mentioned above), which allows it to handle multiple concurrent connections efficiently. In traditional server-side models, each incoming connection would block the server, leading to degraded performance under high traffic. However, Node.js's event-driven, single-threaded architecture enables it to handle large numbers of requests simultaneously without getting bogged down.

When a request comes in, Node.js places it in a queue and continues processing other requests. When the I/O operation is complete, Node.js notifies the event loop, which then executes the corresponding callback function. This approach allows Node.js to handle multiple requests at the same time without blocking the main thread, making it a highly scalable platform for building networked applications.

![](https://miro.medium.com/v2/resize:fit:780/0*kJ6vNeUGrJ0x115j. align="left")

### Some drawbacks.

While Node.js has many advantages, it also has some disadvantages that developers should be aware of.

1. **Not ideal for CPU-intensive applications**: Node.js is designed to handle I/O-bound tasks, making it less efficient for applications that require a lot of CPU processing power. These types of applications could cause the event loop to block, slowing down the entire server.
    
2. **Asynchronous Programming** is difficult to understand for new developers.
    
3. **Not suitable for heavy-load applications**: While Node.js can handle a large number of concurrent connections, it may not be the best choice for extremely high-traffic applications, as it can become difficult to scale vertically.
    

---

This was mostly a theoretical blog on Nodejs. The main aim was to cram as much info into a single place to serve as a reference before interview prep. If you did find this helpful, stay tuned/like/all that good stuff. Will write on more topics. If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!
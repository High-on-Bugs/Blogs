---
title: "Backend Development - Part 1"
datePublished: Fri Mar 17 2023 13:24:11 GMT+0000 (Coordinated Universal Time)
cuid: clfckn8q4000209meesvg7k9r
slug: backend-part-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1679057514376/64c2a3fd-0b4f-4200-ad4b-cff5d5c584d8.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1679059445126/fedfc367-ee00-43c6-bcbc-8c9dd8545114.jpeg
tags: express, mongodb, nodejs, backend, full-stack

---

This series is the one I've been preparing for till now. The REST series and the Web Basics series all build up to this series. So, this is the blog that will kick off the Backend Development series. Let's first see what we are working with and what we'll be building.

### The Tech Stack

MongoDB is a popular NoSQL database that provides scalability and flexibility for data management. Node.js is a powerful runtime environment for executing JavaScript code on the server side, while Express is a minimalist web framework for building APIs and web applications.

Together, these technologies provide a robust, scalable, and efficient solution for building a backend for a blog. In this guide, we will explore the fundamentals of using MongoDB, Node.js, and Express to build a backend for a blog, covering everything from setting up the environment to creating RESTful APIs and integrating them with a front end. So, let's get started!

### What are we building?

We'll be building a user login system, which is a fundamental feature in most web applications, allowing users to securely access their personal information and data. However, building a user login system can present some challenges, such as user authentication, security, and session management.

One of the first challenges in building a user login system is implementing a secure authentication process. This can be accomplished through the use of secure encryption and hashing techniques, such as "bcrypt", to store passwords and compare them to user inputs.

Another challenge is managing user sessions to maintain the user's authentication state across multiple requests. This can be achieved through the use of cookies or JSON Web Tokens (JWTs), which store session data on the client side and allow for secure authentication and authorization.

Technologies commonly used in building a user login system include Node.js, Express, and MongoDB for backend development, and frameworks for the front-end side of things.

For authentication, technologies like JSON Web Tokens can be used. Sessions can be managed with the help of packages like Express-session or JWT tokens.

### Pre-requisites

Some of the Prerequisites for the series are:

1. **JavaScript**: JavaScript is the primary programming language used in building web applications with Node.js and Express. A basic understanding of JavaScript fundamentals, including data types, functions, and control flow, is necessary.
    
2. Node.js: Knowledge of Node.js is quite important. Check out my [blog on Nodejs](https://highonbugs.sbk2k1.me/nodejs) for a quick refresher.
    
3. **RESTful APIs**: Building a blog requires creating RESTful APIs to handle requests and responses. Understanding RESTful API design principles and how to create endpoints for a web application is necessary. Check out my [REST series](https://highonbugs.sbk2k1.me/series/rest-series).
    
4. **HTML, CSS, and front-end frameworks**: Building a blog also requires knowledge of HTML and CSS for creating a user interface. Knowledge of front-end frameworks such as React is helpful for building dynamic and responsive user interfaces.
    
5. Basics of how the Web Works: Check out my series on [Web Basics](https://highonbugs.sbk2k1.me/series/web-basics) as well.
    

We'll figure out and explain other requirements as we go along.

---

That's it! We'll start with installation and setup in the next blog. This was just a small blog to update on the Backend Dev blog series, that I've been preparing for a long time. If you did find this helpful, stay tuned/like/all that good stuff. Will write on more topics. If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!
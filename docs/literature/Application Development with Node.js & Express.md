# Application Development with Node.js & Express

This document contains notes based on the course provided by IBM on edX.\
<a href = "https://learning.edx.org/course/course-v1:IBM+CAD220EN+3T2022/home?_gl=1*u05ill*_gcl_aw*R0NMLjE3MjU5NDc3MjAuQ2p3S0NBand1ZnEyQmhBbUVpd0FuWnF3OHZON0s5THZQSFdsdVFYVG4taXdJNlpiSnBwMEtXemg1Mlg3bDZieG9pLWtzT0Vkb2xfYVhSb0M1amdRQXZEX0J3RQ..*_gcl_au*Mzk4MTUxMjY4LjE3MjU5NDc1MzM.*_ga*NTIwNzIwNzE0LjE3MjU5NDc1MzI.*_ga_D3KS4KMDT0*MTcyNTk0NzUzMy4xLjEuMTcyNTk0NzczNy40Mi4wLjA.">Link to the course</a>

## Introduction

### Why Node.js and Express
- Node.js is the most popular used server-side technology (based on stackoverflow survey 2022).
- Express ranked as the 4th most popular web technology overall, which makes it the most rated server-side framework.

### What are Node.js and Express
- <b>Node.js</b> is a runtime environment that can run server-side JavaScript applications.
- <b>Express</b> is a server-side JavaScript web framework that runs on top of Node.js.

### Objectives
- Server-side development using JavaScript
- Code first web server using node package manager
- Make applications run in a non-blocking manner
- Use Asynchronous callbacks and promises
- REST APIs usage with Express.js
- Build web server using Express
- Create dynamic content with middleware, routing, and templating

## Overview

Focusing on Node.js and Express, specifically the goal is to:
- Develop applications using asynchronous callbacks and promises
- Create REST APIs and perform CRUD operations
- Implement authentication and session management

## Introduction to Sever-Side JavaScript

### What is Back End Development

- Back-end developers write code to communicate with the browser's engine and back-end server
- Back-end technologies includes servers, databases, web APIs, programming languages, frameworks and runtime
- Servers can refer to hardware, software or both
- Servers communicate with and provide functionality to a client
- Servers can also communicate with and provide functionality to each other

### Types of servers

- Database servers
    - House, retrieve, and deliver data
    - Database server and database often used interchangeably
- Application servers
    - Host and deliver the application through HTTP
    - They sit between a database server and a web server
    - Transform data into content
    - Run business logic
        - Data storage rules
        - Transfer rules 
- Web servers
    - Web APIs are how two pieces of software communicate.
    - Web service is a programming interface that sends and receives requests using HTTP among web servers and client
    - Web service is a type of web API
 
### Back-end languages

Languages used to make the servers function. Languages include: JavaScript, PHP, Python, Ruby, Java, C#.

### Frameworks

- Provide structure for code
- Generates code that cannot be altered
- Back-end frameworks include:
  - Django (Python)
    - Ruby on Rail (Ruby)
    - Express.js (JavaScript)
- Express.js is a framework that runs on top of Node.js that handles HTTP requests made to a web server.
 
### Runtime environments

- Like a mini operating system that provides the resources necessary for an application to run
- The infrastructure that supports the execution of a codebase
- The environment in which an application gets executed
- Node.js is a back-end runtime environment
 
### Node.js

- Runs on Google Chrome's V8 engine
- The V8 engine also runs on the client's front-end browser
- Executes JavaScript
- JavaScript can be used on the front-end and back-end
 
### Backend responsibility

- Scalability: Essential for enterprise software success and is the responsibilty of the backend which is affected by the load on an application
- Load: Number of concurrent users, number of transactions, and the amount of data transfer between clients and servers

Scalability is the application's ability to dynamically handle changes in load without affecting performance
Essential for the success of a client-server application.

### Other back-end responsibilities

- Security
- Authentication
- Malware prevention
- Performance
 
## Back-end and Front-end Development Overview

### Key components of Back-end Development

1. <b>Server</b>: The hardware or software that provides resources, data, services, or programs to clients over a network.
2. <b>Database</b>: A structured collection of data that can be easily accessed, managed, and updated.
   - <b>SQL Databases</b>: Relational databases like MySQL, PostgreSQL, and SQLite.
   - <b>NoSQL Databases</b>: Non-relational databases like MongoDB, Cassandra, and Redis.
3. <b>Server-Side Languages</b>: Programming languages used to build the back-end logic.
   - <b>Node.js</b>: JavaScript runtime built on Chrome's V8 JavaScript engine.
   - <b>Python</b>: A high-level programming language known for its readability and efficiency.
   - <b>Ruby</b>: A dynamic, open-source programming language with a focus on simplicity.
   - <b>Java</b>: A versatile and powerful programming language used for large-scale applications.
4. Frameworks and Libraries:
   - <b>Express</b>: A minimal and flexible Node.js web application framework.
   - <b>Django</b>: A high-level Python web framework that encourages rapid development.
   - <b>Ruby on Rails</b>: A server-side web application framework written in Ruby.
   - <b>Spring</b>: A comprehensive framework for enterprise Java development.

### Importance of a Robust, Scalable Back-end

A robust back-end ensures data security, performance, scalability, and smooth application logic. It supports user interactions, handles business logic, and integrates with front-end systems.

### Front-end Development

Front-end development, also known as client-side development, involves creating the part of a website or application that users interact with directly. This includes everything the user experiences visually and through interactions.

### Key Components of Front-end Development

1. <b>HTML (HyperText Markup Language)</b>: The structure of web pages, defining elements such as headings, paragraphs, images, and links.
2. <b>CSS (Cascading Style Sheets)</b>: The styling of web pages, including layout, colors, fonts, and responsiveness.
3. <b>JavaScript</b>: The behavior of web pages, enabling interactive features like forms, animations, and dynamic content updates.
4. <b>Frameworks and Libraries</b>:
  - <b>React</b>: A JavaScript library for building user interfaces.
  - <b>Angular</b>: A TypeScript-based framework for building web applications.
  - <b>Vue.js</b>: A progressive JavaScript framework for building user interfaces.

### Responsibilities of a Front-end Developer

- Create responsive designs
- Ensure cross-browser compatability
- Optimize performance
- Implement accessibility standards
- Collaborate with designers to implement mockups

## Getting started with Node.js

### Full-stack application

A full-stack application includes the following components:
- <b>The Client Side:</b>
  The website and the mobile application that are user-facing.
- <b>The Server Side:</b>
  Processes any requests from the client side and sends responses back to the client. In today's world, the cloud hosts the web server, application server, and database.
- <b>Open Source and Cross-Platform:</b>
  JavaScript is an ideal choice for client-side validation of HTML pages due to its versatility and cross-platform compatibility. Recognizing its ease of use, JavaScript was further adapted for server-side coding, resulting in Node.js. Node.js functions as a runtime environment, and what's more, it requires no special licenses for use. Additionally, a plethora of packages and libraries have been developed for use with Node.js, thanks to its open-source nature. Furthermore, Node.js code can seamlessly run across various operating systems such as Linux, Windows, and Mac OSX.
- <b>V8 Engine:</b>
  Every piece of code you write needs to undergo processing and conversion into a machine-readable form. In the realm of Node.js, JavaScript code is executed using the Google V8 engine. Renowned for its high performance, V8 is an open-source engine developed by Google, and it is integrated into all Google Chrome browsers. Moreover, modern browsers like Microsoft Edge and Firefox also employ the V8 engine for executing Node.js code.
- <b>Event-Driven, Asynchronous, Non-Blocking, Single-Threaded:</b>
  Server processes can be categorized as either "single-threaded" or "multi-threaded". In a single-threaded environment, only one command is processed at any given time, while in a multi-threaded environment, multiple commands can be processed simultaneously. Despite being single-threaded, Node.js excels in performance due to its asynchronous and non-blocking nature. This means that while a process is being executed, the program does not need to wait until it finishes. Node.js is event-driven, meaning that when it performs an input/output (I/O) operation, such as reading from the network or accessing a database or file system, an event is triggered. Instead of blocking the thread and consuming processor time while waiting, Node.js resumes operations when the response is received, or when the corresponding event occurs. This non-blocking behavior enables the server to remain responsive and handle multiple tasks concurrently, akin to a multi-threaded environment.

## JSON Payload

JSON stands for JavaScript Object Notation, formatted as "key-value pairs". The payload represents the data transmitted between the client and the server. When the client needs to send data to the server, it does so in the form of a JSON object, as illustrated in the example below:

```
{
    "name": "John",
    "age": "24",
    "email": "johnparker@gmail.com"
}
```
The above object is a JSON. When this data is sent as part of the request, its values can be extracted simply by using `request.name` and so on.

Similarly, the response is also sent as JSON. An example is provided below:

```
{
    "status": "ok",
    "message": "Successfully added"
}
```

### Express Framework

While Node.js provides packages to create a server, the Express framework simplifies the process of creating APIs and endpoints. An API endpoint is a specific point of entry for a request from the client to the server.

## Introduction to Node.js

- Node.js is an open source language that runs on V8
- V8 is an open source engine developed by Google for Google Chrome browser

### Node.js functionality

- Developers often use JavaScript for client-side functionality. Node.js is the server component in the same language.
- Node.js is event-driven and uses asynchronous, non-blocking I/O.

### JavaScript with Node.js

- <b>Step 1</b>: The user selects an option in the user interface, written in HTML and CSS.
- <b>Step 2</b>: this action by the user triggers JavaScript code that implements the business logic on the client-side, for example, input validation.
- <b>Step 3</b>: the JavaScript application makes a web service call over HTTP with a JSON data
payload. The REST web service, which is part of a node.js application running on the node server, receives
- <b>Step 4<b>: the REST web service processes the request and returns the result to the
client as a JSON payload over HTTP.

### Node.js usage

- Developers can now use Node.js in the same components of the architecture where they use Java, Perl, C++, Python, and Ruby.
- Node.js is used in production by companies, such as Uber, Yahoo!, LinkedIn, GoDaddy, eBay, and PayPal.
- It is event-driven and uses asynchronous, non-blocking I/O.

### Express.js

- Configurable framework for building applications on Node.js
- Abstracts lower-level APIs in Node.js by using  HTTP utility methods and middleware.

### Key Node.js Concepts

Express.js simplifies application development on Node.js.
The following features enable you to develop your application quickly:
- <b>Public</b>: public assets like image, CSS, and javascript.
- <b>Templates/views</b>: server-rendered HTML that is sent back to the client in response to requests.
- <b>Routes</b>: defines endpoints that accept and process client requests.
- <b>Server.js</b>: a file which contains the main application code.
- <b>Package.json</b>: contains metadata information about the project including dependencies.

## Import and Require

To be continued

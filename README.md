# WebServ
### Nginx says hi, :blush:
---
#### Project OverView: {#overview}
As the title suggest, this is a simple project where we have to simulate the **client/server** model through **http** protocol using *socket programming*.
Our task is simply to create a **web server** that is responsable to adhere to config file rules, parse client request and send a convenient response.
<br />

Socket Programming
: is simply programming using **socket** APIs, and a socket itself is nothing but a network(local, remote) ability to connect 2 nodes(devices) on a network so that they can communicate, one socket listens for upcoming connection --server-- whereas another socket --client-- reach out and the **connection happens**.

##### Explanatory Example:
Take as an example the website [Example.com](https://www.example.com) is using nginx server (very popular open source webserver). As soon as the nginx deamon is running, the server then is called to be in "pending" mode, meaning **server socket** actively waiting for clients to reach. Now there is you "Handsome reader", who typed Example.com in the url bar and hit enter, in the *background* your browser has **created a socket** and tries to connect to the site ip server ==> connection established and http request/response flows starts.

<br />

I/O Multiplexing
: A real world experience like the one aformentioned is not always the case, we won't have a **single user** "You" requesting files from server instead there is millions and millions of users who dumps the servers for data in short amount of time (say milliseconds). The servers need to handle this workflow and **serve all users equally** in an efficent way.
This whole operation, is what it is simply referred as *I/O multiplexing*. Using sockets, they are 2 mainly modes ***Blocking*** and ***Non-Blocking***.
<br />
In the **blocking** mode the socket will hang until that client request is fully served, which is inefficient (for ex, Client getting a large video, other clients will wait until the full video is served since the main parent thread is blocking on sending that video).
**Non-Blocking** sockets are simply a socket that recv/send read/write operations on doesnt hang, it serve little to one user then switch to serve another etc...
This could be achieved by *select* system call for example.

---

#### Project Separation:
I collaborated with 2 other teammates, one was assigned the task of *I/O mutliplexing*, me and the second one we took responsabilty of the http request itself.
The subject stated to handle 3 http verbs (Get, Post, Delete) and Cgi for each one of these methodes.
I took the **Post method** with all its functionalities (Content-Type, Transfer-Encoding...) and its cgi ofc :smiley:

#### Project Takeways:

| Skills | Description |
| ----------- | ----------- |
| Socket Programming | [Click here](#overview) |
| Convenient Http Responding | Reply with the right response status code  |
| Cgi Implementation | Execute the file requested and return its output as response to the client  |

##### Project Rating: 
![](https://geps.dev/progress/90?dangerColor=800000&warningColor=ff9900&successColor=006600)



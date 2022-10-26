---
title: "Pizza-N-Go: A Full-stack Application"
date: 2021-11-15T14:04:51-05:00
draft: false
categories: 
    - Full-stack
weight: 1
ShowToc: true
TocOpen: true
cover:
    image: /images/portfolioImages/pizzango/1.jpeg#center
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    alt: "pizza-image"
    relative: false # To use relative path for cover image, used in hugo Page-bundles
---

I would admit, the picture above looks delicious, isn't it ? 
 
I like to present the food ordering application I have created to learn Full-stack Web Development. I had general understanding of the web application and how they are built, but I always wanted to build one from ground up with some of the advance features like real time communication using Web Sockets, user Sessions and Cookie management, integrating text message API, asynchronous operations and more. Furthermore, I wanted to sharpen my skills for AWS by deploying the complete app on AWS platform using some core services like EC2 instances, RDS Database, DynamoDB, Route 53 etc.
 
You can find this application running live on [🍕 Pizza-N-Go](https://pizzango.sidpatel.org/)
 
Let me start from the features and working of this application, and then I will try to explain the technology I've used later.
 
## Application
 
&nbsp;
 
![pizza-n-go-homepage](/images/portfolioImages/pizzango/2.png#center)
 
This application consist of platform where users and admin(Pizza-n-go restaurant) can interact with each other. First, there is a functionality for a user to sign up and login from the homepage. Admin credentials are hard coded in the database, so all the new users created from the sign-up form will have assigned role as 'users'.
 
![pizza-n-go-homepage](/images/portfolioImages/pizzango/3.png#center)
 
From the homepage it may look simple, but when you log in as a user or as an admin, the portal you interact would be different. Below, I have shown two screens side-by-side. On the right a user has items in carts and on the left this is how a restaurant would see their portal. Notice that restaurant has different functionalities than a regular user, where they can track or adjust the status of the orders.
 
![pizza-n-go-homepage](/images/portfolioImages/pizzango/6.png#center)
 
You can notice that when a user adding items in cart, the cart in the navbar is also updating at the same time. To place an order, user have to be logged in. The user cart is managed by user sessions. I will explain about this later in backend technology section. 
 
Once a user place an order, they will be redirected to an order tracking page. This page shows the order ID and other details about the order. Along with this web message, an SMS will be sent to the customer cell number that they used while registering. At the same time, the restaurant will receive the notification about the new order. This communication between user and restaurant happens in real-time with Web Socket protocol. 
 
![pizza-n-go-homepage](/images/portfolioImages/pizzango/7.png#center)
 
From here, a restaurant can set an estimated time it will require to fulfill this order.  When a restaurant set the time and click 'send SMS' button, the status of order will be changed from 'New' to 'In-Progress' and a user will receive a text message about this change along with update on the web portal.
 
![pizza-n-go-homepage](/images/portfolioImages/pizzango/8.png#center)
 
At last, the restaurant has an order ready, they can click 'ready to pickup' on their portal. This will move the order from 'In-Progress' to 'Completed' state and a use to receive notification for order pick up on phone and web portal.
 
![pizza-n-go-homepage](/images/portfolioImages/pizzango/9.png#center)
 
Now, let me explain how some feature in this application are implemented. 
 
## Frontend
 
The front of the application is build using simple HTML, CSS, client side JavaScript and EJS templating engine for JavaScript. All the pictures and details about the food you see on the page is stored in the database. When a user visits the page, the browser will send a request to the server asking for required HTML, CSS and JavaScript files. 
 
There is a logic written in these JavaScript files that make asynchronous request to server asking for the images for food and detail to show on the page. I have used a library called [Axios](https://www.npmjs.com/package/axios) to fetch the data. 
 
Now let's move to the backend or server side logic. This is where all the magic happens.
 
## Backend - Server logic
 
I have used Node.js with Express framework to write the server logic. Primary reason for choosing this tech stack is that, there are a lot of libraries available for Node.js. Furthermore, I have not done any projects in Node.js before this, so by building the app in Node.js would give me insight in new Technology. 
 
You may be intrigued by the real-time communication notification between user and restaurant. This was new to me before I started this project, and it was the primary reason I made this project so that I can learn about the events, Web Sockets in web development. [Web socket](https://en.wikipedia.org/wiki/WebSocket) is a protocol like HTTP. But unlike HTTP, the connection in Web Socket stay open between client and server. Typically, this protocol is used when there is need for real-time communication like chat box, score update during sport tournament etc. I am using [Twilio](https://www.twilio.com/) API to send SMS to customers.
 
The database is PostgreSQL database. User details, Food items and all the Orders are stored in the database. As I mentioned before, I am using sessions to manage user cart, login status etc for particular user. To keep this information persistent, I am storing them in PostgreSQL database as well. Although I am using this method for storing sessions, this is not a good architecture. Generally, sessions are stored in NoSQL databases like DynamoDB or in-memory databases like Redis. 
 
## Deployment - Amazon Web Services(AWS)
 
I have deployed this application on [AWS](https://aws.amazon.com/). The compute layer is deployed on EC2 Linux instances and Database is on the RDS PostgreSQL database. Normally if you deploy node application on EC2 instance, it will stay on until you are connected to it, but to keep it running I have used PM2 library. Nginx web server is load balancing the traffic coming from client.
 
The application is using [SSL](https://www.cloudflare.com/en-ca/learning/ssl/what-is-an-ssl-certificate/) certification from [Certbot](https://certbot.eff.org/). I will post detail blog post for deploying detail instructions how to add SSL certificate and deploy it on any Linux computer.












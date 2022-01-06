---
title: "Pizza-N-Go - A FullStack Application"
date: 2021-11-15T14:04:51-05:00
draft: false
categories: 
    - FullStack
cover:
    image: /images/portfolioImages/pizzango/1.jpeg#center
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    alt: "<alt text>"
    caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles
---

I would admit, the picture above looks delicious, isn't it ?  

I like to present the food ordering application I have created to learn FullStack Web Development. I had general understading of the web application and how they are built, but I always wanted to build one from ground up with some of the advance features like real time communication using Web Sockets, user Sessions and Cookie management, integrating text message api, asynchronous operations and more. Furthermore, I wanted to sharpen my skills for AWS by deploying the complete app on AWS platform using some of the core services like EC2 instances, RDS Database, DynanoDB, Route 53 etc. 

You can find this application running live on [🍕 Pizza-N-Go](https://pizzango.sidpatel.org/)

Let me start from the features and working of this applicaiton, and then I will try to explain the technology I've used later.

## Application 

 &nbsp; 

![pizza-n-go-homepage](/images/portfolioImages/pizzango/2.png#center)

This application consist of platform where users and admin(Pizza-n-go restaurant) can interact with each other. First there is a functionality for a user to sign up and login from the homepage. Admin credentials are hardcoded in the database, so all the new users created from the sign-up form will be have assigned role as 'users'. 

![pizza-n-go-homepage](/images/portfolioImages/pizzango/3.png#center)

From the homepage it may look simple, but when you login as a user or as an admin, the portal you interact would be different. Below I have shown two screens side-by-side. On the right a user has itms in carts and on the left this is how restaurant would see their portal. Notice that restaurant has different functionalities than a regular user, where they can track or adjust the status of the orders.

![pizza-n-go-homepage](/images/portfolioImages/pizzango/6.png#center)

You can notice that when a user adding items in cart, the cart in the navbar is also updating at the same time. To place an order, user have to be logged in. The user cart is managed by user sessions. I will explain about this later in backend technology section.  

Once a user place an order, they will be redirected to order tracking page. This page shows the order id and other details about the order. Along with this web message, a SMS will be sent to customer cell number that they used while registering. At the same time, the restaurant will receive the notification about the new order. This communication between user and restaurant happens in realtime with Web Socket protocol.  

![pizza-n-go-homepage](/images/portfolioImages/pizzango/7.png#center)

From here, a restaurant can set an estimated time it will require to fullfill this order.  When a restarant set the time and click 'send SMS' button, the status of order will be changed from 'New' to 'In-Progress' and a user will receive text message about this change along with update on the web portal.

![pizza-n-go-homepage](/images/portfolioImages/pizzango/8.png#center)

At last, restaurant has an order ready, they can click 'ready to pickup' on their portal. This will move the order from 'In-Progress' to 'Completed' state and a use receive notification for order pick up on phone and web portal.

![pizza-n-go-homepage](/images/portfolioImages/pizzango/9.png#center)


## Frontend

The front of the application is build using simple HTML, CSS, client side JavaScript and EJS templating engine for JavaScript. All the pictures and details about the food you see on the page is stored in the database. When a user visit the page, the browser will send a request to server asking for required HTML, CSS and JavaScript files.  

There is a logic written these JavaScript files that make asynchronous request to server asking for the images for food and detail to show on the page. I have used a library called Axios to fetch the data.  

Now let's move to the backend or server side logic. This is where all the magic happens.










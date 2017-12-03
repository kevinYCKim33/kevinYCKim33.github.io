---
layout: post
title:      "Vendough -- like Venmo but worse"
date:       2017-12-03 03:00:08 -0500
permalink:  vendough_--_like_venmo_but_worse
---


https://github.com/kevinYCKim33/vendough-app

When it came time to build my Sinatra project 50 days ago, I initally wanted to create a Venmo clone and name it Vendough, but felt like I hadn't developed enough chops to pull it off after brainstorming up ways to set up my objects.  After making [BudgetChallenge](http://kevinyckim.com/budgetchallenge_-_sinatra_project_reflections) instead, and learning a ton of Rails since then, I decided to revisit Vendough for my Rails project. Even though I still didn't exactly know how the models would be set up, I felt like my googling abilities had grown considerably since then and I liked having this mix of excitement and anxiety of only having a hunch of how it's all gonna work out. My mindset was: just start piecing things together and hope for an epiphany.   

I felt this nagging feeling that the model relations would resemble a Doctor-Appointment-Patient relationship, but knew something was amiss.  A Sender-Transaction-Recipient relationship didn't work since a user can be a sender in one transaction and a recipient in another transaction. 

The roadblock really cleared once I watched an excellent Railscast on [Self-Referential Association](http://railscasts.com/episodes/163-self-referential-association), a fifteen minute code-along where this messiah set up a friend adding model.  Shortly after watching this video, I had an epiphany that just as friendship is a mutual two-way relationship among two Humans, a transaction is also a two-way mutual relationship between two Users.

There were so many challenges that came along from just trying to mirror Venmo's behavior, but of particular interest was trying to think like a hacker, and trying to be a step ahead of them. 

![a lot more code goes under the hood to mimic Venmo's elegant interface than I had thought.](https://i.imgur.com/zUyV4Fl.png)

For example, I realized based on the way I set up my database-model relations, a hacker could steal money by paying someone a negative amount. A hacker could also open up the Chrome console and then just change values of my Pay/Request buttons and put in data that'd corrupt my database. In stark contrast to my BudgetChallenge app, where the major security issue was blocking ways for hackers to view other people's challenges and logs, implementing a user-to-user relations where *money transactions* are involved meant I had to be extra careful and creative in how I validate data to be stored.   

![only if I knew jQuery, I wouldn't need that submit button](https://i.imgur.com/36uNH1g.png)

The more I tried to mimic Venmo's behavior exactly, the more I realized that I need jQuery in my life.  As I switch gears into JavaScript land starting tomorrow, hopefully I'll gain more chops and confidence to build up more functionalities into Vendough. 

Overall, I'm feeling proud that I'm continuing to pick projects that are just a bit outside of the curriculm and purposefully putting myself in these uncomfortable yet exciting position. We'll see what this last third of the curriculm lies ahead, and hopefully my mindset stays hungry and motivated.    



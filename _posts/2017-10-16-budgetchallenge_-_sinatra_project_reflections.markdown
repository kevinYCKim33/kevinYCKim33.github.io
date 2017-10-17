---
layout: post
title:      "BudgetChallenge - Sinatra Project Reflections"
date:       2017-10-17 01:54:19 +0000
permalink:  budgetchallenge_-_sinatra_project_reflections
---


Today marks the 2.5 monthiversary of enrolling in Flatiron, and it also coincides with my completion of the second of my five portfolio project...well pending review, but darn it, I feel it's a moment worth celebrating.  

Picking what I want for my project was a challenge in and of itself.  I didn't want to do a project where I was just copying and pasting from past labs and just changing the class and variable names. (i.e. Instead of Artist-Song-Genre class, I'll do Actor-Movie-Director class!")

At the same time though, I didn't want to do something where I was wondering "Is this even possible with how much I know so far?" and struggle through weeks and google my way out to the other end, only to find out the following sections in Rails/Javascript/React all explain very clearly and concisely the things I was struggling with.

I eventually settled on doing a finance-tracking app where you set a goal like "When I go to Las Vegas this weekend, I will spend no more than $300." and then log your spendings, and have a progress bar that fills up and goes red when you go over budget.  

Sounded simple enough, a user has many challenges, and a challenge has many spending logs.  

As I was implementing adding multiple on-going challenges, I realized that a log should be able to belong to multiple challenges. For example If you have two challenges like "Keep food budget this month to $500" and "Keep fast-food budget to $40 this month", a Chipotle burrito should belong to both of those challenges.  

Soon enough, I found myself dealing with a many-to-many challenge, and adding and dropping columns in my database and classes, and felt quite proud of just how much ActiveRecord and SQL I've learned in just a few weeks. 

This project also seemed like a good moment to refresh my knowledge of HTML/CSS that I learned on the 2nd week of this curriculm.  Bootstrap seemed like such a scary concept to me, but I'm glad I went with it, as I received some excellent Bootstrap advice from tech mentor Dakota that I wouldn't have gotten if I just went after the basic requirements for completing this project.

The capstone of the project was in figuring out a particular problem I had involving routing. When I created a log from my page that displayed all the logs I've made, I had it re-direct back to the "view logs" page, which was a totally fine behavior.  But, when I clicked on "Creat a new Log" from a challenge page, I wanted Sinatra to go back to the challenge page after creating the new log, and not the "view logs" page as that just didn't seem like a pleasant user experience.   

I explained this to my second tech mentor Kevin, and he explained to me that I was dealing with what was called "nested-routing" and that he had never seen this being attempted in a Sinatra app.  We worked through the problem together, and came up with a solution where we create two get routes that take you to the same erb file, where the challenge name was stored in a hidden field.  After filling out the log form, and hitting "Create a log", my post action would check to see if the hidden field storing challenge name was empty or not.  If the field was empty, it would redirect you back to the logs page. If it was filled, it would route you back to the challenge page using the challenge's slug.  It was a fun pairing moment, and he seemed legitimately excited as I was that we were able to figure that out in just over half an hour.  

My program isn't perfect at the moment.  I want to build a count-down component that lets you set how many days you want the challenge to last.  I also want to create a feature that keeps track of how many challenges you've completed or failed. Save for another time though.  

But overall, I'm happy with what I have. Instead of downloading some finance app, and being frustrated/confused by its interface and wishing it had certain features, I now know I have the ability to build my own finance app from scratch and build it as contrived as I want it to be for my own amusement--and that's empowering and exciting to me.     







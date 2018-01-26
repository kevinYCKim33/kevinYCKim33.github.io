---
layout: post
title:      "jQuerying up my Vendough"
date:       2018-01-26 04:58:34 +0000
permalink:  jquerying_up_my_vendough
---


So there goes up another project.  Since the start of this project, there was a too good to be true internship posting asking for recent bootcamp graduates, that made me revamp my whole LinkedIn and update my old resume, and a friend's wedding in Denver I had to attend.  I guess all I'm saying is that this project feels like it took forever to complete, but if you compact it down, it might have been a relatively brisk project.

The project started off disastrous enough however.  After thinking that I needed to revamp my generic Bootstrap navbar into this cool [sidebar](https://bootstrapious.com/p/bootstrap-sidebar), and thinking I got oh-so close to the point of picking out sharp color schemes, the navbar kept glitching out in displaying its content in an impossible to pin down random-seizure-like ways that was beyond the scope of googling/debugging.  

TLDR: git reset --hard after embarrasing amounts of hours poured in.

Then came stripping away all the cdn links and instead leveraging (I learned a lot of action verbs during my resume rewrite) Rails assets and gemming up my bootstrap and jquery to clean up my layout file.  

The biggest challenge turned out to be displaying my Vendough panels via AJAX.  

To the untrained programmer's eyes a Vendough transaction panel looks relatively simple.  It shows one user paid another user for something on some date. 

However, the panel is more dynamic than a genric blog post.  Whether the transaction says person A *charged* or *paid* person B involves careful querying from SQL, and whether or not to display the amount of the transaction depending on whether the logged in user is involved in the transaction adds another layer of logic.  Not to mention, whether or not to present the transaction amount in a red (-) sign or a green (+) sign to the logged in user.  

All these logic above I had solved in my previous build of Vendough, but adding AJAX into it, I realized that all my view helper methods were largely inaccessible.  In the end, I ended up rewriting most of my rails helper functions into Handlebars functions. On one hand, it made me gain great confidence in using Handlebars, but on the other hand, I felt somehow unclean knowing that this isn't very DRY having two sets of view helper methods that essentially do the same thing just because I wanted to incorporate AJAX.  I feel like the right thing to do at this point is to just get rid of a bunch of Rails code that Handlebars does, but somehow I can't seem to let go...

Overall, I feel like I flexed my Javascript and jQuery muscles enough on this project, sending get and post requests to my own personal API's and manipulating the returned JSON hashes in not-so-simple ways.  

Check out the [demo](https://vendough.herokuapp.com) and my [code](https://github.com/kevinYCKim33/vendough-app).

Have a good night everybody.  



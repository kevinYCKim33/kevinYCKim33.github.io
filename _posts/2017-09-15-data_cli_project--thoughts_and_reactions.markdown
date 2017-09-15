---
layout: post
title:  "Data CLI Project--Thoughts and Reactions"
date:   2017-09-11 20:21:58 -0400
---


The first actual project for Flatiron is just about under wraps...just as soon as I publish this blog, and have an instructor look over my code...so basically...done. Right?

There's always this hint of deflated feeling after a project is done and you see how little physical code there actually is left.  So many hours stuck on a line of code, only to find out there was an additional argument that needed to be thrown in.  

Overall, the project itself was pretty straight forward in hindsight.  Yet...

As a music aficionado, I had an idea of scraping a list of Rolling Stone's 100 Greatest Singers of All Time.  I opened up the console, and sure enough, some weird Javascript action was going on, where there was no nice clean <div> </div> list, and the list just seemed to load up more and more as you scrolled down a list, and sure enough I felt a bit over my head so I gave up on that dream.

Then I looked into Metacritic's albums out currently.  I felt sad because I did not recognize about 90% of artists on the list, and debated whehter I lost my touch with the youths of this generation; however, opening up the console, I was relieved to see a pretty reasonable and well ordered HTML file that I could Notogiri my way out of and decided to proceed.  

I then started off seeing Avi's overview video and sure enough, Avi being Avi, he cranked out a working version of the project in just over an hour, while pausing and talking several time to explain his process.  Ballpark estimate, I'd multiply that by like ten, then I would be done, was my initial thought.  (ha, my hubris)  

I liked his approach of not even worrying about the act of scraping first.  Paraphrasing, he said something like: "Write the code that you want to have."  and that sounded good in theory.  I followed his advice and had built myself a nice interface and objects that would work together. The list has many albums.  Every album has many songs...therefore, the list has many songs...in a sense.  

I set up a nice architecture, then went on to scrape the thing like Avi said.  When it came to time to scrape.  

I got this very unfortunate error.  

"403 Forbidden"

Which led to a rabbit hole of figuring out how servers work, how the internet REALLY works, and web security and cybercrimes, and many stack overflow forum suggestions that led astray every time.  

Discouraged and swallowing my pride, I decided to hunt down another website to work off of.  

Hence I realized I like classic films and decided to head into Rotten Tomatoes, and conveniently enough, they had a list of 100 best films of all time, based on critics aggregate scores.  And this time, I made sure to see scraping the website was possible.  

After printing out and looking over a student's worlds-best-restaurants-cli, I understood the architecture, but 
wasn't too thrilled with the way that the scrapers and objects were getting mixed around in the same method and class.  I eventually ended up basing my code off Student-Scraper project.  Where I have two scraping methods. One for scraping the index page, and two for scraping the individual movie page, a class that would convert hashes created from these scrapers into instance methods of movie objects and a CLI to bridge the scraping methods and the class instances together.  

Everything seemed to work like it should, and I ran the file, and sure enough...

I got the oddest error stating that openURI forbids me from going from https to http.  

Again this led me to another rabbit hole of understanding web security. (There is so little I know and life is only finite) and unfortunately, this fell on a weekend and I did not have access to my project mentor until Tuesday. 
I wasted a whole evening trying to debug it and decided to call it off and wait until Tuesday, where my mentor JJ earnestly helped me and assured me that this is a really odd error, and figured out how to debug the thing right before our 30 minutes was up.  

From then on, the project was basically done.  I refactored it some, but I got kind of disappointed at how similar it was to the Student Scraper Lab, and wondered if I should've done more.  Right now, I feel like I've got bigger fish to fry.  

My Github is getting beefier by the day and so far I'm very pleased with my progress, and glad to see just how much I've learned in the last six weeks.  









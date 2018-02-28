---
layout: post
title:      "Twogle: Final Project Reflections"
date:       2018-02-27 06:50:35 -0500
permalink:  twogle_final_project_reflections
---


So, my Twogle project is done, or to use a recently learned tech lingo, it is an MVP (minimum viable product).

<center>
	<img src="https://i.imgur.com/6Qt5NOA.png" alt="Twogle" style="width: 500px;"/><br />
	<footer>Twogle main page.</footer>
</center>

I scheduled the (hopefully) final assessment for tomorrow 2/28/2018 as that would mean I started learning coding full time on June 1st, started Flatiron on August 1st, and graduated from the program in exactly seven months.  In some ways I'm very excited, and in other ways, this feels like I'm about to watch the final episode of a show I've been binge-watching on Netflix.  There will be a deep chasm in my life, and I wouldn't know what to do with myself. 

Anyways, going back to the project.

It started with a couple days of not even coding.  I read a pretty long article on setting up a React app with a Rails server that was linked directly from the final project rubric.  It was a heavy read for sure,  and I ended up taking a walk about halfway through and deciding to start from the top again.  

I learned a lot about proxy servers and CORS disabling, and what <strike>exactly</strike> the gist of a Webpack Dev server is.

Afterwards, I watched a Luke video on how he did it,  and was somewhat disappointed that there was just an enable button for CORS in Rails.  (But I know so much about what CORS is now, and the value of a proxy server!)  

Attaining the API keys sounded simple enough, and it was for attaining NewsAPI's keys.  But Twitter's API keys?  I wanted to utilize the option they had where I enable Application only authentication, meaning no need to create a twitter login, and just be able to use the Twitter search API. 

I heard/reddited somewhere that recruiters and hiring managers don't want to make fake emails and fake passwords to log into an app, let alone create an authentic fake twitter account using authentic gmail and validating them via text messages and futuristic captchas.  

Sure enough, this was a pretty painful process of digging around githubs and extracting out my precious bearer tokens and then making sure to hide them in a .env file.  

Another obnoxious error was that Twitter somehow seemed to sense that my fetch requests were coming from the client-side, and rejected my requests to its API, so I ended up sending a fetch request to my Rails API and then having it send an AJAX request via Faraday to get my precious tweets in its JSON glory.  I'm still not sure if this was just some odd fetch syntax error or if it really was as theoretical as I'm making it out to be. 

Probably the hardest part of the project was getting the twitter widgets to load properly.  So twitter has this button on each of their tweets where it gives users options to embed the tweet directly onto a web page.  The formatting goes a little something like this.  

```
<blockquote class="twitter-tweet" data-lang="en">
<p lang="en" dir="ltr">Funny people are also more intelligent, according to new research 
<a href="https://t.co/VRWO5GWWL6">https://t.co/VRWO5GWWL6</a> 
<a href="https://twitter.com/hashtag/mentalhealth?src=hash&amp;ref_src=twsrc%5Etfw">#mentalhealth</a> <a href="https://t.co/QKH7cb6JU5">pic.twitter.com/QKH7cb6JU5</a></p>&mdash; World Economic Forum (@wef) <a href="https://twitter.com/wef/status/968796194561515520?ref_src=twsrc%5Etfw">February 28, 2018</a></blockquote>


<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
```
Just a big block of html, followed by a script tag that converts the html into the popular tweet form as we know it.  

<center>
  <img src="https://i.imgur.com/cK7bL6N.png" alt="Ellen" style="width: 500px;"/>
</center>

The only problem is that the script will only fire on tweets that were loaded onto the DOM at the time the script was present.  Tweets that I query up won't convert to its famous twitter format as the moment the tweets load, the script was already present, and already executed. 

Thus, that's when `ComponentDidMount()` came to the rescue. When the `<TweetList />` component loaded up, I executed this beautiful piece of code

```
  componentDidMount() {
    this.addTwitterScript()
  }
	
  addTwitterScript() {
    const script = document.createElement("script");
    script.src = "https://platform.twitter.com/widgets.js";
    script.async = true;
    script.charset="utf-8";
    document.body.appendChild(script);
  }
	
```

Above in English, reads: once all the tweets that you searched for render into the DOM, fire the `addTwitterScript()` that creates the twitter script tag, and appends it to the document body.  So from the just birthed Twitter Script's perspective, it'll see a bunch of tweets in its plain blocktext appearance and start to wave its magic wand at converting these blocktexts into legit tweets.  

*You may have noticed this yourself whenever you read an article with tweets embedded,  you see a flash of texts looking rather normal, and then all of a sudden, it converts into a Tweet.*

Aside from this, the rest were pretty normal React-Redux problems that the labs have been drilling me for.  Just pushing the state up, and vise versa, updating the store with Redux,  making as many components as possible into presentational components, thus making my code modular.  Pretty fun stuff, and a new way to go about coding things.  I read somewhere the React is the VC in MVC structure, and I can now see why. 

A personal win for me was my improvement in styling.  The curriculum never emphasized styling, and I took it upon myself to continously improve at it.  Thanks to some wonderful site called Flexboxfroggy, my columns and organizing divs didn't seem as scary.  

So the assessment is in less than twelve hours away.  I hope to create a medium post soon.  And now I am wondering if all this writing that's kind of haphazardly written writing will show up on a Google search in the not too distant future and embarrass me in the future.  I hope not.  I hope to create some legit Medium site soon too.  But who knows.  

Well it's been fun.  Have a good night.  

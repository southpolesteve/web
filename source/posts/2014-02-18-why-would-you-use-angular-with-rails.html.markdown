---
title: Why would you use Angular with Rails?
date: 2014-02-18 04:58 UTC
tags: angular, rails
---

A few weeks ago, someone posted to our [local Ruby meetup group](https://groups.google.com/forum/#!topic/mad-railers/KVA6cbgm1oI) with the following question:

> Recently I have seen a ton of information tutorials, blog posts etc. about combining AngularJS with rails. But thus far I have not seen a compelling reason to follow the trend. Is this nothing more than hype over a new framework or does angular offer significant improvements over the rails standard templates? As an example in tutorials I see a lot of angular repeaters replacing resource.each statements but I don't see this kind of thing providing any tangible benefits.

I ended up sending a lengthy reply which I have decided to edit a bit and repost here...

First off, to use a bad analogy, your question is a bit like asking "Why should I use a motorcycle?"

We'll where are you trying to go? What are you trying to do? If your trying to get to Australia, a boat might be a better option. Or a plane would get you there much faster but cost more money. Rails and Angular are both tools and it is important to understand what you want to do so you can decide which tool is right for the job.

Rails is a server side MVC framework. It provides all the tools you need to create a web app. It delivers HTML to the browser but can also power APIs. Out of the box it is primarily used for sever rendered websites.

Angular is a client side javascript framework. It provides all the tools necessary to create a javascript app that runs in the browser and talks to an API. It can be delivered to the browser as a static JS file

Let me try and answer your question by breaking it down into a bunch of smaller ones:

###### Why build a client side javascript app?

A lot of reasons. Speed is one. Only communicating via an API can be much faster. It also makes delivering your app to the browser much simpler since it is just a static HTML/JS/CSS file. Depending on the app, you may also be able to offload certain tasks to the browser which saves server resources.

For me, the main advantage has come from the mentality of divorcing the backend completely from the front end. This provides better separation of concerns. Both parts can be worked on independently as long as the API remains the same. This forces me to write better code. If your front end is a JS app, you can't call directly to the database like you could in a rails app.

###### Why use a javascript framework?

Frameworks allow you to write apps quickly. Just like its easier to write a web app in Ruby using Rails than completely from scratch. Of course there are draw backs to frameworks too. When you try do something the framework isn't designed for things can get ugly quick. This point is also endlessly debated by programmers everywhere.

###### Why use Rails as a backend API?

Check out this [blog post by Alex MacCaw](http://blog.alexmaccaw.com/rails-is-just-and-api-and-that-s-ok) that does a pretty good job of explaining Rails as a backend. Turns out Rails is pretty good at making APIs. Your views are just JSON or XML responses instead of HTML.

###### Why use Rails to package a javascript app?

Because the Rails asset pipeline is pretty decent at building javascript. It will help you organize, concatenate and minify your javascript. There are also ton of other tools out there that perform these tasks in various languages. Check out grunt.js for a javascript based alternative.

###### Why use Angular as a javascript framework?

I'll preface this by saying I'm a self-admitted [Ember.js](http://emberjs.com/) fan boy :)

Angular is designed to make building javascript apps easier. It provides man common tools so you don't have to write them yourself (just like Rails provides ActiveRecord models). It's worth going through some tutorials to see how Angular's features work for you.

For me, one of the biggest features of a JS framework like angular is data binding. This means that when your javascript model gets updated, those change propagate to the UI. Imagine a web app like Rdio or Spotify. When you click "play" on a track all kinds of stuff on the page changes. The song title changes, the icons change, the play bar starts moving, the album art changes. You can imagine that keeping track of what needs updating or already has updated can get messy. Hence the phrase "spaghetti" code. Angular makes this much simpler by keeping track of what elements depend on what data and updating everything automatically.

###### Why use Angular and Rails together?

For all the reasons above! Rails is great for building sever APIs. Angular is great for building client side javascript apps. They are both great at what they do so in combination they can make great apps.

Personally, I think Rails and Ember are much better matched. They have similar philosophies about how apps should be built that make them work well together. In fact one of the Ember core team members is also a Rails core team member. But that is just my opinion. I've used angular too and think it is a great tool.
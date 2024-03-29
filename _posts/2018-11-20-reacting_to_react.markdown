---
layout: post
title:      "Reacting to React"
date:       2018-11-21 03:00:48 +0000
permalink:  reacting_to_react
---


It's here. After several months of long days and hard work, I finally finished my final project for Flatiron School's Full Stack Web Developer program. 

This was by far the most difficult project that I did during this program for many reasons. Every other project took me between 3-4 days of work and came out pretty much how I had envisioned them. This project was not like that, this took at least 7 days, averaging about 10 hours each day. There were several times I had to back up and rework how I wanted this app to function and how I was going to accomplish that. I read more articles to help me through certain issues than I can even keep track of, but you know what? I did it. 

This project was a React App with a Rails API. All of my previous projects were very much form-based where you create some sort of object with a form and then you can associate them to other objects or users in different ways. If I had stayed on that same course, I probably could have had this project done sooner than I did, but I wanted to branch out, try something new and try to add a bit more logic to what my app was doing. That's why I decided to create a flashcard/quiz app. 

Cerebral is a game where you can find quizzes that other users have made, go through the questions and see how many you can get right. At the end it will tell you how many you got correct and also keeps score of the deck's overall high score and shows what users got the top 3 scores. 

A few new things:
1. Building an API
*       Whereas I feel pretty comfortable in the Rails world, I had never written my own API. It was a bit different, but with Rails' nifty --api flag, it is actually pretty easy and quick to do. I just built out my models with their associations, logic, routes and serializers and was good to go in no time. 


2. Postgres Database
*      Before this project I had always used Rails built in SQLite3 database. I decided to use Postgres this time for a few reasons. First was just to get the exposure, but also because I plan to host Cerebral on Heroku, and to do that you need to have a Postgres database. This was also pretty easy to get going, I just found a quick tutorial and was good to go. 

3. React
*      Since this module was on the React framework, I of course needed to use it in this project. Using React to this scale was a big learning curve. 

*A bit more on the React learning curve...*
Throughout my React coursework we very quickly covered a lot of topics, but I'm not sure if they fully prepared me for what I was about to get into. I ran into a lot of issues with nested forms, promises, asynchronous functions and figuring out how much to store in my local state vs my redux store. 

You can read more about my journey with a dynamic nested form here. 

As great as asynchronous functions can be, they can also be quite tricky when you actually need things to happen in a certain order. This is when `.then()` becomes quick useful. I'm not certain if what I did was the prettiest way to go about it, but `.then()` allowed me to make a post request back to my API to create a deck (my parent object) first and *then* create my cards (child objects) that belong to that deck. Otherwise, when I just tried calling two asynchronous functions one after the other without chaining them, the cards didn't have proper deck_id because that deck hadn't been made yet. 

I initially tried not to store too much information in my store, but quickly realized that sometimes it just made sense to store something there, even if I didn't need it in several different places in app. This helped me to not have to keep creating local states that got passed down through several levels of child components. When in doubt, redux.

This is a basic overview of how my final project went and I plan on doing a few specific write-ups on some of the issues I faced and how I solved them, so keep an eye out for some of those. 


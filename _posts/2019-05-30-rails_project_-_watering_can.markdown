---
layout: post
title:      "Rails Project - Watering Can"
date:       2019-05-30 17:02:02 +0000
permalink:  rails_project_-_watering_can
---


I started out immediately knowing what I wanted my project to be on - an app that waters your plants while you are on vacation. I have a ton of plants and honestly just watering them everyday is annoying but I love the way they look. The idea is a customer can go to the store and buy a hypothetical drone-type machine called a "watering can". They go online and register thier watering can with its product number. Now the user can add plants to it (like for example if I have a plant in my bedroom, needs 2oz water every 3 days). When the user goes on vacation, they select the amount of days they'll be away and the machine will make sure thier plants get the specific water oz they need. The machine can hypothetically refill itself (from a person's sink or something) and continue to water these plants according to thier needs. 

This was the hardest project I've done in a long time. Working with dates it's hard to test the app because you have to wait a whole day to see if it "watered" the plants or not. I thought the Google oauth was going to be the hardest part but it ended up being the easiest. What I spent the most time on was a User method #water_everyday. This is pretty much the backbone of the app - it decides whether the plants need water and if so, it waters them. 

I spent a long time thinking about how I can have this app kind of run in the background and update things while the user isn't on the page or even logged in. I looked around online and found a [gem called "whenever"](https://github.com/javan/whenever). This gem can run rake tasks whenever you need it to - I set it so everyday at 9am it runs User.water_everyday. This took a ton of trial and error, as I'm not too familiar with rake tasks and cron at all. Overall I'm really happy with everything I learned by doing this type of project and maybe in the future I can actually make something similar and won't have to worry about watering my plants. 

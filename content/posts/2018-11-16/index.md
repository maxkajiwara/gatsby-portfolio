---
title: "Rate My DIY: Week 2"
cover: "http://3.bp.blogspot.com/-59x2vBBUerg/UBX11I7Vi3I/AAAAAAAABeQ/NTRZT_FngGE/s1600/51FQq0NRFVL.jpeg"
author: "maxkajiwara"
date: "2018-11-09"
category: "labs"
tags:
    - sprint
---
# Individual Accomplishments this Week

https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/graphs/contributors

### Tuesday
I built the project routes and model using my pseudocode and notes for reference.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/41

### Wednesday
I built the post routes and model using my pseudocode and notes for reference. I also updated the migrations.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/41

I pair programmed with Tristen to set up authorization middleware. It works on Postman when supplied a valid cookie and user_id.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/47

I started working on the project page component.

### Thursday
I got pulled away from working on the frontend and spent most of the day working on authentication instead. I got my whiteboard done around 9pm and then continued working on authentication, finding one important bug but not solving the issue of cookies not reaching the backend from the browser. I then stayed up til 5am getting the project page set up for this week's mvp objective.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/57

### Friday
I got straight to debugging and deployment of our recent changes. I didn't stop working on hotfixes to the server until lunch time. Our two third party API's tests are functional and projects from the database are able to display on the frontend.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/58
+ a bunch of hotfixes having to do with environment variables, broken packages, and netlify redirects

# Tasks Pulled

## Front End
- Build project page
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/57
 - https://trello.com/c/lEeZIoks

## Back End
- Build project routes and model
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/41
 - https://trello.com/c/IdrbQ98q


- Build post routes and model
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/43
 - https://trello.com/c/2hXRQXsx


- Pair programming: Set up authorization middleware
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/47
 - https://trello.com/c/mFgKoUjQ

 - Pair programming: Set up authorization middleware
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/47
 - https://trello.com/c/mFgKoUjQ


## Hotfixes
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/59
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/60
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/61
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/62
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/63

# Detailed Analysis
Netlify wasn't loading pages other than our homepage. It turns out that you need to add a `redirects` rule in netlify.toml to handle routing with react-router.
![](https://i.imgur.com/mwPTgBI.png)


I found the role on https://www.netlify.com/docs/netlify-toml-reference/.
![](https://i.imgur.com/mPqVguI.png)


Our /project/:id page works now! As do our other pages.
![](https://i.imgur.com/OHaHdlt.png)

# Milestone Reflections
Work in progress.
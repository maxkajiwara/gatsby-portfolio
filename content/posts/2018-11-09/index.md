---
title: "Rate My DIY: Week 1"
cover: "https://www.dailydot.com/wp-content/uploads/97b/cc/122cd4f6677bc912-2048x1024.jpg"
author: "maxkajiwara"
date: "2018-11-09"
category: "labs"
tags:
    - sprint
---
# Individual Accomplishments this Week

https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/graphs/contributors

### Monday
We decided on a tech stack.
https://docs.google.com/document/d/1zVRXTBC7DHDebiPs5M-kJ44FJ6rH9eBCXKzHOcxHcYA/edit?usp=sharing

I got our project started by building a boilerplate setup for the frontend and backend, including example files.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/commit/33faed5d5065e74f6805d025178a2d875017b5a3

I also started learning how to use MS SQL Server Express.

### Tuesday
I designed the component file structure.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/commit/16ee8a53d5958f767c5167568008a6fb58bc6b31

MS SQL Server Express had failed to install correctly and could not be uninstalled. It took a while to fix this.
https://social.technet.microsoft.com/wiki/contents/articles/31786.sql-server-not-starting-after-fresh-installation.aspx

I got familiar with using SSMS and Azure Data Studio to manage the database.

### Wednesday
I set up table migrations for the database.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/6
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/9
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/14

I eventually got the migrations working with my local database. One of my dumber, time-consuming bugs was caused by migrating the tables in the wrong order.

After getting migrations working, I started learning how to use Azure.

### Thursday
I got an MS SQL Server database set up on Microsoft Azure and configured the firewall. It took a while to get things working. I've been through hundreds of docs, guides, and stackoverflow pages at this point. Once it was working, I tested knex migrations from my computer to the database.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/25

I spent way too many hours trying to get our backend deployed to Azure web apps. I finally gave up and deployed to Heroku. The Heroku backend uses a dynamic ip from aws to make queries. I tried some addons that were supposed to give it a static ip but they didn't work. Out of desperation, I set the azure database firewall to accept connections from the entire ip spectrum. I'm not satisfied with this solution.

I also spent some time sketching out most of our routes and models with pseudocode. All that's left is registration and search.

# Tasks Pulled

- Inital project setup
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/commit/33faed5d5065e74f6805d025178a2d875017b5a3
 - https://trello.com/c/VXlvIf84
This wasn't a pull request but I assume it counts as frontend and backend.

## Front End
- Component file structure
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/commit/16ee8a53d5958f767c5167568008a6fb58bc6b31
 - Forgot to make a trello card for this

## Back End
- Build database schemas
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/6
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/9
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/14
 - https://trello.com/c/h7Hjnc9W


- Set up MSSQL database on Azure
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/25
 - https://trello.com/c/7tdti34J


- Deploy backend on Heroku and connect to Azure
 - https://ratemydiy.herokuapp.com/api/projects/1
 - https://trello.com/c/2BOBvPy9


# Detailed Analysis
When deploying the backend to Heroku, I ran into an issue with Heroku only looking for package.json in the root directory of the repo. After some googling, I found a buildpack to solve the problem.
![](https://i.imgur.com/cdLOtd4.png)
https://github.com/timanovsky/subdir-heroku-buildpack


I installed this, followed the instructions, and set the project path to `server`.
![](https://i.imgur.com/QSatD6c.png)

![](https://i.imgur.com/kshw6E4.png)

The backend successfully deployed. Hooray!

![](https://i.imgur.com/fRphdhO.png)

# Milestone Reflections
Oh boy. I shouldn't have tried to use a new database management system.

When deciding on our tech stack, I encouraged the team to try something new that we'll likely work with on future jobs. I don't mind spending a couple days learning a new tool, and I eventually got everything deployed and connected, but the team had become very impatient and people were unwilling to install SQL Server locally for testing.

I think I did a good job setting up the project skeleton to get us started. Even though I haven't had many opportunities to work on actual code for the frontend and backend, I've spent a lot of time helping my teammates by planning out features, explaining expected functionality, teaching them how to do things in react or express, and fixing their code. A lot of this doesn't show up in the pull requests, but it probably accounted for 20-30% of my time and effort this past week.

Getting Auth0 set up to interact with our database has been a pain. We've been struggling to create a setup where a user is recognized and verified by their userid for various endpoints on the backend. Tristen has been doing a great job figuring this out and I think we're close to having it working properly.

I'm in disagreement with the rest of my team about whether or not we should have a dev branch. Everyone else wants to make pull requests directly to master for new features. I think that pushing directly to deployment is a bad idea and it'd be safer to push from the dev branch periodically after testing the interactions of recently added features. I'd even advocate for staging branches so we can test a snapshot and still be able to push new features to dev.
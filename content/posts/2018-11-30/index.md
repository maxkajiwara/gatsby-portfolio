---
title: "Rate My DIY: Week 3"
cover: "https://pbs.twimg.com/media/DcvXNtiXcAAL2tx.jpg"
author: "maxkajiwara"
date: "2018-11-30"
category: "labs"
tags:
    - sprint
---
# Individual Accomplishments this Week

https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/graphs/contributors

### Monday
I rebuilt the project page and added components, actions, and reducers for adding, editing, and deleting projects. I also built a confirmation modal to confirm certain actions.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/71

### Tuesday
I worked on the review modal and its related actions, reducers, routes, and model.
No PR.

### Wednesday
I continued working on the review modal and its related actions, reducers, routes, and model.
No PR again. I know I'm supposed to break things up but nothing was remotely functional yet.

### Thursday
Here it is, the giant PR for adding and reviewing reviews.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/92

### Friday
Auth was broken again. I fixed it and also got rid of a ton of react warnings from other people's contributions.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/101

# Tasks Pulled

## Front End & Back End
- Projects: create, update, & delete
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/71
 - https://trello.com/c/RnirNTOq
- Reviews: create & view
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/92
 - https://trello.com/c/UNoj3WYm
- Bugfixes
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/101
 - https://trello.com/c/v3T658Xt

- Landing Page: featured projects
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/68
 - https://trello.com/c/LuRXvg5k

Also a ton of other pair programming but I forgot to track the trello cards

# Detailed Analysis
Coming soon

# Milestone Reflections
I've been working on this project for over 80 hours this week and it still feels like it hasn't been enough. So many features are still incomplete or broken. I'm having to spend a lot of my time building and fixing things for other people's features as well. I don't mind helping them and I'm glad to get things working but I can't spend the time I need to get my own tasks done.

Last night I figured out sql transactions but knex -> mssql -> sql server doesn't support them. Early this morning I set up a Heroku Postgres server and they work fine with that.

There were many other major challenges I overcame this week but I'm struggling to recall them at the moment; I'm still working hard on features and everything else like watching principles for success or writing this journal feels like a distraction from getting MVP done. Every moment documenting changes or issues is a moment not building or debugging. Everyone is feeling this pressure. Our pull requests barely get glanced over most of the time, broken code gets merged constantly because everyone's impatient to see their changes deployed and we just don't have the time to do thorough tests.

##Features
Everything is likely to be broken depending on the state of the master branch. My bugfixes haven't been merged yet. There's so much more I know I can fix, given more time. Nearly any fault with the user experience is something I'm already aware of. I'll fix it myself if nobody else will.

 - Landing Page https://ratemydiy.netlify.com/
 - Search Page https://ratemydiy.netlify.com/search
 - Project List https://ratemydiy.netlify.com/projectlist
 - Add Project https://ratemydiy.netlify.com/newproject
 - View/Edit/Delete Project https://ratemydiy.netlify.com/project/:project_id
 - Review List https://ratemydiy.netlify.com/reviewlist
 - Review Modal - Go to project page and click "Review Project"
 - Settings https://ratemydiy.netlify.com/settings
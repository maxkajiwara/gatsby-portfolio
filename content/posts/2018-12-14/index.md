---
title: "Rate My DIY: Week 5"
cover: "http://contemporary-home-computing.org/still-there/fullsize/geocities/uc.png"
author: "maxkajiwara"
date: "2018-12-014"
category: "labs"
tags:
    - sprint
---
# Individual Accomplishments this Week

https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/graphs/contributors

### Monday
I got like functionality set up on the backend.
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/122


### Tuesday
I did a big rework of the project page and project and post actions.
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/123

### Wednesday
I did a big rework of the review modal and review actions and implemented like functionality on the frontend.
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/126

I also submitted a small change to reset the scroll height when visiting the project page any way other than via back/forward.
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/129

### Thursday
I reworked and restyled project cards, built review cards, set up working like/dislike buttons on the review modal, and did a bunch of other styling and tweaks around the site.
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/134
- https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/141

I also set up empty cards to display while cards are loading.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/136

I added category selection to the new project page and displayed them on the project page. I also restyled the new project page.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/142

### Friday
I review some pull requests, did some last minute tweaking before the demo, and wrote this journal.

# Tasks Pulled

## Front End
- Update projectReducer.reviews when user changes a card's like value
- Various ux improvements
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/141
 - https://trello.com/c/OtRBmuFV

- Add category selection to the new project page and displayed them on the project page.
- Update new project page styling
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/142
 - https://trello.com/c/QvgGz9EE

## Back End
- Add like functionality to backend. Updates the helpfulness stat of a review and its author whenever a like is added/changed/removed.
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/122
 - https://trello.com/c/our4NlEc

 - Display empty cards when loading projects
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/136

## Front End & Backend
- Rework many actions to use callback functions when updating components. This was previously managed awkwardly via the redux store
- Update ProjectPage, NewProject, EditProject, Post, NewPost, and EditPost to use these new actions
- Clean up the old actions, store, and reducers
- Change some `<a>` tags to unstyled buttons and disable various project or post related buttons during certain actions
- Fix a number of minor bugs
- Add rating validation to EditReview route
- Various ui tweaks
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/123
 - https://trello.com/c/C9qyX8LD


- Refactor the review modal with updated actions and props
- Update modal to close or trigger confirmation modal when user clicks outside of it
- Disable action buttons while waiting for actions to complete
- Fix some minor bugs
- Add like functionality to the review modal
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/126
 - https://trello.com/c/ZNohy50N

- Restyled project cards and the featured projects container
- Built and styled review cards
- Built review page
- Implement working like/dislike buttons
- Added and updated a bunch of actions and queries
- Added a hopefully obvious dropdown arrow
- Made a bunch of other miscellaneous tweaks and fixes
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/134
 - https://trello.com/c/EZYefEAP
 - https://trello.com/c/F00AKg82
 


# Detailed Analysis
Work in progress

# Milestone Reflections

I feel exhausted. I worked really hard this week on finishing up most of the missing or incomplete features and functionality. Once most of these changes were working and deployed I was able to finally move on to styling the fronted. I feel like I made some major contributions to improving the aesthetics and user experience for the site even in the relatively short amount of time I've spent on working on it.

That being said, I'm still fairly dissatisfied with various unstyled elements and inconsistent visual design around the site. Many of the components are still bare bones structures with tiny input fields, radio buttons, and cramped text strings. There are still many user actions that aren't accounted for, such as trying to create or review a project without being logged in. Users who signed up with gmail still can't change their profile settings and they have the potential to run into unique name constraint errors. You can still get stuck in limbo between auth0 and account creation on the backend. Search still doesn't handle categories, reviews, or users. There is no request rate limiting on the backend and prop types aren't enforced.

I've also continued to meet resistance when suggesting user experience improvements to my teammates. Invariably I end up adding tasks to my personal list of "nobody else will do it so I'll have to do it myself. Eventually." For example, the dropdown menu and its links were ridiculously tiny and hard to click, and even though I brought it up often, nobody thought it was a problem. I fixed that and many other issues this week, but there are still many, many more, such as lack of visual feedback during image uploads ("Is the site working? Did I lose connection? Should I try again?"). At first I felt like I was just annoying my teammates but now I'm convinced that these are just the kind of things that definitely belong in a polished project.



I'm heading back home to visit my family in Hawaii for a couple weeks but I intend to come back refreshed and spend the rest of the break working on improving the project.

### Tech Stack
From top to bottom, we have a react redux frontend with auth0 handling authentication, a node express backend using knex to build queries, a heroku postgres database, and aws s3 for image hosting.

### The Application
You can share your own diy projects, rate and review others' projects, and even provide feedback for reviews themselves in the form of likes or dislikes. You can also search for projects by name, description, or maker.

### Media licenses
Work in progress. There are still a bunch of hotlinks and uncited images on the site.

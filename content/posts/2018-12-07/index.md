---
title: "Rate My DIY: Week 4"
cover: "https://wfa.life/wp-content/uploads/2016/02/asleep-at-desk-computer-e1455839264842.jpg"
author: "maxkajiwara"
date: "2018-12-07"
category: "labs"
tags:
    - sprint
---
# Individual Accomplishments this Week

https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/graphs/contributors

### Monday
I updated the rest of the project actions to handle categories. Selecting categories still isn't implemented on the frontend.
I also updated addReview to modify average ratings for the project being reviewed and its
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/102

I also fixed some of our authentication issues with logging in or out. These changes were added to a pull request I'd been helping Tristen with.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/103

### Tuesday
I added edit and delete functionality to the review modal. These actions also update average ratings in the database.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/111

### Wednesday
Today was mostly helping plan, build, or debug other people's features. My one pull request had to do with fixing the display order of featured categories by updating the orderBy() behavior for postgres. The query behaved differently on mssql.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/112

### Thursday
I fixed a race condition between updating/deleting a review and refreshing the page for that project. I'd already labled the earlier hacky solution an unideal and temporary. The new behavior is much more elegant and reliable.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/119

I worked with David to fix another race condition between our loggedIn action and getting projects or reviews by user_id. I finally figured out the correct way to chain actions to sovle this problem. Applying this elsewhere should uncomplicate a bunch of other behaviors around the site.
https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/121

I also helped Mike find the problem that preventing updating projects. The frontend wasn't sending a category array.
https://trello.com/c/ytvuIdeN/164-cant-submit-changes-to-a-project

### Friday
I'm finishing up implementing likes. I have a lot of other issues and features to get to today. See our Trello for reference.

# Tasks Pulled

## Front End
- Fix behavior for editing or deleting a review
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/119
 - https://trello.com/c/SNTaVp29

- Solve issue with fetches not being asychronous on ProjectList and Reviewlist
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/121
 - https://trello.com/c/pP4GsJDV


## Back End
- Get, add, & update project categories; update average ratings when adding a review
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/102
 - https://trello.com/c/1f3Sl4jM
 - https://trello.com/c/9jKZ0HCz

-  Fix issue with orderBy() behavior on postgres database
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/112
 - https://trello.com/c/gCXoXmCS


## Front End & Backend
- Let users pick a username from auth0 and fix the logout issue
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/103
 - https://trello.com/c/r4J3Q4RA

- Add edit & delete functionality to the review modal
 - https://github.com/Lambda-School-Labs/Labs8-RateMyDIY/pull/111
 - 


# Detailed Analysis
Todo: take screenshots of my old action/reducer/props setup for chaining actions and the new callback functions replacing it.

I'm kind of embarrassed about this one. Not knowing how to chain actions asychronously had been a recurring issue since we started this project. I also couldn't figure out how to update a parent component's state depending on the outcome of an action. I've been using the redux store as a workaround to handle a lot of related functionality.

Yesterday I was helping David with an issue with the My Projects and My Reviews pages. If you navigated to one of the pages from somewhere else on the site, they worked fine. However, if you refreshed the page or navigated to it directly as you would via the address bar or an external link, the projects or reviews would fail to be fetched.

I recognized this as an issue with overlapping actions: the fetch action in the componentDidMount() lifecycle was not waiting for the loggedIn action to return a userInfo object. Because it wasn't waiting, it had no user_id to send to the backend for the database query. You didn't run into this issue if the redux store was already holding onto userInfo from a previous page.

At first I started setting up a clunky action chain like the one I'd used on the projects page, and as usual I couldn't help but experience the nagging feeling I get when something seems more complicated or awkward than it should be. The breakthrough occured when I considered reworking the loggedIn action to handle a number of different action chains upon fetching the userInfo. All the sudden I realized that I could send the next action and its arguments from the component as a callback function.

This was one of those moments where a concept "clicked" and immediately became obvious in hindsight. I can uncomplicate a lot of my previous code with this new knowledge. I'm looking forward to applying it to the rest of the site moving forward.

# Milestone Reflections
I'm still laser focused on improving our site's structure and behavior. This involves working on a lot of missing or broken features. I haven't touched any css all week but I have provided occasional feedback to my teammates. There's still so much to be done improving the user experience flow before I can even think about colors, sizes, and shapes.

My teammates get annoyed by a lot of my feedback concerning awkward gaps, unintuitive behavior, and unresponsive actions in the user experience all around the site. Once they've applied a suggested change they do agree it was a significant improvement. For example: providing feedback to a user that the site is doing something after clicking a button. Previously, selecting an image would not change the page at all. Neither would clicking upload, until the upload finished. In the meantime the user had no idea if anything was working at all.

I'm doing my best to ignore what's easier for the developers and look at the site strictly from a user perspective. There are a great number of changes I intend to implement once I've gotten through more of my growing list of issues on Trello. If not by next week, I know I'll spend a great deal of time updating the look and feel of the site before our next encounter with Labs.
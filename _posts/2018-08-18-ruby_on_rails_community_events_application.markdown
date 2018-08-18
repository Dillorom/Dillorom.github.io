---
layout: post
title:      "Ruby on Rails community events application"
date:       2018-08-18 02:35:46 -0400
permalink:  ruby_on_rails_community_events_application
---

For my [Ruby on Rails project](https://github.com/Dillorom/samp-rails-project) I created a local area parents’ guide for events, where users can see upcoming events, and if needed go back to see past events. Every event contains information about time, location and description of the event, and optionally link to the source of the information. Any user can submit an event. In the homepage, events are sorted as today’s events, upcoming events and past events, where I used class level scope methods. Users can sign up either by a traditional sign up form or sign up/log in through Facebook. Logged in users can see other user’s profile and their email addresses. Users can edit or delete their profiles, events and comments. Admin user can edit/delete any user account, event or comment. Users can leave comment on event pages and be able to edit or delete their comments. Comments are shown below the event information on the event page. When a comment is edited, it opens in a nested, but a separate page of `“events/:id/comments/:id”`. Ideally, comments could be edited or deleted on the same event page. But my research showed that is possible using JQuery, and I am not in JQuery section in the curriculum, so “events/:id/comments/:id” suffice for now. 

One may think my table association structure would be `users has_many events, events has_many comments`. And I think this structure would have been much easier to work. Since the Rails project requirements asks for bidirectional join table, I decided to structure my associations as `events has_many comments, users has_many comments, events has_many users through comments`, and `users have_many events through comments`. It took a lot of thinking in an opposite direction, but it was possible to do it. Additionally, once I deploy the application, I thought having users submit an event, but having only admin post events that are approved would be easier to keep the application clean from unwanted events. 

I nested comments under events. However, it is hardly useful because comments are posted below the event in the same page. One can only see the nested address while editing a comment. 
I set up Omniauth Facebook after setting up conventional sign up/login forms. It was a little difficult to combine both ways since most tutorials on Omniauth explain setting up Omniauth only. I also learned it might have been better to start with setting up Omniauth first, and then building models. I had to go back and add more columns for my user table to suit Omniauth requirements. 

Rails project took longer than I expected. I struggled a lot, first in associations, then in setting up Omniauth, and lastly in scope methods that sorted events by time. I faced several uninvited problems such as not being able to bypass secure connection requirements on the browser, because I forgot to run the server on `“thin”`, accidentally updating my Virtual Machine (VM) and losing internet connection on my VM, therefore having to re-install the Virtual Box. The experience itself felt like diving in the ocean and looking for gems I needed to build the application. I probably read 10 articles and tutorials on average and another 10 more articles on StackOverflow on every obstacle I faced. It made me feel confident in searching for narrowly-scoped questions and sorting out what platforms I would most likely find a potential answer. 
 



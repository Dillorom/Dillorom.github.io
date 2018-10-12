---
layout: post
title:      "Hijacking with AJAX: my Rails and JS portfolio project"
date:       2018-10-12 17:23:02 -0400
permalink:  hijacking_with_ajax_my_rails_and_js_portfolio_project
---

From the second part of August, I started learning about JavaScript (JS), a new language. Coming from Ruby language, my first reaction was that not everything was well defined in JavaScript. Adjusting to a new language rules and feels took a little more time to absorb than I have expected. However, I realized that most of the websites’ front-end features that I appreciate as a user, such as loading information on a single page, checking user name availability or password acceptance while I am typing in the form when signing up, were made available thanks to JavaScript. 

During my study period I tried to learn as much as possible about plain JavaScript, so that I understood the fundamentals of the language. I slowly incorporated JS libraries, such as JQuery once I was sure I understood the basics. I particularly spent longer hours in making sure I understoond JS Scope and Closures, application request and response cycle and importance of distinguishing data types in using AJAX.  In my Rails and JS project, I worked on top of my previous Rails project, which is events application for parents to view and post kid friendly events in Seattle area, adding front-end features to my application on a new Github branch. 

My application has nested routes, where comments and rsvps are nested under an event. In my previous Rails project, I have built individual pages for `events/:id/comments/new`  and ` index` and `events/:id/rsvps/new` and `index`. In Rails and JS project, I worked on rendering `comments/new` and `rsvp/new` and `index `pages in a single page -- `event/show` page using APIs. I also added next and previous event functions that fetch the data from the next and previous event pages using AJAX. 

Since I created multiple AJAX requests, I had to regulate event listeners’ flow by creating ` attachListeners` functions on ` turoblinks: load`. When you use low level `.AJAX get `or ` post` request, the response object is automatically converted into a `JSON` object. But for some reason, I was not able to get `JSON` object, so I had to specify the format of my response object manually like this `url: this.href + ".json"` in my request. I also used **ActiveRecord Serialization**, because I needed to set up association between my` comment` and `user`, `rsvp` and `user` models to get `user.username` property. In my `post AJAX` request, I created a `new Comment` object using a constructor method and defining it with a set of attributes. I also assigned `renderComment` method to the `Comment` object’s prototype to save some memory space. 
 
I believe people have different learning styles. While learning JS and working on my project, I switched between the Flatiron Curriculum, Linda.com and Udemy courses, and a bunch of books that I borrowed from my local library. I particularly found “Brain friendly guide-Head First” series on JavaScript, Rails, Ajax. 

My project repository is available[ here](https://github.com/Dillorom/seattle-kids-events/tree/rails-js). After passing my project assessment I plant to merge my master branch, where my Rails project lies, and Rails and JS project, and to deploy the application on Heroku. My Rails project is available [here](https://seattlekidsevents.herokuapp.com/ ).

![](https://prodimage.images-bn.com/pimages/9780596527747_p0_v1_s600x595.jpg)
![](https://covers.oreillystatic.com/images/9780596515782/lrg.jpg)
![](https://covers.oreillystatic.com/images/9780596515775/lrg.jpg)






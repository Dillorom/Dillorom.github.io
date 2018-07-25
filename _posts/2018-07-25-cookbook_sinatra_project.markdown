---
layout: post
title:      "Cookbook Sinatra Project"
date:       2018-07-25 16:23:41 -0400
permalink:  cookbook_sinatra_project
---

It seems like it took forever to get here, but finally, I am here to start my blogpost after finishing my Sinatra project!
ActiveRecord magic gave me a sense that it will all going to be magical from now on. But I struggled more in Sinatra than I did in CLI block while working on the labs. I worked hard on connecting routes with proper views following the CRUD. Understanding and getting used to use slugs and flash messages in right places also took some time. Most importantly, trying to make sense of association took a lot of time.

I created a recipe application, where ideally, I and my family members would post and share our old and new recipes. The application has a user model and a recipe model. A user` has_many` recipes, and a recipe `belongs_to` a user. The application has two layers. If a user is not logged in, she can view the homepage where it directs to all the recipes and signup and login pages. To view the recipes, a user does not have to log in. Once logged in, a user can create, edit and delete her profile. A user can view his recipes list, other user’s recipe list, all the listed recipes, as well as the list of users and their profile pages. Only logged in users are able to view other user’s emails. Additionally, a user can add a recipe, edit and delete her recipes. 

In this project, I spent more time on associations. At one point, I had user pages and recipe pages all set up, but two models would not communicate to each other. For example, I was not able to see an individual user’s recipes. The next step was to associate two models by adding `user_id` table for recipes table. After migrating the table, I had to define both the `@recipe` and `@user` in the action route where I wanted to render the view `recipe.user.username`. Getting to this point was not automatic, as I had to go back to my resources while thinking through the ways to bridge two models.

I realized that authorization, although not too difficult to figure out, takes time to go to every single page and think whom you give permission to view, what to view, edit, delete or what buttons to show. Adding custom made flash messages to every possible scenario is also a tedious work. Since I will be assessed for the application logic in this instance, I did not spend too much time in giving the application a style. I tweaked a lot on session cookies with

```
use Rack::Session::Cookie, :key => 'rack.session',
                           :domain => ENV.fetch(“HOSTNAME”),
                           :path => '/',
                           :expire_after => 3600, # In seconds
                           :secret => ENV.FETCH(“SESSION_SECRET”),
``` 
while removing enable: sessions. I wanted  my application automatically log a user out when the browser shuts downs or server quits. But for some reason, what I expected did not work. So I put this improvement for hold, and moved on with what I have right now. 

It was fun to learn to deploy my application to Heroku. Current application is in its simplest form. It can be improved to add social network element by making users able to connect with each other or adding `has_many_through` relationship in a form of comments that belong to a recipe, which belongs to a user, and adding additional tables for the recipe table such as ingredients, instructions, picture and video entries. I hope to work on these features as I gain more skills and make more progress in the curriculum. Meanwhile, any bug reports or suggestions for improvement would be greatly appreciated. 

You can access my application here: [Dillorom’s Cookbook](https://dilloromscookbook.herokuapp.com/)

Link to the application’s [GitHub repository.](https://github.com/Dillorom/sinatra-project)






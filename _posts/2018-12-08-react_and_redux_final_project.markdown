---
layout: post
title:      "React and Redux final project "
date:       2018-12-08 15:07:50 +0000
permalink:  react_and_redux_final_project
---

For my final project I created a Goodreads-like application to keep track of books a user reads. Although the application is not fully implemented yet, my plan is to have a user sign up, enter a goal of number of books a user wants to read in a certain year, search/add books from/to the library to her/his shelf, and be able to see the progress one makes as the books get added up to the shelf. 

Currently, the application supports books library, adding new books fully and setting a goal partially. Login and shelf components will be added soon. The application is a full stack, and I used Ruby on Rails for my back-end. React and Redux takes over the front-end. As React only can offer a view part of MVC trio, I had to rely on Rails for my model and controller to persist the data. The application has two models: books and users for now. I have entered a list of books in my seed database to render books in the library. 

The front-end of the application consists of containers, components, store and actions. My containers are concerned with either having a state of their own or connecting to the store to access props. Container components parent child components and therefore pass props. Stateless components do not have a state as the name suggests, and receive props from a parent component, and simply renders them. As I worked on my project, I came to realize that not all the components’ state has to be stored in the store. If there is no need to access the state and properties in a different component, the state and property are better to be left in the component. I think it is a thin line in Redux that every developer needs to be of her own judge, and don’t overuse store. 

I have defined my actions in the actions folder and imported them to components as I need using connect. Once an action is triggered, it goes to the store, where my reducers recognize an action by the action type and perform the appropriate solution. I connected my front-end with the Rails part of my application in the actions with fetch() method using` GET`, `POST`, and `DELETE` methods. Because of the asynchronousity of the fetch method, I used the `thunk` middleware from Redux. The` thunk` allows you to write action creators that return a function instead of an action. As the ` fetch() `method returns a function, the `thunk` helps to delay the dispatch of an action, or to dispatch only if a certain condition is met. 

I also used React Routes to render different manu tabs via `NavBar`, ` Link` and regular ` Route`. Because I have many different reducers in the store, I used `combineReducers `from Redux. I also use `<Provider />` , a special component in my `index.js` file to make the store available to all containers without passing it explicitly. I mostly created a folder to each component where I have both ` .js` and` .css` files, and style my components in the ` .css` file. 


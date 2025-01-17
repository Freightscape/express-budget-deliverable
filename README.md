<h1><img src="https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png" alt="" style="max-width:100%;" /></h1>

# Budgtr

Build an express app that let's you create, and read

#### Learning Objectives

- Practice building an express app
- Practice making an index route
- Practice making a show route
- Practice making new/create routes
- Practice adding static assets (CSS)

#### Prerequisites

- Express Basics (Create/Read/Static Assets)

---

## Deliverables

You'll be creating an app that can let you

- see a list of your income and expenditures
- show you one income/expenditure item
- create a new income/expenditure item

## Technical Requirements

1. Must be able to run without syntax errors
2. Must have index, show, create, new routes, using REST
3. Must have basic MVC structure (more details below)

## Submission Guidelines

- Must be submitted no later than the start of the next class

---

# Getting Started

## Data

You are provided a `budget.js` file with data for you to use to populate your index and show routes

## Routes

- Index
  - GET `/budgets`
- Show
  - GET `/budgets/:index`
- New
  - GET `/budgets/new`
- Create
  - POST `/budgets`

## MVC

Models, Views, Controller

We only have one model, so it may seem all these folders are overkill. As we start building with more complexity these folders will gain utility

- Your app should follow the MVC format
- Models
  - `budget.js` - the data we provided
- Controllers
  - since we just have one set of routes, we'll include them in our `server.js` stay tuned for lessons that'll teach us how to organize our code when we have more sets of routes
- Views
  - your liquid files go in here
- Public
  - your css file(s) go(es) here
    - recommended to go to try a new css framework:<br>
      http://getskeleton.com/
    - download the `normalize.css` and `skeleton.css` files and add them to your public directory (or use the CDNs:
      <br> `https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.0/normalize.css` and `https://cdnjs.cloudflare.com/ajax/libs/skeleton/2.0.4/skeleton.css` - thanks for the Tip Sam Whitleton!)
    - link them in your liquid files:
    ```html
    <link rel="stylesheet" href="/normalize.css" />
    <link rel="stylesheet" href="/skeleton.css" />
    ```
    In order to immediately modernize your HTML

At the root of your project:

- `server.js`
- `package.json` created with `npm init`
- `.gitignore` - create it and add `node_modules`, you don't need it yet, but it is good practice to use this

<details><summary>File Structure</summary>

![file structure example](https://i.imgur.com/vIbW1fN.png)

</details>

### Commits

The order doesn't matter, but this will help you check your progress of completing this homework:

##### commit at least each time you get a route and/or view working

#### Getting Started

- server is working and displays a plain `res.send` index page ` with some text like 'hello world'
- Added and configured npm packages `express`, `liquid`, `liquid-express-views`
- configured `express.static`

- created index.liquid
  - html boiler plate
  - link `normalize.css` and `skeleton.css`
  - div with the class `container`
  - `h1` with the text Budgtr ALL (or similar text)

Expected appearance with `normalize.css` and `skeleton.css` are properly linked:

![just an h1 inside a div with a class of container](https://i.imgur.com/CygNXJZ.png)

<hr>

#### Index

- Set your` models/budget.js` data to a variable named `Budget`
- Display your data on your index page as a `<table>`
- each income/expenditure should be a `<tr>`
- each piece of data should be its own table cell `<td>`
- the `name` should be wrapped in an `<a>` (anchor) tag, that goes nowhere for the moment, but will eventually link to the show page for that item

Expected Apperance:

![index.liquid populated with data](https://i.imgur.com/Hf6TkJU.png)

<hr>

#### Show

- A show route and `show.liquid`
- a link from `index.liquid` item name to its show page
  - html boilerplate
  - remember to add your css links (copy from your `index.liquid`)
  - a `<div>` with the class of `container`
  - an `<h1>` with the name of your item
  - a `<button>` that takes you back to the `index.liquid` page
  - the rest of the details of the item

Sample Apperance:

![show route](https://i.imgur.com/dVBZicJ.png)

**Hint:** the button should already be styled if your `normalize.css` and `skeleton.css` are linked properly

Feel free to organize the rest of this page any way you like. Hold off on styling this more until the HFM section - just use the base styles provided by our already linked css files

<hr>

#### New

- configured `body-parser`
- Add a button in your `index.liquid` that links to a new route that displays `new.liquid`
- The `new.liquid` should contain
- html boilerplate
- links to your css files
- a `div` with the class container
- an `h1` with a descriptive title
- a form, with the appropriate action and method
- an input field for
  - date
  - name
  - amount
  - from
  - submit
  - tags (bonus)
- Styling forms are a pain, keep it simple for now

**Hint**: use the attribute `placeholder` in the input field to see a placeholder value, rather than putting a label of the input field outside. Here is an example:

![placeholder example](https://i.imgur.com/KZ0DSKn.png)

**GOTCHA** - make sure this get route is above your URL parameters route

![filled out form](https://i.imgur.com/3CA6L5F.png)

<hr>

#### New

- A new route that is a post route
- first just console.log the `req.body`
- once the `req.body` is what you'd an expect (an object with keys that match our data in our `models/budget.js` and values that were entered in your form) `.push()` the `req.body` to your `Budget`
- then redirect to the index
- when you redirect to your index page, your new item should appear

See new item at the bottom:

![new item in list](https://i.imgur.com/0OTjWiw.png)

Show page should also render properly

![new item show page](https://i.imgur.com/r6CvxlW.png)

### Hints

<details><summary>Server.js</summary>

![server.js example](https://i.imgur.com/uSYHYzp.png)

</details>

## Innovation Time!

Remember, this is just JavaScript, so you can write as much JS logic as you want to make the app more useful beyond just showing the data as is. Be sure you solve this on your own.

- Add a variable 'bankAccount'

  - display it at the top of the `index.liquid`
  - have this value update based on each item
  - if the value is less than 0, change the background to red
  - if the value is greater than 1000 change the background to blue or green

- Tips
  - pseudocode on your own, figure out YOUR way of solving it
  - have a code graveyard
  - talk it through with the TA
  - link to helpful articles on stack overflow/elsewhere
  - collaborate - have a friend help you solve it your way or help a friend solve it their way

<hr>

---

## Hungry for More

<details><summary>Click to see HFM options</summary><p>

Feel free to choose what you want and if you want to implement something differently than the suggestion, go for it! It is hungry for more time!

- Go back to the afternoon lab and use cURL
- render the tags as list items in an unordered list
- input the tags, and add them to the tags array, figure out how to properly add multiple tags
- override the amount input so that it defaults to a negative number
- add logic to check whether the item is an expenditure or income (use two different fields? a check box? separate buttons? The choice is yours) and then input the amount as negative or positive based on the user's input

- style your app, add a `main.css` that adds your personal style on top of normalize and skeleton

**SUPER BONUS**

- try to store data in [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API)

- If you implemented tags, sort/filter your list by tags (no hints! There are many ways to solve this!)

</p></details>

---

_Copyright 2020, General Assembly Space. Licensed under [CC-BY-NC-SA, 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)_

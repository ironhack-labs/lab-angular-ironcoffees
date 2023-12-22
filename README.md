![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# LAB Angular | IronCoffees

## Introduction

We have just learned how to get and post the data from and to the APIs so let's practice a bit more.

<br>

## Requirements

1. Fork this repo.
2. Clone this repo.
3. Add your instructor and the class graders as collaborators to your repository. If you are unsure who your class graders are, ask your instructor or refer to the day 1 slide deck.
4. In the repository, create a Java project and add the code for the following prompts.

## Submission

Once you finish the assignment, submit a URL link to your repository or your pull request in the field below.

<br>

## Instructions

Since coffee is one of the most consumed drinks between Ironhackers, our mission here is to create an app to showcase some of the best-handcrafted coffees, but not just that - to save some as well so the rest of Ironhack community is informed :blush:. Our end goal is creating something like this:
<br>

<div style="display: flex; justify-content: center">
<img src="https://education-team-2020.s3.eu-west-1.amazonaws.com/assets-ironcoffee/ironcoffees-homework-1.gif" />
</div>

<br><br>

We will be building a Angular app so the API (server) needs to be built somewhere for us, right? You are completely right, it's deployed on _heroku_ and the root fo the API is:
**[https://ih-coffees-api-42e1df06199a.herokuapp.com/coffees](https://ih-coffees-api-42e1df06199a.herokuapp.com/coffees)**.

<br>

The available endpoints are the following:

<br>

| Method | Endpoint            | Response (200)                                           | Action                                                                                                                                      |
| ------ | ------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| GET    | /                   | [coffees]                                                | Get all the coffees from the DB                                                                                                             |
| GET    | /:id                | { coffee }                                               | Get the a single/specific coffee                                                                                                            |
| GET    | /random             | { coffee }                                               | Get a random coffee from the DB                                                                                                             |
| POST   | /new                | { message: "New coffee successfully saved to database!"} | Create a new coffee (the fields are specified in the instructions)                                                                          |
| GET    | /search?q=`{query}` | [coffees]                                                | Get coffees from the DB whose name contains the search term. For example `/search?q=lager` searches for all coffees with lager in the name. |

<br>

The **IronCoffees** project will include the following features:

- A **Home** page with three different options:
  - _All Coffees_
  - _Random Coffee_
  - _New Coffee_
- A **List Coffees** page where you should display all the coffees
- A **Single Coffee** page to display the details of the coffee the user clicked on
- A **Random Coffee** page to display a Random Coffee
- A **New Coffee** page to show a form where a user can create new coffees

## Iteration 1 | Home Page

Create a **Home Page**. This view should include three links to separate pages:

- `/coffees`
- `/random-coffee`
- `/new-coffee`

Feel free to design it however you wish, but in case you want to do it the way we did it, you can find the following images in this folder - **[lab-ironcoffees-resources](https://drive.google.com/drive/folders/1TZVZdPJqA6pvBwuLe_XVEcbmvNqAlk1k)**.

- Create a new folder inside `src` (you can name it `assets`) and add the images inside that folder.

<div style="display: flex; justify-content: center">
  <img src="https://education-team-2020.s3.eu-west-1.amazonaws.com/assets-ironcoffee/home-page.png" height="600px" />
</div>

<br>

## Iteration 2 | Header

On every view (except for the `home`), we should add a **header** with a `link` to the root of the `app`.

  <details>
    <summary><b> Click to see the image </b></summary>

  <br>
    
  <div style="display: flex; justify-content: center">
    <img src="https://education-team-2020.s3.eu-west-1.amazonaws.com/java/ironbeers-homework-nav.png" height="100px" />
  </div>
    
  </details>

<br>

## Iteration 3 | List all the coffees

On the `/coffees` route, we should display all the coffees from the database. So, in this case, you need to "hit" the API's route `https://ih-coffees-api-42e1df06199a.herokuapp.com/coffees` and the API will return an **array of coffees**.

_Hint_: The array of coffees is array of objects. We strongly advise you to **console log the response** from the API so you can see the structure of it.

You should display the following from each of the coffees:

- `image`
- `name`
- `tagline`
- `contributed_by`
- **Also, add the link to check the details of each coffee. The link should navigate to `/coffees/:coffeeId`.**

<br>

<details>
    <summary> <b> Click to see the image </b> </summary>

<br>

<div style="display: flex; justify-content: center">
  <img src="https://education-team-2020.s3.eu-west-1.amazonaws.com/assets-ironcoffee/all-coffees-page.png" height="600px" />
</div>

</details>

<br>

The first time you call the API, it might take a bit to respond. It's hosted on Heroku and it goes to sleep after 30 minutes, you know! :wink:

<br>

## Iteration 4 |  Display a single coffee

When a user click on one of the coffees, you should display a detailed view of it, including the following fields:

- `image`
- `name`
- `tagline`
- `first_roasted`
- `strength_level`
- `description`
- `contributed_by`

Again, we **strongly recommend to console log the response from the API**.

<br>

<details>
    <summary> <b> Click to see the image </b> </summary>

<br>

<div style="display: flex; justify-content: center">
  <img src="https://education-team-2020.s3.eu-west-1.amazonaws.com/assets-ironcoffee/single-coffee-page.png" height="600px" />
</div>

</details>

<br>

## Iteration 5 |  A random coffee

On the `/random-coffee` route, we will render a single coffee that will be retrieved from the database. The endpoint will do all the job for us, all we need to do is to call `https://ih-coffees-api-42e1df06199a.herokuapp.com/coffees/random`. We should receive an object including all the info about a coffee.
The same way we did with the **Single Coffee** view, we should render the following fields:

- `image`
- `name`
- `tagline`
- `first_roasted`
- `strength_level`
- `description`
- `contributed_by`

<br>

<details>
    <summary> <b> Click to see the image </b> </summary>

<br>

<div style="display: flex; justify-content: center">
  <img src="https://education-team-2020.s3.eu-west-1.amazonaws.com/assets-ironcoffee/random-coffee-page.png" height="600px" />
</div>

</details>

<br>

## Iteration 6 |  Create a new coffee

Finally, on the `/new-coffee` route, we should render a form where user can create new coffees. The `form` should include the following fields:

- **name** - must be type _text_
- **tagline** - must be type _text_
- **description** - must be type _text_
- **first_roasted** - must be type _text_
- **roaster_tips** - must be type _text_
- **strength_level** - must be type _number_ **!!!**
- **contributed_by** - must be type _text_

Why we pointed out the type? Well, since we already console log response from the API, we could notice that all the fields are strings but _strength_level_, which is number. In the _coffee model_ all the properties are type _String_ except _strength_level_, which is type _Number_.
When you have built the form, you should do a `POST` request to `https://ih-coffees-api-42e1df06199a.herokuapp.com/coffees/new`, passing all the data on the `body` object. If everything went ok, you would receive a **200** response from the server.

Notice that the fields on the `body` should have those specific **names** so the API can create a new coffee.

_What could go wrong?_: You inputted string instead of number in the _strength_level_ field and the server sent you **500** error.
Since we didn't cover how to upload images yet, don't worry about it now - the API will assign a random image to the new coffee.

<br>

<details>
    <summary> <b> Click to see the image </b> </summary>

<br>

<div style="display: flex; justify-content: center;">
  <img src="https://education-team-2020.s3.eu-west-1.amazonaws.com/assets-ironcoffee/add-coffee-page.png" height="600px" />
</div>

</details>

<br>

## Bonus | Filter the coffees

Yes! One endpoint left! On the `/coffees` route, add an `input` where users can search for coffees. Every time a new letter is typed, you should call to **`https://ih-coffees-api-42e1df06199a.herokuapp.com/coffees/search?q={query}`** passing the value of the input in the `q` param.

<br>

## Important Notes

- Everyone in the squad should contribute equally to the project in time and lines of code written.
- All code must be reviewed before it is merged into the `master` branch.
- All squad members must participate in code review.
- Every repository should have a README file with clear instructions, demo files, or any documentation needed so other teams don't have problems with the review.
- This is intended to be a challenging assignment. You will have to rely heavily on your teammates and independent research. Learning independently is a hallmark of a good developer and our job is to turn you into good developers. This process may be frustrating but you will learn a ton!

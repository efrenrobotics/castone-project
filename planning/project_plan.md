# Project Plan

Pod Members: **Efren Mendoza, Blessing Adomakoh, Faaizah Afoda**

## Problem Statement and Description

### Problem Statement

The challenge is to develop a user-centric, dynamic recipe book that utilizes AI.

Sometimes while looking through the kitchen one gets stumped thinking about what to make with the ingredients they have. They spend more time thinking about eating than actually eating. Our app comes to mitigate that problem.

Target Audience : Emerging Adults

### Description

An AI powered chef that creates recipes based on ingredients and a cuisine chosen by YOU!
We want to aid emerging adults in the kitchen as it’s difficult to decide what to cook. So we have created and utilized this AI tool to help those looking to cook and diversify their palates!

## User Roles and Personas

### User Roles

- BEF Register User (RU)
- BEF Unregistered User (UU)

### User Personas

#### User Persona - Tim Hutchins

"I always come back from studying and never know what to cook"

**User Demographic**

- Age: 21
- Location: Los Angeles, California
- Occupation: Student/Intern
- Income: ~$25,000
- Status: Single

**Background**

- Tim goes to classes, enjoys working out, and in his spare time likes painting.

**Goals**

- Spend less money eating out
- Cook more often
- Learn new recipes
- Experiment with new cuisines

**Frustrations**

- Improve health through a better diet

#### User Persona - Amanda Walker

"I am always scrambling between my job, cleaning the house, and feeding the family"

**User Demographic**

- Age: 42
- Location: Dallas, Texas
- Occupation: Retail Worker/Housewife
- Income: ~$75,000 (Joint Income)
- Status: Married

**Background**

- Amanda works a nine-to-five Monday through Friday and she needs to be efficient when going grocery shopping.

**Goals**

- Always feed my family
- Organize my grocery shopping
- Keep track of my favorite recipes

**Frustrations**

- Often forget what I want to buy when I go to the grocery store
- No easy way to track which ingredients I'm missing when looking at recipes

## User Stories

1.) As a I want < to be able to a Welcome Page> So that < I can understand what the website is about>

Acceptance Criteria: Given that I am a (UU) I can navigate through the website and have access to home page and about page

2.) As a I want < to be a to see a How to of the site> So that

Acceptance Criteria: Given that I am an unregistered user, I want to be able to understand how the website works I expect a “How to section” of the website to see what the website is about

3.) As an I want < to be able to a couple example recipes> So that < I can have a glimpse into how the recipes are like>

Acceptance Criteria: Given that I am an unregistered user, I want to be able to view what recipes can be generated I should see an example of what the application will provide me if I were to use it

4.) As a < Unregistered User > I want < be able to register > So that < I can have my own user profile >

Acceptance Criteria :

Given that I am an (UU) I want to create a user profile to be able to access the (RU) features User must input first name, last name, valid email, password, birthday (month, day) when in the registration form

/_ categories _/ 5.) As a < Registered user > role: beginner, intermediate, expert I want So that < I can diversify my Palette >

Acceptance Criteria:

Given that I am a registered and logged in user, I should be able to see the dropdown of different types of cuisines to choose from.

If the cuisine I want to make is not in the dropdown, then I should be able to type it in to specify the type of food I want to make.

/_ chef category (beginner, intermediate, expert) _/ 6.) As a < Registered user > I want < to receive instructions > So that < to learn how to make meals>

Acceptance Criteria: MVP:

Given that I am a Registered user: I should be be able to input my ingredients to receive a recipe I should be able to receive instructions to follow

Stretch: When I put ingredients in the query I have an option to pick a level of specificity for instructions (easy, medium, etc.) Can see ratings from other users to see what's recommended from others

/\* database 7.) As a < Registered User > I want < Be Able to look at previous recipes > So that < I can refer back to recipes I have created >

Acceptance Criteria: Given that I am a registered and logged in user, I can click on a button to add this recipe to my “previous recipes” table. When I go to my user profile I can view a list of my previous recipes and I can browse them

8.) As a I want So that .

Acceptance Criteria: MVP:

Given that I am a registered and logged in user, I can click on a button to add this recipe to my “favorite recipes” table.

When I go to my user profile I can view a list of my favorite recipes and I can browse them

Stretch Goal :

Implement the friend network and share with friend

/_ ChatGPT _/ 9.) As a < Registered User > I want So that < I can get more done>

Acceptance Criteria:

Given that I am a Registered user when searching for recipes I should be able to have a “favorites and previous section to have access to quick recipes I should be able to input ingredients I have to make food based on ingredients I have

10.) As a < Registered User> I want So that < I can still have my recipes saved >

Acceptance Criteria: Given that I am a registered user who is logged in, I should be able to log out My information and recipes should save when I log out

## Pages/Screens

List all the pages and screens in the app. Include wireframes for at least 3 of them.

## Data Model

### User Table

| Unique Id | First Name | Last Name | Email            | Password |
| --------- | ---------- | --------- | ---------------- | -------- |
| 1         | Tim        | Hutchins  | thutch@gmail.com | Password |

### Unique User Table

| Unique User Id | Previous Recipes        | Favorite Recipes         |
| -------------- | ----------------------- | ------------------------ |
| 1              | list of 10 prev recipes | list of favorite recipes |

### All Users Recipes

Recipe Categories
| Catch All | American | Mexican | Indian | Italian | Japanese | ... |
| -------- | -------- | -------- | ------ | ------- | -------- | --- |
| [] | [] | [] | [] | [] | [] | [] |

## Endpoints

User Routes

POST /api/user/favorite_recipe: Create entry for current recipe in the Unique User Recipe Table - Favorite Recipes.

GET /api/user/prev_recipes: Read the first five entries from the Unique User Recipe Table - Prev Recipes.

Recipe Routes

POST /api/recipes/generate_recipe/:cuisine:
If :cuisine is NULL, create a recipe with the following ingredients ingredients array and output it in JSON format.
If :cuisine is not NULL, create a recipe with the following ingredients ingredients array, chosen cuisine style, and output it in JSON format.
Authentication Routes

POST /api/auth/register: Create a new user entry and add it to the users table.

Authentication and Security
Error handling on erroneous input.
POST /api/auth/login: Read user entry from the users table.

Authentication and Security
Error handling on erroneous input.

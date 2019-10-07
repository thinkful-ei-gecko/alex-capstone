# Recipeak Screen Inventory

## Basic Page Layout

### Landing Page
[Link](./index.html)

- About page with basic app description and super slick foodie hero. Call to action for Signup Page.

### Signup Page

[Link](./signup.html)

A signup form with fields for new users. Includes text inputs for name, username, email and password. All should have form validation in front and data validation in back.

- When user submits signup info for form ->

  if valid and passes server -> Go to ['User's Home'](./userhome.html) page

  if invalid/server error -> Displays feedback on what must change/what happened

### Login Page

[Link])(./login.html)

A login input that takes a username and password, then allows a user to log in with appropriate permissions.

- When user submits login info ->

    if valid -> Go to [User's Recipes](./userhome.html) page; ['Primary Nav'](./elements/primarynav.html) display name and username.

    if invalid/error -> display feedback stating some part of submission incorrect.

### User's Home Page

[Link](./userhome.html)

Page with compacted ['Recipe Cards'](./recipe/recipecard.html) that show title, category and rating. A nav for this page, ['User Home Nav'](./elements/userhomenav.html), appears under primary nav. Cards may be viewed or deleted from this screen.

- When card title or recipe logo clicked ->

go to ['Recipe View'](./recipe/recipeview.html) page for target recipe.

- When card 'Edit' button clicked ->

go to ['Recipe Edit'](./recipe/recipeedit.html) page for target recipe.

- When card 'Delete' button clicked ->

shoot ['Delete Recipe'](./modal/deleterecipe.html) modal, which asks for confirmation; 'Are you sure?' with 'Yes, Delete' and 'No, Go Back' buttons. ->

if yes -> delete item, return to ['User's Home'](./userhome.html) Page.

if no -> modal disappears, remain on current page.

### Recipe Add Page

[Link](./recipe/recipeadd.html)

Displays a form with inputs for all portions of a recipe -

#### Section 1

- Name (text, required)

- Category (enum [None(default), Breakfast, Lunch, Dinner, Dessert, Snack], required)

- Rating (integer, range 1 to 6, optional)

- Portions (integer, how many portions the base recipe makes)]

#### Section 2

- Ingredients (amount, ingredient)

Drop menu for amount with various measurement units to be further defined in production. Sticky form on the bottom of section to continue adding ingredients.

### Section 3

- Instructions (includes step-by-step directions for recipe. For example:

        Step 1: Once the water boils, place the noodles in the pot. Cook for 15 minutes.
        Step 2: Strain the noodles and rinse under cold water.

(In an ideal world, steps would act like cards and have drag-and-drop reordering for more impressive display options, but I don't think I have time to implement that.)

### Recipe View Page

[Link](./recipe/recipeview.html)

Displays all info for a single recipe:

- section 1 (header): [Title, category([Breakfast, Lunch, Dinner, Dessert, Snack]), rating, portions(how many portions the base recipe makes)]; Rating is a five-star system that is editable from this page by clicking on star.

- section 2 (recipe-menu): 'Edit Recipe' button leading to ['Recipe Edit'](./recipe/recipeedit.html) page; 'Delete Recipe' button leading to ['Delete Recipe'](./modal/deleterecipe.html) modal.

-section 3 (instructions): ingredients, steps[step 1, step 2, step 3...].

### Recipe Edit Page

[Link](./recipe/recipeedit.html)

Displays contents of view page as editable form, with original content as placeholders.

    Editable fields: Title, category, rating, portions.

### 404 Error Page

[Link](./404.html)

- Displays with broken link. The Primary Navigation is here, as well as a fun image and a 'Back' button going to the previous page.

## Static Page Elements

### Primary Navigation

[Link](./elements/primarynav.html)

    If logged out, displays Logo and link menu as 'Sign Up', Log In', 'Home', 'About'
    If logged in, displays Logo and link menu as [name], 'Log Out,', 'Home', 'About'

### User Home Navigation

[Link](./elements/userhomenav.html)

Recipe menu. Includes: 'Add', 'Category', and 'Rating' toggle buttons that filter the recipes by stated criteria. (This is a good place for a searchbar and other list functions for recipes down the road.)

- When 'Add Recipe' button clicked ->

    go to ['Add Recipe'](./recipe/recipeadd.html) page.

- When selection for 'Category' (ASC) or 'Rating'(ASC) made ->

    sort card view by category, rating or both, depending on what is active; change display of button to indicate it is active.

- When 'Metric' or 'US' is clicked ->

    change all recipe measurements in Ingredients to 'metric' or 'us' accordingly.

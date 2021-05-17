

## Troubleshooting steps

  1. Write down in dialy tasks the steps you will try before based on your best guest
  2. Use a test.html page
      - This way you make changes and get it working without worrying about messing with other code
  3. Test each step
      - if it work emplement it into yoru code
      - if it doesn't work restart on step 1

## How I found answers
- Responsive columns
  - Looked at the templates or site I was copying and inspected the column element and it showed me how they did it

- Responsive navbar
  1. Search youtube for tutorial looked for shortest one 
    - Used newboston
    - Even though answer was old found in his code navbar classes I was missing. And that navbar is automatically responsive
  2. Resarched navbar on bootstrap and got closer with responsiveness
    - Watched a tutorial on bootstrap navbar
  3. Finally found the answer by copying piece of the code over to an empy text bootstrap html file. For some reason on the new file the navbar had differen't classes and it worked
    - Narrowed it down to find the answer by comparing the two by each line
    - Basically debugging strategy

- Menu links won't justify
  - Added a border around the column, then div 
  - Found the I was trying to justify the div in the column which because it was the only thing in the div it couldn't move
  - Make sure you use borders and be specific about what you are trying to justify

- Hero Image Overlay
  1. Found a video that showed me how to do it
  2. Looked at the code
  3. Copied the code to make sure it works for me
  4. Figured out how it worked
    - Added border to the div I was learning about
    - Add comment to each line to explain what they did
      - If I didn't know I looked it up
    - Removed background image temporarily to see the overlay alone
  5. Test it on my project

 - Styling classes
  - search in google :  .className  what you want to do
  - Look for stack overflow guide

## Chrome dev tools

### Computed Tab
This shows the actual resolved css as it is rendered on the page

### Style Tab
This shows the css as it was written

## Head

### Link style sheet inside styles folder
```html
<link rel="stylesheet" href="styles/style.css">
```
## Footer

### Sticky footer (CSS)
- HTML
  - Add .sticky-footer to footer element
- CSS
 ```css
{
  body{
    min-height: 100vh; 
    /* make the minimum height of the body 100% of the whole screen */
  }

  .sticky-footer{
  position: sticky; 
  /* positions object to stay in place regardless of scrolling */

  top: 100%; 
  /* Threshold so that 100% of the view port must be between the top of the class before it becomes sticky */
  }
}
```
### Nav links without bullets
- CSS

  ```css

  .links{
    list-style-type: none; /* removes bullets */
    margin: 0; /* removes margins */
    padding: 0; /* removes padding */
    text-decoration: none;
    color: inherit;
  } 
  ```
  
- HTML
    
    ```html
    <div class="col border" >
    <h3 class="border">About Us</h3>
    <ul class="links border" >
      <li>
        <a href="#">Company</a>
      </li>
      <li>
        <a href="#">Team</a>
      </li>
      <li>
        <a href="#">Career</a>
      </li>
      <li>
        <a href="#">Graphic Design</a>
      </li>
      <li>
        <a href="#">Documentation</a>
      </li>
    </ul>
  </div>
  ```
  
  
### Search bar
- Pill shape
  - rounded-pill
- Move placeholder
  - add padding left, right, ect
- Increase height of search 
  - increase padding or use padding-top and padding-bottom

### Social media icons
- Use icon from font awesome, bootstrap, etc
- Changing colors
    - icon = color:white
    - background = backround-color: #hex of social media icon
- Background 
    - Make it a circle
        - Use rounded-circle (bootsrap) or border-radius: 50% (css)
    - Make circle bigger
        - Add padding 
    - Hover effect
        - Add .className:hover{opacity:0.5} in css below the class name with the rest of the css for the that specific icon

### Outline showng while clicking on rounded pill search

```css
  *{
    outline:none;
  } 
  ```

### Responsive columns

By defining the number of columns for each break point and giving that amount to all of the columns I can have the break points show how ever many columns I want. 
Ex: 
```html
<div class="col-12 col-sm-6 col-lg-3 mt-sm-0 ">
```
### What does .col-md mean column?
```html
  <div class="col-md"> 
    <!-- columns will be veritically stacked until it hits medium viewport -->
```

### Find font family
- Use dev tools arrow button

### Find font weight
- Use dev tools computed tab

### Import google fonts
 - You can use the @import option to import the font into the css directly instead of in the link. This helps with abstraction because you can import the font for the specific section of css you want directly on that page. 

1. Find the font
2. Choose the font
3. Choose the @import option ( on the side at time of writing)
4. Copy the code inside the style tag 
5. Paste the code in the specific css file where it will be used
6. Copy the font-family css code
7. Paste the code in the css file inside the element, class, or id you will be using on

### Margins (large) on the side of footer
- Changed the footer to .container this automatically gave it large margins on the side

### Margin too much at top of screen
- Useful links column had too much margin at smaller or medium size . Fixed by remove mt-5 because at xs-md it doesn't need any extra margin because its already at the top of screen like about


## Header

### Nav spacing between columns not spread to end
- Nav wasn't taking up the whole width of row
- Made nav width 100% of row with .w-100


### How to create a collapse button in bootstrap

https://www.w3schools.com/bootstrap4/bootstrap_collapse.asp

.collapse class indicates a collapsible element (a div in our example); this is the content that will be shown or hidden with a click of a button.

### Menu button (create)
- The icon with the 3 lines is called a "menu" icon 
- You can get it at this site https://lineicons.com/icons/ by typing in menu
  - This should work on other sites that offer icons
- Also can use &#9776; ( this the unicode for 3 lines) don't use if you don't have to because it can be blurry on non-retina displays and doesn't have correct semantic meaning https://css-tricks.com/three-line-menu-navicon/


### Collapse menu not disapearing
` Missing: 
```html
<nav class="navbar navbar-expand-md d-flex w-100 ">
```
- especially the navbar-expand-md which makes the nav list horizontal after the medium breakpoint(or whichever you set). And apparently it also determines if the menu icon will disapeear and the links will show automatically at that breakpoint

### Collapse menu not in right location
- If you want to click the button the links show up under/after the button then button has to be first in the html
- If you want to click the button and the links show up in front/side of the button the links have to been infront of the button in html

### Collapse menu justify center on small screen
- On the div containing the whole menu section change the col at small ( or whatever breakpoint you want) to col-breakpoint-12. This way while the screen is from 0 up to all of the small value the menu div will take the whole with of the screen
- You can now center the links with .text-center
  - You use text center because you can't flex the menu div with without messing up everything else
-

### Jusity menu links end 
- used .justify-content-end on the div above ul 
  - For some reason adding .d-flex to that same div messed with the menu buton and put the links outside of the menu button

### Text size responsive (Bootstrap)
- https://bootstrapcreative.com/can-adjust-text-size-bootstrap-responsive-design/
- Also in programming folder on google drive in bootstrap procedures


## Hero Section

### Sticky hero background

```css
.img-property{
  height:40em;
  background-image:url(images/img-property.jpg);
  background-repeat: no-repeat;
  background-position: center;
  background-attachment: fixed;
  background-size:cover;
}
```


### Hero Image with Transparent Colered Overlay
https://codepen.io/DZuz14/pen/jOPWLgz
- Create two divs
  - container div you will have the background image on 
  - overlay div you will have your content and a dark background color on
- The overlay div goes inside the container div
- The overlay div needs to fill 100% of the vertical and horizontal space of its container div
- This will put a dark background with content on top of the picture making it apear darker and that it has content on it.

- In bootstrap
  - Make a .container-fluid class
  - Giv it a background image
  - Give it a height (can use vh or em)
  - Verify you can see image
  - Inside that container-flud add another .container-fluid with all the content of the page like you normally would
  - Give it a .h-100 
  - Give this secound .container-fluid a class of .overlay
  - Give .overlay a   background: rgba(0, 0, 0, 0.65);
    - possibly .bg-color-secoundary might work
  - Remove the padding left and right from the original .container so the overlay covers the whole container

  ### Transparent search bar
  - Bootstrap
    - ON input element add .bg-transparent(b)
    - Note this will keep the background transparent when you type
  - CSS 
```css
.form-control{
  background: transparent;
}
```
- Note this the background will be white when you type
### Change placeholder color
create a class eg: .placeholder-search
add following css
```css
.placeholder-search::placeholder{
  color: white;
  
}
```
### Chance input search bar border thickness 
1. Create a class like .border-form
2. Add it the main div surrounding your search bar or just to the input element if its just a regular input
3. Add css to class
```Css
.border-form{
  border:3px solid white;
}
```
### Button fill space of containing div
- Use .d-flex on btn group
- use .flex-fill on each button

### Move text on a button
- .d-flex on button class
- .justify-content-*, or .align-content-* etc

### Tranparent dropdown button (when clicked)
- Add .bg-transparent to button class
- Add .text-* to make sure the text stays the same color you want when the button is clicked

### Transparent dropdown menu
```css
.dropdown-menu{
border:white;
}
```
### Dropdown item text color
```css
.dropdown-menu a{
  color: #FFFFFF !important;
}
```
### Dropdown item hover background
```css
.dropdown-menu a:hover{
  background:white;
}

```

- in boostrap the padding will be off between the menu and the item
to fix this add .p-2 to the first dropdown item in each dropdown menu
- .p-2 issued because its about 37.5% but in bootstrap it goes from .p-1 .25 and .p-2 .50 

### Put space (padding ) in between buttons
- add padding to the div conting the buttons
 
 ### Images responsive
-Boostrap
  - Should automatically be but if not add w-100

### Full width inside column (boostrap)
- remove padding on columns


## Section

### Column sizes need to be even but not fill the entire width
- Used .col-3 for size even though it was only three columns which usually would be a .col-4. (bootstrap)

### Center columns in a row
- beside the row class add .justify-content-center (boostrap)

### Cards different heights
- If the cards are different heights because of text 
- Add .h-100 to the class beside card on all the cards
  - This will make the cards fill the entire hieght of of the column

### Card content uneven
- on the same div as .card body usded: d-flex flex-column justify-content-between

### How to use psuedo-elements like ::before or ::after
```css
.recommendation-title{
  font-family:  'Poppins', sans-serif;
  font-weight: 600;
  
}
.recommendation-title::after{
  font-family: "FontAwesome";
  content: "\f10e";
  font-size: 56px;
  color: #F0F0F1;
  
}
```

### How to add icon to psuedo-element
- https://stackoverflow.com/questions/14294935/unicode-via-css-before

- In font awesome 4.7
```css
.recommendation-title{
  font-family:  'Poppins', sans-serif;
  font-weight: 600;
}

.recommendation-title::after{
  font-family: "FontAwesome";
  content: "\f10e";
  font-size: 56px;
  color: #F0F0F1;
  
}

```
  - Must remember to add font-family or it won't work
  - In the content section you have to use the unicode with a \ to escape it

- in font awesome 5 plus you might not need to do this 


### Turn image gray(grey)
Use 
```css
.img{
  filter: grayscale(100%);
}

```
### Media queries/ Responsive Css template
```css

@media only screen and (max-width: 568px) {...}


@media only screen and (min-width: 568px) {...}


@media only screen and (min-width: 768px) {...}


@media only screen and (min-width: 992px) {...}


@media only screen and (min-width: 1200px) {...}
```

### Naming classes
- Block, Element, Modifer

### Columns that in between sizes
- Create a container-fluid
- Put a .container inside of it
- Add the row inside the container
- Add the columns inside the rows



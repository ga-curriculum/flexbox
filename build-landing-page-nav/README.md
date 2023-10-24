# Build a Landing Page: Setup

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## Let’s build a site together!

We’re going to re-create the landing page for [**dribbble.com**](https://dribbble.com)! We’ll start by talking about the larger overall pieces of the site and then dive into building those individual pieces to create the whole!

Let’s take a quick look at the site.

![Hero image](./assets/dribble-hp.png)

## Setup

We’ll need to start from scratch with our HTML and CSS files for this activity. You will have two options, either create a new lecture project to start from scratch or reset the code in your current files you've been using up to this point.

Both options are totally fine.

### Option 1: New Lecture Project

If you want to create a new lecture project from scratch so that you can keep separate notes in it, open the toggle below for a command block you can copy that will do this for you quickly:
<details>
  <summary>New Project Setup</summary>

  Open your Terminal application and navigate to your `~/code/ga/lectures` directory:

  ```bash
  cd ~/code/ga/lectures
  ```

  Make a new directory called `flexbox-site`, then enter this directory:

  ```bash
  mkdir flexbox-site
  cd flexbox-site
  ```

  Create a folder called `css`:

  ```bash
  mkdir css
  ```

  Then, create an `index.html` file and a `style.css` file that lives inside the `css` folder. These files will hold your work for this lecture:

  ```bash
  touch index.html css/style.css
  ```

  With the files created, open the contents of the directory in VS Code:

  ```bash
  code .
  ```

  Open the `index.html` file and add HTML boilerplate by typing `!` and then hitting the `Tab` key.

  Change the `title` to `Dribble Flex`:

  ```html
  <title>Dribble Flex</title>
  ```

  Then make use of the `style.css` file by adding this line inside the `<head>` tag:

  ```html
  <link rel="stylesheet" href="./css/style.css">
  ```

  Add the following to `style.css`:

  ```css
  html {
    box-sizing: border-box;
  }

  /* The Universal Selector */
  *, /* All elements*/
  *::before, /* All ::before pseudo-elements */
  *::after { /* All ::after pseudo-elements */
    /* height & width will now include border & padding by default
      but can be over-ridden as needed */
    box-sizing: inherit;
  }

  body {
    background-color: gray;
    font-family: sans-serif;
    margin: 0;
  }
  ```
</details>

### Option 2: Reset Current Files

If you just want to reset from the beginning with your current files, this toggle has the starter code for you:

<details>
  <summary>Starter Code</summary>

  `index.html`:
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dribbble Flex</title>
    <link rel="stylesheet" href="./css/style.css">
  </head>
  <body>

  </body>
  </html>
  ```

  `css/style.css`:
  ```css
  html {
    box-sizing: border-box;
  }

  /* The Universal Selector */
  *, /* All elements*/
  *::before, /* All ::before pseudo-elements */
  *::after { /* All ::after pseudo-elements */
    /* height & width will now include border & padding by default
      but can be over-ridden as needed */
    box-sizing: inherit;
  }

  body {
    background-color: gray;
    font-family: sans-serif;
    margin: 0;
  }
  ```
</details>

As part of this process, let’s also set some reasonable expectations for what we're trying to accomplish. We’re going to keep our re-creation focused around the layout of the site, not trying to duplicate fonts, photos, colors, animation, functionality, size of elements, etc. This will help keep us focused on the task at hand: **learning to design a site using Flexbox.** The purpose isn't to **FULLY recreate** the site, we're just staying focused on how these elements are laid out at a very basic level.

# The Flexbox Process

Our first order of business when we’re approaching a design we want to implement in Flexbox is to determine the main sections on a page. This is what we get after going through this process:

![Hero image](../assets/tktkhero-main-subhead.png)

We have four distinct parts of this page:

- A nav bar
- The hero content of the page - the main point of interaction on the page
- A sub-nav for filtering and sorting the main content
- The main content of the page

> 🧠 What you’re going to find is that this is a somewhat subjective process - if your first inclination would have been to combine the sub-nav and main content sections, that’s not a wrong decision - we’ll talk more about why we’re doing things in this way when we get to that point.

Breaking a site like this down into distinct parts is the foundation of our work with a layout - what you’re going to find with Flexbox is that the process is ultimately just about putting boxes (elements) inside of other boxes (elements that are Flexboxes). Let’s start over with our CSS and HTML and we’ll get the parts set up in code and then we’ll dive into the nav bar.

```html
<body>
  <nav></nav>
  <section id="hero"></section>
  <div id="subnav"></div>
  <main></main>
</body>
```

![Hero image](../assets/tktkhero-main-subhead.png)

Above is a dissection of the nav bar for the site. Looking at this we can broadly describe the items on the left side of the nav being ************destinations************ on the site and the items on the right of the nav as being related to user *******actions******* (as an aside this is a very very common pattern across the internet and one that many users will instantly recognize - you can use this knowledge to improve the user experience of your own sites!)

So how do we go about coding this? Well, first off there is a natural hierarchy here - destinations and actions are both inside of the nav and grouped separately so let’s start with that:

```html
  <nav>
    <div id="destinations">

    </div>
    <div id="actions">

    </div>
  </nav>
```

> 🧠 The only reason we’re using ids on these is so that we have an easy reference to them to talk about them in this lecture, a pattern you’ll see repeated throughout this lecture. In a normal project we wouldn’t need to use ids in this way.

Next, these need some content, so let’s fill that in. Remember that what we’re going for here is re-creating the general layout - not functionality - so even though this content is a bunch of links we’re just going to create them as p tags:

```html
  <nav>
    <div id="destinations">
      <p>dribbble</p>
      <p>Inspiration</p>
      <p>Find Work</p>
      <p>Learn Design</p>
      <p>Go Pro</p>
      <p>Design Files</p>
      <p>Hire Designers</p>
    </div>
    <div id="actions">
      <p>🔍</p>
      <p>Sign in</p>
      <button>Sign up</button>
    </div>
  </nav>
```

Let’s check out what we have so far:

![Hero image](../assets/tktkhero-main-subhead.png)

Our content is in place, let’s do a small bit of work to get it looking a little bit more like the original, and then we can make it flex!

Go to your browser, open the dev tools, and select the element picker (we lovingly refer to this as the magic wand). Get used to using this tool often - it’s one of the most useful tools you have in the browser to inspect elements quickly

![Hero image](../assets/tktkhero-main-subhead.png)

Let’s play with this for a bit and use it to find a few things:

- The color details of the sign up button (the color of the background and the font)
- The font details of the sign up button (specifically, its font weight)
- The details about the border of the sign up button (the border thickness, and radius)
- The dimensions of the sign up button and where those dimensions are coming from (padding)
- Here’s what we’ll need to implement to mimic this styling
    
    ```css
    nav button {
      background-color: #f082ac;
      border-radius: 8px;
      padding: 10px 16px;
      border: 0;
      color: #ffffff;
      font-weight: 500;
    }
    ```
    

Don’t worry, we won’t be this detailed about specifics of an element for the rest of this lecture, we’re using this as an opportunity to show that these details are available to you in the browser and you can use those details to help implement your own designs. Even after this work we’re no where close to an exact match, and that’s ok - **************************that’s not the goal here!**************************

### You Do 💪 - 5 minutes

- Find the background color of the nav bar element from dribbble using the magic wand in the browser and change the color of our nav bar element to match.
- Turn the nav bar into a Flexbox. Select a value on `justify-content` to make the `destinations` and `actions` appear on opposite sides of the nav bar. Use the Complete Guide to Flexbox to help you accomplish this. This won’t look great at the moment, but it’s a start.

https://css-tricks.com/snippets/css/a-guide-to-flexbox/

> 💡 Something you’ll notice when implementing Flexbox is that things will commonly look much worse until they start to look better.

Here’s the resulting code if you need it afterwords

```css
nav {
  background-color: white;
  display: flex;
  justify-content: space-between;
}
```

### You Do In Groups 💪 - 15 minutes

- Turn the `destinations` and `actions` `div` elements into Flexboxes that lay out their children in a row. Note that these elements are currently flex children - when you turn them into Flexboxes they will be acting as both flex children - to the `nav` element - ***and*** flex parents - to the elements that are inside of them.
- Using the Complete Guide to Flexbox, research a method we could use to create some space between the different elements inside of these `div`s. You can reference the nav bar element from dribbble to find the spacing between elements there, or not.
- Find the height of the nav bar element from dribbble using the magic wand in the browser and make it so that the height of our nav bar matches. Note there’s a quite a few ways you could go about this - there is no right and wrong way here, but some ways will make our future work easier or harder.
- Using the Complete Guide to Flexbox, find a method we could use to center the elements inside of the `destinations` and `actions` vertically in the nav bar. Depending on how you set the height of the nav bar this may take multiple new declarations.
- Add some left and right padding to the `nav` element so that the items on the left and right aren’t on the edge of the screen. You can reference the nav bar element from dribbble to find the padding around those elements there, or not.

https://css-tricks.com/snippets/css/a-guide-to-flexbox/

And here’s the resulting CSS so far if you need it afterwords:

```css
html {
  box-sizing: border-box;
}

/* The Universal Selector */
*, /* All elements*/
*::before, /* All ::before pseudo-elements */
*::after { /* All ::after pseudo-elements */
  /* height & width will now include border & padding by default
     but can be over-ridden as needed */
  box-sizing: inherit;
}

body {
  background-color: gray;
  font-family: sans-serif;
  margin: 0;
}

nav {
  background-color: white;
  display: flex;
  justify-content: space-between;
  padding: 0 24px;
}

nav button {
  background-color: #ea4c89;
  border-radius: 8px;
  padding: 10px 16px;
  border: 0;
  color: #ffffff;
  font-weight: 500;
}

nav > div {
  display: flex;
  height: 80px;
  align-items: center;
}

nav > div:first-child {
  gap: 32px;
}

nav > div:last-child {
  gap: 16px;
}
```

Our nav bar looks fantastic, great work!!

## Hero Section

On to our hero next. Let’s do the same breakdown for this that we did for our nav bar:

> ❓ What’s different about how the Hero section lays out its children compared to the nav?

Note that there is technically another section here - the attribution link at the bottom right - that we’re going to omit.

Here’s some HTML to get us started - copy it into your project.

```html
  <section id="hero">
    <div id="discover">
      <p>Content</p>
      <p>Content</p>
      <p>Content</p>
      <p>Content</p>
      <p>Content</p>
    </div>
    <div id="headers">
      <h1>
        Explore the world's leading
        <br>
        design portfolios
      </h1>
      <h2>
        Millions of designers and agencies around the world showcase their 
        portfolio work
        <br>
        on Dribble - the home to the world's best design and creative
        professionals.
      </h2>
    </div>
    <input type="text">
    <div id="trending">
      Trending searches
      <p>Content</p>
      <p>Content</p>
      <p>Content</p>
      <p>Content</p>
    </div>
  </section>
```

### You Do 💪 - 2 minutes

Take some time to explore this HTML and get more familiar with it. We’ll discuss any points of interest afterwords.

### You Do In Groups 💪 - 25 minutes

Utilize the Complete Guide to Flexbox to help you:

- Give this `hero` `section` a height of 560px, like this section is on dribbble’s site. Also give it a black background and white colored text.
- Turn the `hero` `section` into a Flexbox. Have it lay out its children in a column. Implement a Flexbox property to make it so that each of its children elements has some space around them.
- Turn the `discover` and `trending` `div`s into Flexboxes, have them lay out their children in a row, center those children horizontally and vertically within them, and make it so each element has a small gap between it and the other elements - you can have this match dribbble’s site or not. Give each `p` element a white background with black text (this is different than dribbble’s site, but simpler for us to implement - again the focus here is Flexbox). Also give the `p` elements in both the `discover` and `trending` `div`s an appropriate border radius, along with padding.

- Turn the `headers` `div` into a flexbox and have it lay out its children in a column. Make it so that the font size of the h1 and h2 elements matches the font size from dribbble’s site. Make sure the text is vertically centered as well. Make sure there is no margin at the top of the `h1` element and that there is no margin on the bottom of the `h2` element, or else the `headers` element will be too large.
- Give the input a size matching the size of the input element from dribbble’s site, along with an appropriate amount of padding and border radius. Remove the border from the element as well.

https://css-tricks.com/snippets/css/a-guide-to-flexbox/

Here’s the resulting CSS that we added!

```css
section {
  height: 560px;
  background-color: black;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  color: white;
}

h1,
h2 {
  text-align: center;
}

h1 {
  margin-top: 0;
  font-size: 32px;
}

h2 {
  font-size: 16px;
  margin-bottom: 0;
}

input {
  height: 58px;
  width: 600px;
  border-radius: 29px;
  border: 0px;
  padding: 0 24px;
}

#trending,
#discover {
  display: flex;
  justify-content: center;
  align-items: center;
}

#trending {
  gap: 6px;
}

#discover {
  gap: 10px;
}

#trending > p,
#discover > p {
  background-color: white;
  color: black;
  border-radius: 50px;
}

#discover > p {
  padding: 16px 20px;
}

#trending > p {
  padding: 6px 15px;
}
```

And here’s our re-creation so far:

![Hero image](../assets/tktkhero-main-subhead.png)

# Build a Landing Page: Breakdown

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

# The Flexbox Process

Our first order of business when we’re approaching a design we want to implement in Flexbox is to determine the main sections on a page. This is what we get after going through this process:

![Dribble Home Page Breakdown](./assets/dribble-hp-breakdown.png)

We have four distinct parts of this page:

- A nav bar
- The hero content of the page - the main point of interaction on the page
- A sub-nav for filtering and sorting the main content
- The main content of the page

> 🧠 What you’re going to find is that this is a somewhat subjective process. Your first inclination may have been to combine the sub-nav and main content sections. That’s not a wrong decision, we’ll just talk more about why we’re doing things in this way when we get to that point.

Breaking a site like this down into distinct parts is the foundation of our work with a layout. What you’re going to find with Flexbox is that the process is ultimately just about putting boxes (elements) inside of other boxes (elements that are Flexboxes).

Let’s get each of the parts that we've identified and set them up in our new code:

```html
<body>
  <nav></nav>
  <section id="hero"></section>
  <div id="subnav"></div>
  <main></main>
</body>
```

The next step will be coding out each distinct section of our site.

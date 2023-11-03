# ![Flexbox - Fundamentals](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to create Flexbox containers and items.

## Establishing default behavior

Let's discuss some baseline facts about the HTML we're working with. Ensuring we have a base understanding of these default behaviors will help us evaluate how they change as we apply flexbox rules to them.

```html
<section class="flex-parent">
  <div class="flex-child" id="1">1</div>
  <div class="flex-child" id="2">2</div>
  <div class="flex-child" id="3">3</div>
  <div class="flex-child" id="4">4</div>
</section>
```

- The `<section>` element is a **parent** element to all four `<div>` elements inside it. These `<div>` elements are the **children** of the `<section>` element (hence, our naming convention of the classes). Note we don't see its background color anywhere on our page - it's currently obscured by the background color set on the children elements!

  tktk Hunter - can you make an asset that helps demo this? Doesn't need to be complex, just want something visual to map this idea to.

- The `<section>` element is a **block** element. Block elements take up the entire width of their parent element, which, in this case, is the `body` element. By default, the `body` element is the full width of the browser window. Therefore, our `<section>` will span the full width of the browser window as well.
  
  tktk Hunter, same as above, just an asset to reinforce this idea. 

- Because each `<div>` within the `<section>` are also **block** elements, they, by default, also take up the full width of their **parent** element. That is why each `<div>` spans the full width of the browser window.
  
  tktk Hunter, same as above, just an asset to reinforce this idea.

- Also by default, their **height** is defined by the height of their contents. Unless you specify otherwise, they will be just as tall as they need to be to accommodate the content they hold.
  
  tktk Hunter, same as above, just an asset to reinforce this idea. Drawing out the height of the content and how that is equal to the height of the element should be enough.

- The same is true of the `<section>` element! Its height is based entirely on the height of its children. This is why we don't see its background color anywhere on our page - it's the same as the combined height of all its children elements!

  tktk Hunter, same as above, just an asset to reinforce this idea.

- If you remove the text from one of the `<div>`s, it looks like the element has been removed from the page, but it hasn't! Its height has just been reduced to 0.

- Here, we are giving these items classes called `"flex-parent"` and `"flex-child"`, but the actual application of Flexbox will occur in our CSS file. The names themselves provide no functionality whatsoever.

## Implement flexbox

The above is all the behavior of our page in its default state before making any of the elements into a flexbox.

Change the existing `.flex-parent` rule in your CSS to this:

```css
.flex-parent {
  background-color: black;
  display: flex;
}
```

We use a CSS `display: flex;` declaration to make an element a *flex container* or *parent*.

> 🧠 The `flex-parent` class name isn't important to making this a flexbox! We're just using it here to clarify where the parent/child relationship is being formed. You typically wouldn't have a class with this name - something like `container` is far more common.

After this change, your browser should look like this:

![Flexbox Enabled](./assets/flexbox-enabled.png)

Note the changes:

- The `<section>` element is now a **flex parent** or **flex container.**
- When we made this into a Flexbox, all of the children of the flexbox (the `<div>` elements) became **inline-block** elements instead of **block** elements. Their height is unchanged, but their width has collapsed to the width of the content inside of them.
- Because the `<div>` elements' widths have collapsed, they no longer take up the full width of the `<section>`. We can see the black background of said `<section>` element. Also, note how the height of the `<section>` element has collapsed so that it is still the height of its children elements.
- The `<div>` elements nested inside of our flex-parent `<section>` (its children) are now **flex children** or **flex items**. They are arranged in a row inside their parent. Arranging the children in a row is the default behavior of a Flexbox.

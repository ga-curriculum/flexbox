# Concepts

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

# Nesting Flexboxes

There’s one last major topic to cover before we move on to applying these ideas in a larger application which is the idea that we can *nest* a Flexbox inside of another Flexbox, like this (note a couple of small changes to the `flex-parent` class as well):

```css
.flex-parent {
  background-color: black;
  display: flex;
  height: 600px;
  justify-content: space-around;
	align-items: center;
}

.flex-child {
  font-family: sans-serif;
  font-size: 48px;
  height: 100px;
  width: 100px;
  display: flex;
}
```

Now any element with the `flex-child` class is also a Flexbox itself - `flex-child` isn’t a great name for this class now, but this is a great demonstration of the fact that flex children can themselves be flex parents!

A couple of items of note with this:

- This has no impact on how the flex children inside the existing flex parent behave. They will still follow all of the existing rules of flex children, and if we wanted to, we could apply child-specific properties to the `flex-child` class. Just like in real life, someone can simultaneously be a parent of a child and a child of a parent.
- What are the children elements of the `flex-child` `div`s? Even though there aren’t specific elements inside of them, text is considered an element itself, so if we apply rules to these elements that will impact their children then the text will be targeted!

This means that with this change:

```css
.flex-child {
  font-family: sans-serif;
  font-size: 48px;
  height: 100px;
  width: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}
```

The text will now be centered inside their boxes both horizontally and vertically! Cool!
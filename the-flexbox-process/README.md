# Concepts

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

For our next activity, we’ll need to start from scratch with our CSS and HTML files - if you want to create a new lecture project to start from scratch with so that you can keep your notes on, that’s totally fine. Open the toggle below for a command block you can copy that will do this for you quickly:

- New project setup
    
    ```bash
    mkdir flexbox-site
    cd flexbox-site
    mkdir css
    touch index.html css/style.css
    code .
    ```
    

If you just want to reset from the beginning with your current files or if you’re starting a new project, this toggle has the starter code for you:

- Starter code

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

index.html

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

css/style.css
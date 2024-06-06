# 7.4 - Interactivity in HTML

###### ICS3U - Mr. Jamieson 

- This README is your task. Read it carefully and follow the instructions.

---

<br>

Working in the console has been fun, but it's not very interactive. Also, **the console is meant for developers, not users**.

This repo contains a pretty simple HTML file. [Check it out](index.html).

In order to connect HTML and JavaScript, we need to connect them with a `<script>` tag. This tag will load _and run_ the JavaScript right away, so we will also add the `defer` attribute to tell the browser to load it last. Go to the `<head>` section of your [index.html](index.html) page and add the following tag under the comment (line 16).

```HTML
<script src="script.js" defer></script>
```

If we preview [the HTML file](index.html), we won't really know if the script loaded _unless we see an error in the developer tools_.

Let's test and check the loading of the script. Go to your [JavaScript file](script.js) and add a `console.log("Hello World!")`. Preview the [index.html file](index.html). **_Where's the console?_**

> _The console is hidden from the user. Press `CTRL+SHIFT+J` (⌘+option+J on a Mac) to open the developer tools. If that doesn't work, check your browser's documentation on how to open the developer console. (Sometimes F12)_

The console is helpful for _debugging_ and _testing_ but it also opens our code to mischief-makers who might play with it.

- 💡 Want to print something more interesting? Try: `console.log(document.title)`

<br>

## Interactivity

Check out [the HTML file](index.html). You will see a `button` and a `span`.

```HTML
<button id="btn_click">Click Me</button>
... <span id="click_counter">0</span> ...
```

More importantly, notice that they have an `id` attribute. This is one way to manipulate elements with JavaScript (and the method we'll be using).

### Input

There are _several_ ways to [get input from the user](https://www.w3schools.com/js/js_input_examples.asp) but we'll start with a `click` _event_.

When a user clicks or moves the mouse, uses the keyboard, speaks into a microphone, or touches the touchscreen - these are called **_events_**. In order to _react_ to an event, we ask JS to register [an event listener](https://www.w3schools.com/js/js_htmldom_eventlistener.asp).

To do this, we _attach_ (or add) the listener at the top of the JavaScript file (just below the `'use strict';`):

```JS
'use strict';

// document.getElementById("unique_id").addEventListener(TYPE, FUNCTION_TO_CALL)

// Example
document.getElementById("my_button").addEventListener("click", my_func)

function my_func() {
  console.log("I was clicked!")
}
```

---

### Let's try it

In [your JavaScript file](script.js), add an event listener for the button on your page. Have it call a function that prints "The button was clicked" to the console. _Test it_.

---

Lovely! But a bit useless.

We want to update the value inside the `<span>` that keeps track of how many times we've clicked the button.

### Output

We can manipulate any element in the Document Object Model (DOM) that has an identification. Most elements have `.innerText`, `.innerHTML` or `.textContent`. In our particular example, we will to modify the `.textContent`.

**Example:**

```JS
document.getElementById("my_element").textContent = "Some text"
```

### Try it

Create a **global** variable `clicks` that starts at 0 when the project loads.

```JS
let clicks = 0;
```

Now modify the button click function so that it increases `clicks` by one and updates the `<span>` contents with the value. _Test it_.

## Your Task

Modify your page by adding two more buttons - give them unique identifiers. Have one of the buttons _reduce_ the value of clicks by one and the other button _reset_ the clicks to zero. You might want these functions to print to the console for testing purposes (up to you).

Feel free to modify any of the page content to your liking.

### Too easy?

Here are some options:

- Start thinking of potential final project ideas (but don't lock yourself into one specifically).
- Have a look at [p5.js](https://p5js.org/) and start thinking of the possibilities...
- Don't really like web-dev and prefer hands-on projects with wires and buttons? Consider an arduino, microbit, or raspberry pi project (but keep in mind you will receive very little assistance). Yes - Mr. Brash has those devices.

<br><br>

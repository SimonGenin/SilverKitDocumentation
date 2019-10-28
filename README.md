# Introduction

SilverKit is a framework to help make an application that include senior users. It is currently in active development as a research project at the University of Namur, Belgium.

<div style="text-align:center">
    <a href="https://www.unamur.be">
    <img src="./images/unamur_logo.png" alt="UNamur Logo">
    </a>
</div>

# Example

SilverKit provides a clear API and a set of convenient html tag data attributes. With very few modification, elements get more accessible to people with deficiences.

Button observer:

```html
<html>
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/silverkit/0.0.1/silverkit.min.js"></script>
  </head>
  <body>
    <button data-sk-intent="click">
      This button is now accessible to seniors with deficiences
    </button>
  </body>
</html>
```

Task tracker, to gather data and analyse if a task is being tedious for the user:

```html
<html>
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/silverkit/0.0.1/silverkit.min.js"></script>
  </head>
  <body>
    <button data-sk-task-start="example-task-name">
      This defines the start of some task
    </button>

    <button data-sk-task-end="example-task-name">
      This defines the end of some task
    </button>
  </body>
</html>
```

Everything is available programmatically through API calls as well:

```html
<html>
  <body>
    <button id="start-task">
      This defines the start of some task
    </button>

    <button id="end-task">
      This defines the end of some task
    </button>
  </body>
</html>
```

```js
import { Task } from "SilverKit";

const exampleTask = new Task();

document.getElementById("start-task").click(event => {
  exampleTask.start();
});

document.getElementById("start-task").click(event => {
  exampleTask.start();
});

// launch analysis and get a promise to act on your view
exampleTask.analyse().then(response => {
  // do something
});
```

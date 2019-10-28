# Introduction

SilverKit is a framework to help make an application that include senior users. It is currently in active development as a research project at the University of Namur, Belgium.

<div style="text-align:center">
    <a href="https://www.unamur.be">
    <img src="./images/unamur_logo.png" alt="UNamur Logo">
    </a>
</div>

In more detais, once SilverKit is used in your code, all kind of interaction metrics are gathered. From them, a system tries to detect if something seems wrong, such as repeated miss clicks near a button. If there is indeed an anomaly infered, actions are taken to update the interface reactively. In the case of the miss clicked button, it might be an increase size of the its font and/or its shape.

SilverKit can collect a quite bunch of metrics and take many different actions on the interface. Everything is configurable, so that the developper stays in full control of his application.

SilverKit comes also with more complex interaction scheme such as task completion analysis. Of course, those more advanced features required more investment from developers and aren't just pluggable in the code like some other features are.

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

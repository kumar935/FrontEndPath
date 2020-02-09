## Closures

#### Closures inside loops

[MDN Link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
[jsfiddle link](https://jsfiddle.net/v7gjv/8164/)

```javascript

function showHelp(help) {
  document.getElementById('help').innerHTML = help;
}

function setupHelp() {
  var helpText = [
      {'id': 'email', 'help': 'Your e-mail address'},
      {'id': 'name', 'help': 'Your full name'},
      {'id': 'age', 'help': 'Your age (you must be over 16)'}
    ];

  for (var i = 0; i < helpText.length; i++) {
    var item = helpText[i];
    document.getElementById(item.id).onfocus = function() {
      showHelp(item.help); // so this will only show the result for last i that is i = 2;
    }
  }
}

// with let
function setupHelpWithLet() {
  var helpText = [
      {'id': 'email', 'help': 'Your e-mail address'},
      {'id': 'name', 'help': 'Your full name'},
      {'id': 'age', 'help': 'Your age (you must be over 16)'}
    ];

  for (let i = 0; i < helpText.length; i++) { // if i put let here, it still won't work
    var item = helpText[i]; // because i've used var item here and for all the scopes created by the loop, the last var declaration will override all, because var spans to the whole function scope
    //let item = helpText[i]; // but if i had used let here, then each loop will have its own scope and its own item.
    document.getElementById(item.id).onfocus = function() {
      showHelp(item.help); // so this will only show the result for last i that is i = 2;
    }
  }
}

setupHelp();

```

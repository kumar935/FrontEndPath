### Intro

### Yarn

Yarn seems simpler and better. But can't pinpoint the exact difference in how it gets flat dependencies.

### React Getting started

Simple enough to make a component without Webpack and all:

```javascript
/* global React ReactDOM */

var MyTitle = function () {
  return (
    React.createElement('div', null,
      React.createElement('h1', null, 'Check out this component!')
    )
  );
};

var MyFirstComponent = function () {
  return (
    React.createElement('div', null,
      React.createElement(MyTitle, null),
      React.createElement(MyTitle, null),
      React.createElement(MyTitle, null)
    )
  );
};

ReactDOM.render(
  React.createElement(MyFirstComponent),
  document.getElementById("app")
);

```

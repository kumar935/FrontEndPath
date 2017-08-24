## Purifying Functions | Lec 5

```javascript

function f(x){
  return 2 * Math.pow(x,2) + 3;
}

var y;

y = f(0);

y = f(2);

y = f(-1);

```

What if we can't avoid writing with side effects. How to purify?

Purifying this:

```javascript
//impure
function f(){
  y = 2 * Math.pow(x,2) + 3;
}

var x,y;

x=0;
f();
y;

x=2;
f();
y;
```

```javascript
//pure
function F(x){
  var y;
  f(x);
  return y;
  
  function f(){
    y = 2 * Math.pow(x,2) + 3;
  }
}

y = F(0);

y = F(2);

```

- Containing the side effect inside `function F(x)`
- Function F(x) shouldn't be too ugly

Another solution:

```javascript

function f(){
  y = 2 * Math.pow(x,2) + 3;
}

function F(curX){
  var [origX, origY] = [x,y];
  x = curX;
  f();
  var newY = y;
  [x,y] = [origX, origY];
  return newY;
}

var x,y;

F(0);

F(2);
```







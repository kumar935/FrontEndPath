### ES6 things

**Default exports vs named exports**
- [mdn](https://developer.mozilla.org/en/docs/web/javascript/reference/statements/export)
- [SO](http://stackoverflow.com/questions/33611812/javascript-es6-export-const-vs-export-default)

**export let vs export const** [SO](http://stackoverflow.com/questions/32558514/javascript-es6-export-const-vs-export-let)

#### Arrow functions

```javascript
[1,2,3].map(v => v+1); 
// desugars to:
[1,2,3].map(function(v){return v+1;});

[1,2,3].map(v => ({x: v}));
//desugars to
[1,2,3].map(function(v){ return {x:v};})

var func = arg1 => { console.log(arg1); }
// desugars to:
var func = function(arg1){ console.log(arg1); }
```

> `this` inside an arrow function now does not refer to undefined (in strict mode). 
```javascript
function Person(){
  this.age = 0;
  setInterval(() => {
    this.age++; // |this| properly refers to the person object
    //if the older way was used, this would refer to undefined in strict mode
  }, 1000);
}
var p = new Person();
```

> arrow functions don't have `arguments` variable, and they can't be used as constructors using the new operator, and they also don't have `prototype` property.

> When invoked through `call` or `apply` only arguments are passed and no `thisObject` is passed as the first parameter

> Not suitable to be used as methods of an object as in member function of an object

See all the examples here: [mdn](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

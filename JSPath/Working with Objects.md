## Object.create

[This](https://hackernoon.com/object-create-in-javascript-fa8674df6ed2) article

```javascript
//copy both prototype methods and properties
var x = Object.create(prototypeObject, propertiesObject);
//copy only properties 
var x = Object.create(null, propertiesObject);
//copy only prototype object
var x = Object.create(prototypeObject);
```

__Difference between using new keyword and Object.create__: new inherits the methods from the constructor's prototype, while Object.create does it from the object directly. See [this](https://stackoverflow.com/questions/4166616/understanding-the-difference-between-object-create-and-new-somefunction)

#### Object's getter and setter

When you try to retrieve the value of a property from an object like so: `x[propName]`, then the getter function gets fired.
for example if you do this:
```javascript

var y = {};
Object.defineProperty(y, {
  'propKey': {
    value: 'propVal',
    get: function(){
      alert("hellow")
    }
  }
})

```

Then when you do y['propKey'], rather than getting 'propVal', you'll get an alert with "hellow".

Another way of defining getter [source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor):

```javascript
var o;
o = { get foo() { return 17; } };
```

## Object's property descriptors

See from [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor)

```javascript
var x = {};
Object.defineProperty(x, 'a', {
 value: 1
}); //when done like this, it assigns writable, enumerable and configurable their default values = false;
Object.getOwnPropertyDescriptor(x, 'a'); //writable, enumerable and configurable their default values = false;

var y = {'a': 1};
Object.getOwnPropertyDescriptor(y, 'a'); ////writable, enumerable and configurable will be true this time;
```

## Configurable, writable, enumerable

[source](https://stackoverflow.com/a/25385794/3248247)

__Writable__: If false, the value of the property can not be changed.

__Configurable__: If false, any attempts to delete the property or change its attributes (Writable, Configurable, or Enumerable) will fail.

__Enumerable__: If true, the property will be iterated over when a user does for (var prop in obj){} (or similar).






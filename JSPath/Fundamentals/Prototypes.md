## Prototypes

#### __proto__ vs Func.prototype

```javascript
function doSomething(){}
doSomething.prototype.foo = "bar";
console.log( doSomething.prototype );

//this will log this:
{
    foo: "bar",
    constructor: ƒ doSomething(),
    __proto__: {
        constructor: ƒ Object(),
        hasOwnProperty: ƒ hasOwnProperty(),
        isPrototypeOf: ƒ isPrototypeOf(),
        propertyIsEnumerable: ƒ propertyIsEnumerable(),
        toLocaleString: ƒ toLocaleString(),
        toString: ƒ toString(),
        valueOf: ƒ valueOf()
    }
}
```
It seemed at first `foo` should be added in the __proto__, but __proto__ is doSomething's prototype object in the prototype chain.

While, if I say doSomething.prototype.foo = "bar", it is defining it's own prototype.
So that when I create an instance from doSomething, I'll see `foo: "bar"` in the instance's __proto__

```javascript
function doSomething(){}
doSomething.prototype.foo = "bar"; // add a property onto the prototype
var doSomeInstancing = new doSomething();
doSomeInstancing.prop = "some value"; // add a property onto the object
console.log( doSomeInstancing );
This
//like this:
{
    prop: "some value",
    __proto__: {
        foo: "bar",
        constructor: ƒ doSomething(),
        __proto__: {
            constructor: ƒ Object(),
            hasOwnProperty: ƒ hasOwnProperty(),
            isPrototypeOf: ƒ isPrototypeOf(),
            propertyIsEnumerable: ƒ propertyIsEnumerable(),
            toLocaleString: ƒ toLocaleString(),
            toString: ƒ toString(),
            valueOf: ƒ valueOf()
        }
    }
}
```

And .prototype property only belongs to functions.

#### Object.create

```javascript

var a = {a: 1}; 
// a ---> Object.prototype ---> null

var b = Object.create(a);
// b ---> a ---> Object.prototype ---> null

//so this is basically similar to this
function a(){}
a.prototype = {a: 1}
var b1 = new a();
// so now b1's __proto__ is a's prototype which is {a: 1} which is what Object.create is doing
// in case of Object.create though there was no need of creating function


console.log(b.a); // 1 (inherited)

var c = Object.create(b);
// c ---> b ---> a ---> Object.prototype ---> null

var d = Object.create(null);
// d ---> null
console.log(d.hasOwnProperty); 
// undefined, because d doesn't inherit from Object.prototype

```


#### Inheritance

So when we're talking about inheritance, say bar has to inherit foo. bar's instance's `__proto__` should be foo's `prototype`.

```javascript
function foo(){}
foo.prototype.fooProp = "fooProp";

function bar(){}


bar.prototype = Object.create(foo.prototype); // one way
bar.prototype = new foo(); // another
Object.setPrototypeOf(bar.prototype, foo.prototype) // another
bar.prototype = {__proto__: foo.prototype} // straight up

bar.prototype.barProp = "barProp";
```



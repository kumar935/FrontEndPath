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


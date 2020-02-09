## let, var

let vs var
- var spans whole function scope, let only the current scope
- var properties defined on global scope add to window properties, but not let
- this example below. it's not assigned undefined like var.

```javscript
function do_something() {
  console.log(bar); // undefined
  console.log(foo); // ReferenceError
  var bar = 1;
  let foo = 2;
}
```

## Intro

## Functional Programming: Imperative vs Declarative

Imperative
- how to accomplish a task. Literally doing what we're telling it to do , like 0s and 1s, in machine language
- Computer is better at reading it
- Directly tell what to do, the HOW

Declarative
- Layers of abstraction over the Imperative literal instructions.
- We're better at reading it
- Tell the framework what we want, framework figures out how to do it, the WHAT


## Provable And Readable

- The parts of code that are done using the proved and trusted way don't need to be re-read.
- Basically no need to re-invent the wheel if it has been done using a trusted way.

__Abstraction__: Abstraction is not hiding details. That's encapsulation. Something in the lines of creating semantic boundaries between intertwined pieces. Not entirely clear.

## Pure Functions and Side Effects

```javascript

function foo(x,y,z,w){
  console.log(x,y,z,w);
}

function bar(x=2, ...args){
  return foo(x,42, ...args);
}

bar();
bar(3,8,11);
bar(...[6,5]);
```

Is foo a function? Nope.
Is bar a function? Kinda. But nope. Gotta be turtles all the way down.

- Arbitrary collection of operations = PROCEDURES.
- All functions are procedures, but all procedures are not functions.

```javascript
function foo(x,y){
  return [x+1, y-1];
}

``` 

A function must have a return keyword. Otherwise it's a procedure. Not just arbitrary return. It has to return a value.

__Side Effects__

```javascript

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

- In the above code, there's no direct output, but a side effect into an external variable.
- Code with side effect causes for example the line which has `f()` makes it impossible to predict the impacts of it. One has to go through lines that are apart from that function's declaration to predict its effects.
- Lot easier to write non functional code.

- But if we were to go ahead and write code without side effects, then it would be indistinguishable from the absence of it. XHR request, writing on filesystem, etc all are side effects.

- So basically avoid them as much as possible, and separate code with side effects and label them.

- React ecosystem already follows this in the way that, dom interaction happens in the end, and all the data transmission, manipulation happens before.















## React Paradigm

These older frameworks, Angular 1 and all, they were inspired from what was used in the backend code MVC architectures I guess, but all in all their purpose was to better than the jQuery spaghetti code.

So he talks about how in case of the older frameworks, like angular 1, there were certain difficulties, like if something broke, then it was hard to trace the problem because there were many moving parts associated with a functionality, such as a controller part, a model part

But react attempts to put everything in one single component. so if something breaks, it's all there.

But then Angular 2 and 4 and other frameworks are also moving in that direction.


## Factories and Props

```javascript
const ce = React.createElement;
//so this is basically for shortening. Eventually we're going to use JSX, but in the lecture he says some people do still use just it.

const titleComponent = function(props){
  return (
    ce('h1', {style: {color: props.color}}, props.title)
  );
}

const myReactComponent = function(){
  ce('div', {id: 'my-react-component'}, (
    ce(titleComponent, {title: "GOT", color: "red"}),
    ce(titleComponent, {title: "Twin Peaks", color: "blue"})
  )})
}

## Prettier

Just a plugin thing for beautifying js, maybe try integrating it in both uniware and the webpack project

## ESLint

ESlint

## Webpack and babel

Basic intro to both

## Configuring Webpack

One cool thing he said:
```javascript
//MyModule
export const x = 1;
export const y = 2;

//different file
import {x} from './MyModule';
```

^ So What webpack will do is what is considered as a misnomer: "Tree shaking", that is removal of dead code. He says that's a misnomer, and actually it is just inclusion of live code, the code that can be reached.

I'm not sure whether webpack does it always, or requires some extra params for it

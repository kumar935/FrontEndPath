## 27th April 17 | react props


### What does this mean: `<Slider {...settings}/>`? React props | Components | Elements

#### # Components [link](https://facebook.github.io/react/docs/components-and-props.html).

So these 2 pieces of code are equivalent:
```javascript
  function Hello(props){
    return <div> Hello, {props.name} </div>;
  }
```
```javascript
class Hello extends React.Component{
  render(){
    <div>Hello, {this.props.name}</div>
  }
}
```
although classes do have additional features yes.

#### # Elements [link](https://facebook.github.io/react/docs/rendering-elements.html)

```javascript
const element = "<div> hello </div>";
```
- This is an element. These are plain objects unlike HTML DOM elements.
- React DOM takes care of matching these objects to HTML DOM elements.
- These are immutable

To render this element, do this:

```javascript
ReactDom.render(
  element,
  document.getElementById("root") //assuming there is a div with id "root"
)
```

> ReactDOM only updates what's necessary comparing current and previous elements and their children.

#### # Back to the original question, answered from [SO link](http://stackoverflow.com/questions/28452358/what-is-the-meaning-of-this-props-in-reactjs) and [fb docs](https://facebook.github.io/react/docs/jsx-in-depth.html#spread-attributes)

`<Slider {...settings}/>`: So this just helps to pass multiple attributes into the component.

So there has to be a `settings` object like this maybe:
```javascript
var settings = {
  something: true,
  someelse: 1,
  whatever: "hmm"
};
```

Now `<Slider {...settings}/>` will translate to `<Slider something=true someelse=1 whatever="hmm"/>. It's called [Spread Attributes](https://facebook.github.io/react/docs/jsx-in-depth.html#spread-attributes)`











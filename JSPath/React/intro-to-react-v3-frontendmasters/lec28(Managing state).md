## Managing state

What happens when you set the value of an input to the state something like this:

```
<input type="text" placeholder="Search" value={this.state.searchTerm}/>
```

The input breaks. It doesn't let you type. 

What happens is, Typing something fires an event that is captured by react which causes a re-render that reverts it back to the original value.

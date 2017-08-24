## Managing state, this.onClickXYZ.bind(this) | Lec 28,29

What happens when you set the value of an input to the state something like this:

```
<input type="text" placeholder="Search" value={this.state.searchTerm}/>
```

The input breaks. It doesn't let you type. 

What happens is, Typing something fires an event that is captured by react which causes a re-render that reverts it back to the original value.


---
```javascript
this.state.searchTerm = 'blah' // this will work, but then react won't know state has been changed, and using setState you tell react to rerender explicitly
```

---

Why we need to do this using `bind`:

```
<input type="text" onChange={this.handleSearchTermChange.bind(this)} placeholder="Search" value={this.state.searchTerm}/>
```

This is bad. Because render gets called a lot. It's creating a function every time event is triggerred.
solution
```
constructor(){

  this.handleSearchTermChange = this.handleSearchTermChange.bind(this)

}
```

## Lec 30

Think of react in terms of deterministic snapshot, as in for given props and states, it would be deterministically be in a certain way. Unlike in jQuery, say you clicked 1 btn, then other btn, then something broke. But in react you get to eliminate the `axis of time`, and be more deterministic.

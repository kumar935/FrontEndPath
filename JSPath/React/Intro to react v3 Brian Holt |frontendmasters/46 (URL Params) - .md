## Sharing State & Updating the Search Components | 47

```javascript
  state = {
    searchTerm: ""
  }
  props: {
    shows: Array<Show>
  }
  
  //for maybe Array of shows
  props: {
    shows?: Array<Show>
  }
  
```

## Finishing the Details Component | 49

Mostly just added the Details Component


## Creating a Header Component | 50

Convention: Own components use Uppercase in the beginning, for custom html items use smaller case in the beginning.

## React Lifecycle methods | 53

Just general lifecycle hooks discussion

## ComponentDidMount() and AJAX Requests | 54

Load the thing without API first.. Then do the API request. Render first, then do the render with API request's response.

## React Dev tools | 57

- Highlight a component, then go to console, and then type `$r` and then enter
- $r.setState() can be done.
- If the highlighted thing is not a component, then type `$0`

## React perf tools | 58

```javascript
shouldComponentUpdate() {
  return false;
}

shouldComponentUpdate(nextProps){
  return this.props.rating !== nextProps.rating
}
```
Might want to do this if there's no state/props change. But it might be dangerous to do it. Only do this when clearly needed. Don't prematurely optimize.

For checking performance:
```javascript
import Perf from 'react-addons-perf'
window.Perf = Perf;
Perf.start();
// then run Perf.stop() and Perf.printWasted() to get a report kind of on how much time wasted on render
// There's also Perf.printInclusive();
// also Perf.printExclusive()
// ^ Inclusive and exclusive of lifecycle methods.
```







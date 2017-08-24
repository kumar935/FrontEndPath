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







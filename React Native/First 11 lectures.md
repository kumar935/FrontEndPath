### First 11 lectures

Mostly setting up and making a simple todo app in react first, and then moving to react native

- Command for seeing devices `adb devices -l`.
- Command for running on android `react-native run-android`
- Not recommended to have hot reload and remote debugging turned on simultaneously



### Styling in React Native | 13

- By default every item is flex. All properties like justify-content, align-items can be used.
- Can't do nested styles.
- Can do hex colors, rgba, css color names
- can use interopolation too: `backgroundColor: rgba(0,0,0, ${opacity})`
- there is margin, padding. The unit is not pixels, it's just unitless sort of.
- You can pass in array of style objects like so: `<View style={[styles.whatever, {backgroundColor: yellow}]}></View>`. Now the styles towards the end would override those before them.
- width, height, position: absolute works. 
- borderRadius, color, fontSize, fontFamily, fontWeight (needs to be string)


Can't use percentages in width. But workaround: 

```
import { Dimensions } from 'react-native';

const {width, height} = Dimensions.get('window');

// so for 50% just do width/2
// but changing orientation screws it up. hmm.
```



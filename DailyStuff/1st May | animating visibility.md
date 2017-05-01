# 1st May | animating visibilty

## How to animate an element from being invisible to visible, then visible to invisible?

> Thanks to [this article](http://www.greywyvern.com/?post=337), where I ended up from this [SO link](http://stackoverflow.com/questions/3331353/transitions-on-the-display-property) , It's done. See this [fiddle](https://jsfiddle.net/thereisn0spoon/d0L65oqn/) I made.

### # Another problem: When using the "+" combinator, the item that shows on hovering, having the cursor over it doesn't let the element stay unhidden. While using the ">" it does stay. 

> Hmm I think, in case of "+" combinator, the element that shows up upon hovering, is not the part of the element upon which the hover conditions should work on. while in case of ">", it stays on because it's basically the child of the original element, so the hover conditions apply on it too. Ugh I should write an example but I'm just being lazy. Maybe later. Just see the difference the example I did in this [fiddle](https://jsfiddle.net/thereisn0spoon/d0L65oqn/) and the example they've shown in [this article](http://www.greywyvern.com/?post=337). I've used the "+" combinator and they've used ">" combinator.

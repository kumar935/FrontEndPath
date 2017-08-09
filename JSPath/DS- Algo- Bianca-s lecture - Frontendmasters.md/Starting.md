## 1.2 OO JS

Stuff about prototypes and all.


## 2 Stacks & Queues

Stacks:

LIFO: Last Item in the stack will be the First item taken off from it: (JUST LIKE JS CALL STACK)

Basically talks about what we learnt in the "What the heck is event loop"


## Exercise: Use a string as a storage with similar functionalities as array:

```javascript
var DELIMITER = "***";
var MAX_CAPACITY = 5;


var Stack = function(){
  	this.storage = "";
}

Stack.prototype.push = function(val){

	//numbers, string, objects, functions, 
	if(this.size() === MAX_CAPACITY){
		alert("Max capacity already reached. Remove element before adding a new one.");
	} else {
		this.storage = this.storage.concat(DELIMITER, val);	
	}

	
};

Stack.prototype.pop = function(){
	// var tempArr = this.storage.split(DELIMITER);
	// tempArr.pop();
	// this.storage = tempArr.join(DELIMITER);
	//^WRONG CAN'T USE ARRAYS
	var str = this.storage.slice(this.storage.lastIndexOf(DELIMITER) + 3);
  	this.storage = this.storage.substring(0, this.storage.lastIndexOf(DELIMITER));
  	return str;
};

Stack.prototype.peek = function() {
  	var str = this.storage.slice(this.storage.lastIndexOf(DELIMITER)+3);
  	return str;
};

Stack.prototype.contains = function(val){
	return this.storage.indexOf(val) !== -1;
}

Stack.prototype.until = function(val){
	val += "";
	if(this.storage.indexOf(val) === -1){
		return "nope";
	} else {
		var ind = this.storage.indexOf(val);
		var strToPop = this.storage.slice(ind + val.length);

		var count = 0, pos=0;
		while(true){

			if(strToPop.indexOf(DELIMITER, pos) !== -1){
				count = count + 1;
				pos = strToPop.indexOf(DELIMITER, pos) + DELIMITER.length;
			} else{
				break;
			}

		}
		return count;

	}
}

Stack.prototype.size = function(){
	var count = 0, pos=0;
	while(true){

		if(this.storage.indexOf(DELIMITER, pos) !== -1){
			count = count + 1;
			pos = this.storage.indexOf(DELIMITER, pos) + DELIMITER.length;
		} else{
			break;
		}

	}
	return count;
};

var myWeeklyMenu = new Stack();

myWeeklyMenu.push("RedBeans");

```


## Queues

FIFO: __First__ Item added __Into__ the queue will be the __First__ one taken __Out__ of the queue.

compared to JS callstack, it will be the first item that gets removed rather than the last item in case of JS callstack.

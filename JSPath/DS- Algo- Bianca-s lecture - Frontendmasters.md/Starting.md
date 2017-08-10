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





//==============================================



function Queue(capacity) {
	capacity = capacity ? capacity : 0;
	this.storage = {};
	this.capacity = capacity;
	this.count = 0;
	for(var i=0; i<capacity; i++){
		this.storage[i] = undefined;
	}
}

Queue.prototype.enqueue = function(value) {
	if(this.count === this.capacity){
		alert("nope");
		return;
	}
 	for(var i=0; i<this.capacity; i++){
 		if(this.storage[i] === undefined){
 			this.storage[i] = value;
 			this.count++;
 			break;
 		}
 	}
};
// Time complexity:

Queue.prototype.dequeue = function() {
  	for(var i=0; i<this.capacity-1; i++){
  		this.storage[i] = this.storage[i+1]
  	}
  	this.count--;
  	this.storage[this.capacity-1] = undefined;
};
// Time complexity:

Queue.prototype.peek = function() {
 	return this.storage[0];
};

Queue.prototype.count = function() {
 	return this.count;
};

Queue.prototype.contains = function(val){
	for(var i=0; i<this.capacity; i++){
		if(this.storage[i] === val){
			return true;
		}
	}
	return false;
}

Queue.prototype.until = function(val){
	for(var i=0; i<this.capacity; i++){
		if(this.storage[i] === val){
			return i;
		}
	}
	return "nope";
}


//==== MY SOLUTION, but it like creates an object with items having undefined as values. We don't want that I guess. Trying the right solution below:

function Queue(capacity){
	this._capacity = capacity || Infinity;
	this._storage = {};
	this._tail = 0;
	this._head = 0;
}

Queue.prototype.enqueue = function(val){
	if(this.count() < this._capacity){
		this._storage[this._tail++] = val;	
	} else {
		return "Max capacity reached";
	}
}

Queue.prototype.peek = function() {
 	return this.storage[this._head];
};

Queue.prototype.contains = function(val){
	for(var i=this._head; i<this._tail; i++){
		if(this._storage[i] === val){
			return true;
		}
	}
	return false;
}

Queue.prototype.dequeue = function(){
	if(this._head < this._tail){
		delete this._storage[this._head++]	
	} else {
		return "Empty storage";
	}
}

Queue.prototype.until = function(val){
	for(var i=this._head; i<this._tail; i++){
		if(this._storage[i] === val){
			return i-this._head;
		}
	}
	return "does not exist in storage";
}

Queue.prototype.count = function(){
	return this._tail - this._head;
}



```


## Queues

FIFO: __First__ Item added __Into__ the queue will be the __First__ one taken __Out__ of the queue.

compared to JS callstack, it will be the first item that gets removed rather than the last item in case of JS callstack.

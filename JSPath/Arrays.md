## Working with arrays

### Array.prototype.every
```javascript
function containsOnlyOddNumbers(element, index, array){
  return element%2 !== 0;
}
[3,5,7,9].every(containsOnlyOddNumbers) //will return true
[4,3,5,6].every(containsOnlyOddNumbers) //will return false
```

[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every), [Question on codefights](https://codefights.com/arcade/intro/level-5/XC9Q2DhRRKQrfLhb5/solutions/pMJHP9KJ73SntcGR5)

### Array.prototype.some
```javascript
function containsOneOddNumber(element, index, array){
  return element%2 !== 0;
}
[24,55,34,22].some(containsOneOddNumber); //will return true
[4,54,34,2].some(containsOneOddNumber); //will return false
```

### Ways to add items of array:
```javascript
[1,2,3,4,5].reduce(function(sum,next){ return sum + next }); //will return 15
```

### reduceRight
```javascript
['1','2','3'].reduceRight(function(accumulator, next){return accumulator + next}); // will return '321';
['1','2','3'].reduce(function(accumulator, next){return accumulator + next}); // will return '123';
```

### More array methods
```javascript
//So ways to create new Array of certain length
var arr1 = Array.apply(0, new Array(6)).map((v,i) => i); //[0, 1, 2, 3, 4, 5]
var arr2 = new Array(5).fill(0); //[0,0,0,0,0]

//fill
[1,2,3,4,5].fill("yo"); //["yo","yo","yo","yo","yo"]

//findIndex and find
function isDivisibleBy3(num){
  return num%3===0;
}
[1,2,3,4,5,6].findIndex(isDivisibleBy3); //will give the index of number divisible by 3 = 2
[1,2,3,4,5,6].find(isDivisibleBy3); //will give the number itself which is divisible by 3 = 3

//includes
[1,3,4,5,6].includes(4); //true
[1,3,4,5,6].includes(4,4); //false (the second parameter is fromIndex, so 4 is not present after the 4th index including the item on 4th index)

//lastIndexOf
[1,2,3,2,1].lastIndexOf(2); //gives 3 which is the index of 2 from the last of the array
[1,2,3,2,1].indexOf(2); //gives 1

//splice vs slice
var arr1 = [1,2,3,4,5];
console.log(arr.splice(2,3), arr); //outputs spliced part [3,4,5] arr becomes [1,2]
var arr2 = [1,2,3,4,5];
console.log(arr.slice(2,3), arr); //outputs sliced part [3], arr remains same

//push, unshift & pop, shift
[1,2,3,4,5].push(100); //output = 6 (length of final array = [1,2,3,4,5,100])
[1,2,3,4,5,100].unshift(30); //output = 6 (length of final array = [30,1,2,3,4,5,100])

[30,1,2,3,4,5,100].pop(); //output = 100 final array = [30,1,2,3,4,5]
[30,1,2,3,4,5].shift(); //output = 30 final array = [1,2,3,4,5]


//Array.from
console.log("================", "Array.from");
var someNumbers = Array.from({length: 10}, (v,i) => i);
var nameLetters = Array.from("animesh"); //can also get array from Set, Map
console.log(someNumbers, nameLetters);

//Array.isArray
console.log("================", "Array.isArray");
console.log(Array.isArray(someNumbers));//true
console.log(Array.isArray({"0": "abc"}));//false
console.log(Array.isArray({0: "abc"}));//false
console.log(Array.isArray(["abc"]));//true

```

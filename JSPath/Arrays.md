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

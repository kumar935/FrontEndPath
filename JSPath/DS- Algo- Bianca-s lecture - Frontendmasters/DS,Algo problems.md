They asked me this one on one of the interviews:

reverse string retaining the positions of certain characters. I made this retaining positions of numbers while reversing strings:

```javascript
function revStr(str){
	var wall = str.length;
	var strArr = str.split("");
	for(var i=0; i<wall; i++){
		if(isNaN(Number(strArr[i]))){
			if(isNaN(Number(strArr[wall-1]))){
				swap(strArr, i, wall-1);
			}
			wall--;
		}
	}
	return strArr.join("");
}
function swap(arr, i1, i2){
  var temp = arr[i1];
  arr[i1] = arr[i2];
  arr[i2] = temp;
}

```

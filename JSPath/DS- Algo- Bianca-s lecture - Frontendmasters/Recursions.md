## Recursions

```javascript

var count = 0;
function loopNTimes(n){
  if(count++ === n){
    return "done";
  } else {
    return loopNTimes(n);
  }
}

//but there's better way

function loopNTimes(n){
  console.log("n is", n);
  if(n <= 1){
    return "done";
  } else {
    return loopNTimes(n-1)
  }
}

```


## Bubble sort, Selection sort

```javascript


function swapArrIndices(arr, index1, index2){
	if(index1 === index2) return;
	arr[index1] = arr[index1] + arr[index2];
	arr[index2] = arr[index1] - arr[index2];
	arr[index1] = arr[index1] - arr[index2];
}


function bubbleSort(arr){
	var noSwapsMade = false;
	for(var i=0; i<arr.length; i++){
		console.log("i", i);
		if(noSwapsMade) break;
		for(var j=0; j<arr.length - 1; j++){
			console.log("j", j);
			noSwapsMade = true;
			if(arr[j] > arr[j+1]){
				noSwapsMade = false;
				swapArrIndices(arr, j, j+1);
			}
		}
	}
	return arr;
}



function selectionSort(arr){
	var maxIndex = 0
	for(var i=0; i<arr.length; i++){

		for(var j=0; j<arr.length - i; j++){

			if(arr[j] > arr[maxIndex]){
				maxIndex = j;
			}

		}
		swapArrIndices(arr, maxIndex, arr.length-i-1);
		maxIndex = 0;
	}
	return arr;

}


```

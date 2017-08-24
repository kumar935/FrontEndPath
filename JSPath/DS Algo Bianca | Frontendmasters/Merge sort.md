### Merge sort

#### pseudo coding merge routine:

We have 2 sorted arrays, and we're comparing each elements of the sorted array

Rpointer = 0
Lpointer = 0

Loop until L.ln === Lpr and R.ln === Rpr
  if L[Lpointer]>R[Rpointer]
    push R[Rpointer] to Output array & Rpointer++
  else 
    L[Lpointer] to Output array & Lpointer ++
  
 ```javascript
 
 //This one doesn't work:
 function merge(lArr, rArr){
  var lIndex = 0, rIndex = 0;
  var result = [];
  while(result.lengh < (lArr.length + rArr.length)){
    if(lIndex === lA rr.length){
      result = result.concat(rArr.slice(rIndex));
    } else if(rIndex === rArr.length){
      result = result.concat(lArr.slice(lIndex));
    } else if(lArr[lIndex] <= rArr[rIndex]){
      result.push(lArr[lIndex++])
    } else {
      result.push(rArr[rIndex++])
    }
  }
  return result;
 }
 
 function mergeSort(list){
  if(list.length < 2) return list;
  var lArr = mergeSort(list.slice(0, list.length/2));
  var rArr = mergeSort(list.slice(list.length/2, list.length));
  return merge(lArr, rArr);
 }
 
 
 ```
 
 
 ### Quick sort
 
 Pseudo code:
 
 partition(arr, first, last)
  pivotLoc = first
  pivot = arr[last]
  loop from first to last
    compare pivot to arr[pivotLoc]
    if(pivot > arr[pivotLoc]
      incrememnt pivotLoc
    else
      swap pivot with arr[pivotLoc]
      swap pivot with arr[arr.ln-2] //??
    
    
  
 
 
 

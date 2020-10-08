`arr.sort(fn)`

To use our own sorting order, we need to supply a function as the argument of `arr.sort()`.

The function should compare two arbitrary values and return:

```javascript
  function compareNumeric(a, b) {
    if ( a > b ) return 1;
    if ( a == b ) return 0;
    if ( a < b ) return -1;
    }
    
  let arr = [6, 3, 87, 45, 34, 65, 54];
  
  arr.sort(compareNumeric);  // return sorted array
  ```
  
  ## With arrow function ->
  
```javascript
 
  let arr = [6, 4, 65, 45, 54, 76, 44]; 
 
  arr.sort( (a, b) => {
    if ( a > b ) return 1;
    if ( a == b ) return 0;
    if ( a < b ) return -1;
    });
```

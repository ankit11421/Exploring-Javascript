# A word about "length"

The `length` property automatically updates when we modify the array. To be precise, it is actually not the count of values in the array, but the greatest numeric index plus one.

For instance, a single element with a large index gives a big length.

```javascript
        let fruits = [];
        
        fruits[123] = "Apple";
        
        alert( fruits.length ); //124
```      
     
Another interesting thing about the `length` property is that it's writable.

If we increase it manually, nothing interesting happens. But if we decrease it, the array is truncated. The process is irreversible, here’s the example:

```javascript
                let arr = [1, 2, 3, 4, 5];

                arr.length = 2; // truncate to 2 elements
                alert( arr ); // [1, 2]

                arr.length = 5; // return length back
                alert( arr[3] ); // undefined: the values do not return
```                

So, the simplest way to clear the array is: `arr.length = 0;`.



# Summary

Array is a special kind of object, suited to storing and managing ordered data items.
- The declaration:

```javascript
                // square brackets (usual)
                let arr = [item1, item2...];
                
                // new Array (exceptionally rare)
                let arr = new Array(item1, item2...);
```

  The call to `new Array(number)` creates an array with the given length, but without elements.
  - The length property is the array length or, to be precise, its last numeric index plus one. It is auto-adjusted by array methods.
  
  - If we shorten length manually, the array is truncated.
  
 We can use an array as a deque with the following operations:
 - push(...items) adds items to the end.
 
 - pop() removes the element from the end and returns it.
 
 - shift() removes the element from the beginning and returns it.
 
 - unshift(...items) adds items to the beginning.

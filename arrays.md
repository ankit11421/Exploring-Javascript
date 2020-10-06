The `length` property automatically updates when we modify the array. To be precise, it is actually not the count of values in the array, but the greatest numeric index plus one.

For instance, a single element with a large index gives a big length.

```javascript
        let fruits = [];
        fruits[123] = "Apple";
        alert( fruits.length ); //124
        
        ```

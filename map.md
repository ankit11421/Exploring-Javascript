# Map -
  Map is the collection of keyed data items, just like an `Object` . But the main difference is that `Map` allows keys of any type.
  
### Methods and properties are - 
  `new Map()` - Creates the map.
  
  `map.set(key, value)` - Stores the value by the key.
  
  `map.get(key)` - returns the value by the key, `undefined` if `key` doesn't exist in map.
  
  `map.has(key)` - returns `true` if the `key` exists, `false` otherwise.
  
  `map.delete(key)` - removes the value by the key.
  
  `map.clear()` - removes everything from the map.
  
  `map.size` - returns the current element count.
  
  
  For instance:
  
  ```javascript
  let map = new Map();
  
  map.set("1", "str1"); // a string key
  
  map.set(1, "num1"); // a numeric key
  
  map.set(true, "bool1"); // a boolean key
  
  map.get("1"); // 'str1'
  
  map.get(1); // 'num1'
  
  
  map.size // 3
  ```
  
  ### Map can also use objects as keys.
  
  For instance:
  
  ```javascript
  
  let john = { name: "John" };
  
  // for every user, let's store their visits count
  let visitsCountMap = new Map();
  
  // john is the key for the map
  visitsCountMap.set(john, 123);
  
  alert( visitsCountMap.get(john) ); //123
  ```
  
  ### Chaining:
  
  Every `map.set` call returns the map itself, so we can "chain" the calls:
  
  ```javascript
  
  map.set("1", "str1")
     .set(1, "num1")
     .set(true, "bool1");
 ```   
     
  ## Iteration over Map
  For looping over a `map`, there are 3 methods:
  -  `map.keys()` - returns an iterable for keys.
  
  -  `map.values()` - returns an iterable for values.
  
  -  `map.entries()` - returns an iterable for entries `[key, value]`, it's used by default in `for..of`.
  
  
  For instance:
  
  ```javascript
  
  let recipeMap = new Map([
      ['cucumber', 500],
      ['tomatoes', 350],
      ['onion', 100]
     ]);
     
 // iterate over keys (veg)
 for (let veg of recipeMap.keys()) {
    alert( veg ); // cucumber, tomatoes, onion
 }
 
 // iterate over values (amounts)
 for (let amount of recipeMap.values()) {
    alert(amount); // 500, 350, 100
 }
 
 // iterate over [key, values] entries
 for (let entry of recipeMap) { // the same as of recipeMap.entries()
    alert( entry ); // cucumber, 500 (and so on)
}
```

### :information_source: The insertion order is used
The iteration goes in the same order as the values were inserted. `Map` preserves this order, unlike a regular `Object`.


Besides that, `Map` has a built-in `forEach` method, similar to `Array`:
```javascript
    // runs the function for each (key, value) pair
    recipeMap.forEach( (value, key, map) => {
      alert(`${key}: ${value}`);  // cucumber: 500 etc
    });
```

## Object.entries: Map from Object

When a `Map` is created, we can pass an array (or another iterable) with key/value pairs for initialization, like this:

```javascript
// array of [key, value] pairs
let map = new Map([
    ['1', 'str1'],
    [1, 'num1'],
    [true, 'bool1']
  ]);
  
  alert( map.get('1') ); // str1
 ```
 If we have a plain object, and we'd like to create a `Map` from it, then we can use built-in method `Object.entries(obj)`
 that returns an array of key/value pairs for an object exactly in that format.
 
 So we can create a map from an object like this:
 
 ```javascript
 let obj = {
    name: "John",
    age : 30
 };
 
 let map = new Map(Object.entries(obj));
 
 alert( map.get('name') ); // John
 
```


 

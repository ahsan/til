# Common operations on arrays and strings

## Creating an array
- Of length of 'L'
```JavaScript
arr = Array(L);
```
- Initialized with some value 'x'
```JavaScript
arr = Array(L).fill(x);
```
- Of a range of integers from 0 to L
```JavaScript
arr = Array.from([...Array(L)], (x,i) => i);
```

## Operations on elements
- Remove first element.
```JavaScript
firstElement = arr.shift()
```
Removes the first element and shifts the array to the left.
- Add an element 'x' to the beginning
```JavaScript
arr.unshift(x)
```
- Validate that all the elements of an array satisfy some condition
```JavaScript
arr.every( function(i) {
    return i > 2
});
```

## Push elements of one array into another
```JavaScript
arr1 = arr1.concat(arr2);
```
or
```JavaScript
Array.prototype.push.apply(arr1, arr2);
```

## Sort an array
By default, sort is in ascending order.
```JavaScript
arr.sort()
arr.sort(compareFunc)
```
Example:
```JavaScript
compareFunc = function (a, b) {
    return a-b;
}

arr.sort(compareFunc)
```

## Map, Filter, Reduce
```JavaScript
// Adds 2 to all values of arr
arr = arr.map( function(i) { return i + 2 });

// arr2 contains only those elements of arr that are greater than 2
arr2 = arr.filter( function(i) { return i > 2 });

// returns sum of all the elements of arr
sum = arr.reduce( (a, b) => { return a+b });

```


## Reverse a string
```JavaScript
reverse = str.split('').reverse().join('');
```
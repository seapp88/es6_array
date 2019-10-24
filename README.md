 - [Russian version](https://github.com/seapp88/es6_array/blob/master/README_RU.md)

# Array intersection, difference and union in ES6

For all the examples, we have two arrays, A `let arrA=[1,3,4,5]` & B `let arrB=[1,2,5,6,7]`

## Intersection
![js array intersection](images/intersection.png?raw=true "Intersection")
The intersection will give us the elements that both arrays share in common, in this case the result must be `[1,5]`.

`let intersection = arrA.filter(x => arrB.includes(x));`

## Difference
![js array difference](images/difference.png?raw=true "Difference")
The difference will output the elements from array A that are not in the array B. The result will be `[3,4]`.

`let difference = arrA.filter(x => !arrB.includes(x));`

## Symmetrical Difference
![js array symmetrical difference](images/s_difference.png?raw=true "Symmetrical Difference")
In this case, you will get an array containing all the elements of arrA that are not in arrB and vice-versa, so the result should be `[2,3,4,6,7]`.

`let difference = arrA.filter(x => !arrB.includes(x)).concat(arrB.filter(x => !arrA.includes(x)));`

## Union
![js array union](images/union.png?raw=true "Union")
The union must be the simplest of them all, at the end, the result should be all the elements from A, all from B, or both like this `[1,2,3,4,5,6,7]`.

`let union = [...arrA, ...arrB];`

But, there is a problem is that if we use spread operator, we will get elements duplicated, so it’s no theoretically an union. For doing this we have can use a Set to help us out:

`let union = [...new Set([...arrA, ...arrB)];`

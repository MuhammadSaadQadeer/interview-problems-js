# interview-problems-js

- Interview problems and their solutions using JavaScript 
- If you have ever faced an interesting problem feel free to open a Pull Request
- If you think there are more solutions to a single problem open a Pull Request
- Feel free if you want to add or comment on anything
## Problem Statement 1

Determine if a string has unique chracters ?

```
function isUniqueChars(str) {
  return new Set(str).size === str.length
}
```

## Problem Statement 2

Given array of numbers e.g `arr = [1,2,3,4,5,6,7,8,9,10,11,12,13]` display the array in below format ?

    Input

    let arr = [1,2,3,4,5,6,7,8,9,10,11,12,13]

     0 < arr.length < 2000

    Output

    1
    2,3
    4,5,6
    7,8,9,10
    11,12,13

    Solution

    ```javascript
    let i = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]; //Original Array
    let z = i; //Making the copy of original array

    for (let j = 1; j < z.length; j++) {
    if (i.length !== 0) {
        splitAndPrint(j, i);
    }
    }

    function splitAndPrint(itr, arr) {
    let j = arr.splice(0, itr);
    console.log(j + "\n");
    }```

## Problem Statement 3

Check Permutation: Given two strings, write a method to decide if one is a permutation of the other.

- Two strings are premutations of each other if
  - they have same length
  - they have same set of characters but with different order

#### Sort the both strings and compare them if they are equal they are permutation of each other

```
function isPermutations(stra, strb) {
  if (stra.length != strb.length) {
    return false
  }
  let a = stra.split("").sort();
  let b = strb.split("").sort();
  return JSON.stringify(a) === JSON.stringify(b)
}

isPermutations("abcd", "dcba") // true
```

## Problem Statement 4

Write a method to replace all spaces in a string with '%20

```
function replaceSpace(str) {
  return str.split(" ").join('%20')
}

replaceSpace("Mr John Smith  ,13")

// Mr%20John%20Smith%20%20,13
```

## Problem Statement 5

Assume you have a method isSubst ring which checks if one word is a substring of another. Given two strings, 51 and 52, write code to check if 52 is a rotation of 51 using only one call to isSubstring (e.g., " waterbottle" is a rotation of" erbottlewat" ).

## Problem Statement 6

Zero Matrix: Write an algorithm such that if an element in an MxN matrix is 0, its entire row and column are set to 0.

```
let m = [ [ 1, 2, 3 ], [ 4, 5, 6 ], [ 7, 8, 0 ] ] 

function zeroMatrix(rows, cols, matrix) {
  let rowcord;
  let colcord;
  if (rows != cols) {
    return
  }
  // Finding the co-ordinates of 0 element
  for (let i = 0; i < rows; i++) {
    for (let j = 0; j < cols; j++) {
      if (matrix[i][j] == 0) {
        rowcord = i;
        colcord = j

      }
    }
  }

  // Replacing the row and count
  for (let i = 0; i < rows; i++) {
    for (let j = 0; j < cols; j++) {
      matrix[i][colcord] = 0
      matrix[rowcord][j] = 0
    }
  }
  console.log(matrix) // [ [ 1, 2, 0 ], [ 4, 5, 0 ], [ 0, 0, 0 ] ] 
}
```

## Problem Statement 1

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

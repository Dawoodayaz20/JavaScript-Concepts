# Arrays methods:

1. **array.length():** returns the number of elements in the array.

2. **array.toString():** converts the given value into the string with each element separated by commas.
   
   ```javascript
   let a  = ["HTML", "CSS", "JS", "React"];
   let s = a.toString();
   console.log(s);  //Output: HTML,CSS,JS,React
   ```

3. **array.join():** creates and returns a new string by concatenating all elements of an array. It uses a specified separator between each element in the resulting string.
   
   ```javascript
   let a = ["HTML", "CSS", "JS", "React"];
   console.log(a.join('|'));  //Output: HTML|CSS|JS|React
   ```

4. **array.delete():** used to delete the given value which can be an object, array, or anything.

5. **array.concat()**: used to concatenate two or more arrays and it gives the merged array. E.g: `a1.concat(a2, a3);`

6. **array.flat():** used to flatten the array i.e. it merges all the given array and reduces all the nesting present in it.

7. **Array.push():** used to add an element at the end of an Array.

8. **array.unshift():** used to add elements to the starting of an Array.

9. **array.pop():** used to remove elements from the end of an array.

10. **array.shift():** used to remove elements from the beginning of an array.

11. **array.splice():** used to Insert and Remove elements in between the original array.
    
    ```javascript
    let a = [20, 30, 40, 50];
    a.splice(1, 3);
    a.splice(1, 0, 3, 4, 5);
    console.log(a); //Output: [20,3,4,5]
    
    // The first a.splice(1, 3) removes 3 elements (30, 40, 50) starting at index 1. The array becomes [20].
    // The second a.splice(1, 0, 3, 4, 5) inserts 3, 4, and 5 at index 1 without removing anything. The array becomes [20, 3, 4, 5].
    ```

12. **array.slice():** returns a new array containing a portion of the original array, based on the start and end index provided as arguments.

13. **array.some():** checks whether at least one of the elements of the array satisfies the condition checked by the argument function.
    
    ```javascript
    const a = [1, 2, 3, 4, 5];
    let res = a.some((val) => val > 4);
    console.log(res);  //Output: true
    ```

14. **array.map():** creates an array by calling a specific function on each element present in the parent array. It is a non-mutating method. It returns a **new array** of the exact same length

15. **array.filter():** creates a new array with all elements that pass the test implemented by the provided function. It does not modify the original array.

16. **array.reduce():** used to reduce the array to a single value and executes a provided function for each value of the array (from left to right) and the return value of the function is stored in an accumulator.
    
    ```javascript
    let a = [88, 50, 25, 10];
    let sub = a.reduce(geeks);
    
    function geeks(tot, num) {
        return tot - num;
    }
    console.log(sub);
    ```

17. **array.reverse():** used to reverse the order of elements in an array. It modifies the array in place and returns a reference to the same array with the reversed order.

18. **array.values():** returns a new Array Iterator object that contains the values for each index in the array.
    
    ```javascript
    const a = ["Apple", "Banana", "Cherry"];
    const res = a.values();
    
    for (const value of res) {
        console.log(value
    );
    }
    
    //Output: \nApple    \nBanana    \nCherry    
    ```

# Activity13-SpaceConstraints

Task 1: Following is the 'Word Builder' algorithm. Describe its space complexity in terms of Big O.

function wordBuilder(array) { 
		let collection = [];
		for(let i = 0; i < array.length; i++) { 
				for(let j = 0; j < array.length; j++) {
						if (i !== j) {
								collection.push(array[i] + array[j]);
						}
				}
		}
		return collection; 
}

Answer: O(n²), because it stores every possible pair of two different elements.
For an array of size n, it stores about n × (n − 1) strings → quadratic space.

Task 2: Following is a function that reverses an array. Describe its space complexity in terms of Big O:

function reverse(array) { 
		let newArray = [];
		for (let i = array.length - 1; i >= 0; i--) { 
				newArray.push(array[i]);
		}
		return newArray;
}

Answer: O(n), because it creates a new array of the same size as the input.

Task 3: Create a new function to reverse an array that takes up just O(1) extra space.

#include <vector>
using namespace std;

void reverseInPlace(vector<int>& arr) {
    int left = 0;
    int right = arr.size() - 1;

    while (left < right) {
        int temp = arr[left];
        arr[left] = arr[right];
        arr[right] = temp;

        left++;
        right--;
    }
}


Uses only O(1) space because it only uses a couple of variables (left, right, temp), not a second array.

Task 4: Following are three different implementations of a function that accepts an array of numbers and returns an array containing those numbers multiplied by 2. For example, if the 
input is [5, 4, 3, 2, 1], the output will be [10, 8, 6, 4, 2].

function doubleArray1(array) { 
	let newArray = [];

	for(let i = 0; i < array.length; i++) { 
		newArray.push(array[i] * 2);
	}
	return newArray; 
}


function doubleArray2(array) {
	for(let i = 0; i < array.length; i++) {
  	array[i] *= 2;
  }
	return array; 
}


function doubleArray3(array, index=0) { 
	if (index >= array.length) { return; }
  array[index] *= 2;
  doubleArray3(array, index + 1);
	return array; 
}

Fill in the table that follows to describe the efficiency of these three versions in terms of both time and space:

Version	   Time complexity	Space complexity
Version 1	 ?	               ?
Version 2	 ?	               ?
Version 3	 ?	               ?

Answer:

| Version        | Time Complexity | Space Complexity |
| -------------- | --------------- | ---------------- |
| Version 1      | O(n)            | O(n)             |
| Version 2      | O(n)            | O(1)             |
| Version 3      | O(n)            | O(n)             |

Version 1

Creates a new array, loops through the whole input.

Time: O(n)

Space: O(n) (because of the new array)

Version 2

Modifies the array in place.

Time: O(n)

Space: O(1) (only uses a loop counter)

Version 3

Uses recursion, processes one element per call.

Time: O(n)

Space: O(n) because recursion builds a call stack of size n.

Video: https://youtu.be/XM0hXt53ug8



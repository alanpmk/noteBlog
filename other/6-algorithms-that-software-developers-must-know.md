---
cover: >-
  https://images.unsplash.com/photo-1688637079192-8eb1d6e4a30b?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTAwNzg4MTB8&ixlib=rb-4.0.3&q=85
coverY: -93
---

# ➕ 6 Algorithms that Software Developers Must Know

## 1. Sorting Algorithms <a href="#8669" id="8669"></a>

**Bubble Sort** in JavaScript:

{% code overflow="wrap" %}
```javascript
function bubbleSort(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        const temp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = temp;
      }
    }
  }
  return arr;
}
```
{% endcode %}

**Merge Sort** in JavaScript:

```javascript
function mergeSort(arr) {
  if (arr.length === 1) {
    return arr;
  }
  
  const mid = Math.floor(arr.length / 2);
  const left = arr.slice(0, mid);
  const right = arr.slice(mid);
  
  return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
  const result = [];
  let i = 0;
  let j = 0;
  
  while (i < left.length && j < right.length) {
    if (left[i] < right[j]) {
      result.push(left[i++]);
    } else {
      result.push(right[j++]);
    }
  }
  
  return result.concat(left.slice(i)).concat(right.slice(j));
}
```

**Quick Sort** in JavaScript:

```javascript
function quickSort(arr, left = 0, right = arr.length - 1) {
  if (left < right) {
    const pivotIndex = partition(arr, left, right);
    quickSort(arr, left, pivotIndex - 1);
    quickSort(arr, pivotIndex + 1, right);
  }
  return arr;
}

function partition(arr, left, right) {
  const pivot = arr[right];
  let i = left - 1;
  
  for (let j = left; j < right; j++) {
    if (arr[j] <= pivot) {
      i++;
      swap(arr, i, j);
    }
  }
  swap(arr, i + 1, right);
  return i + 1;
}

function swap(arr, i, j) {
  const temp = arr[i];
  arr[i] = arr[j];
  arr[j] = temp;
}
```

**Heap Sort** in JavaScript:

```javascript
function heapSort(arr) {
  buildMaxHeap(arr);

  for (let i = arr.length - 1; i >= 1; i--) {
    swap(arr, 0, i);
    heapify(arr, i, 0);
  }
  return arr;
}

function buildMaxHeap(arr) {
  const n = arr.length;
  for (let i = Math.floor(n / 2) - 1; i >= 0; i--) {
    heapify(arr, n, i);
  }
}
function heapify(arr, n, i) {
  let largest = i;
  const left = 2 * i + 1;
  const right = 2 * i + 2;

  if (left < n && arr[left] > arr[largest]) {
    largest = left;
  }

  if (right < n && arr[right] > arr[largest]) {
    largest = right;
  }

  if (largest !== i) {
    swap(arr, i, largest);
    heapify(arr, n, largest);
  }
}

function swap(arr, i, j) {
  const temp = arr[i];
  arr[i] = arr[j];
  arr[j] = temp;
}
```

It’s important to note that these algorithms have different time and space complexities, and some may be better suited for specific use cases over others. When choosing a sorting algorithm, it’s important to consider the size of the data, the desired time complexity, and the desired space complexity.

## 2. Searching Algorithm <a href="#45d2" id="45d2"></a>

Here is an example of binary search, breadth-first search, and depth-first search in JavaScript:

**Binary Search** in JavaScript:

```javascript
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;
  
  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) {
      return mid;
    } else if (arr[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return -1;
}
```

**Breadth-First** in JavaScript:

```javascript
// Breadth-First Search
function breadthFirstSearch(root, target) {
  const queue = [root];
  
  while (queue.length > 0) {
    const node = queue.shift();
    if (node.value === target) {
      return node;
    }
    queue.push(...node.children);
  }
  
  return null;
}
```

**Depth-First** in JavaScript:

```
// Depth-First Search
function depthFirstSearch(root, target) {
  if (root.value === target) {
    return root;
  }
  
  for (const child of root.children) {
    const result = depthFirstSearch(child, target);
    if (result) {
      return result;
    }
  }
  
  return null;
}
```

In the example above, `binarySearch` takes an array `arr` and a target value, and returns the index of the target value in the array if it exists, or -1 if it does not exist.

`breadthFirstSearch` takes a tree represented by a root node and a target value, and returns the node in the tree with the target value if it exists, or null if it does not exist.

`depthFirstSearch` takes a tree represented by a root node and a target value, and returns the node in the tree with the target value if it exists, or null if it does not exist.

a. Example of **how to use the `binarySearch` function** in JavaScript:

```javascript
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const target = 6;

const result = binarySearch(arr, target);
if (result === -1) {
  console.log(`${target} not found in the array`);
} else {
  console.log(`${target} found at index ${result}`);
}
```

In this example, the `binarySearch` function is called with an array `arr` and a target value of `6`. The function returns `5`, which is the index of `6` in the array. The code then checks the result and outputs the appropriate message to the console.

b. Example of **how to use the `breadthFirstSearch` function** in JavaScript:

```javascript
const tree = {
  value: 1,
  children: [
    {
      value: 2,
      children: [
        { value: 4, children: [] },
        { value: 5, children: [] },
      ]
    },
    {
      value: 3,
      children: [
        { value: 6, children: [] },
        { value: 7, children: [] },
      ]
    },
  ]
};
const target = 5;

const result = breadthFirstSearch(tree, target);
if (!result) {
  console.log(`${target} not found in the tree`);
} else {
  console.log(`${target} found with value ${result.value}`);
}
```

In this example, the `breadthFirstSearch` function is called with a tree represented by a root node and a target value of `5`. The function returns the node in the tree with a value of `5`, which is a child node of the root node. The code then checks the result and outputs the appropriate message to the console.

c. Example of **how to use the `depthFirstSearch` function** in JavaScript:

```javascript
const tree = {
  value: 1,
  children: [
    {
      value: 2,
      children: [
        { value: 4, children: [] },
        { value: 5, children: [] },
      ]
    },
    {
      value: 3,
      children: [
        { value: 6, children: [] },
        { value: 7, children: [] },
      ]
    },
  ]
};
const target = 5;

const result = depthFirstSearch(tree, target);
if (!result) {
  console.log(`${target} not found in the tree`);
} else {
  console.log(`${target} found with value ${result.value}`);

```

In this example, the `depthFirstSearch` function is called with a tree represented by a root node and a target value of `5`. The function returns the node in the tree with a value of `5`, which is a child node of the root node. The code then checks the result and outputs the appropriate message to the console.

## 3. Dynamic Programming <a href="#e414" id="e414"></a>

Dynamic programming is a technique for solving problems by breaking them down into smaller sub-problems and reusing the solutions to these sub-problems to find the solution to the original problem. The key idea behind dynamic programming is to avoid redundant calculations by memorizing intermediate results and reusing them as needed.

Here is an example of how to use dynamic programming in JavaScript to solve the problem of finding the nth Fibonacci number:

```javascript
function fibonacci(n, memo = {}) {
  if (n <= 0) return 0;
  if (n === 1) return 1;
  if (memo[n]) return memo[n];
  memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo);
  return memo[n];
}
console.log(fibonacci(10));
```

In this example, the `fibonacci` function uses a memoization technique to store intermediate results in an object passed as an argument. This allows the function to reuse the solutions to sub-problems, improving the time complexity of the calculation. The function returns the nth Fibonacci number, which can be accessed by calling `fibonacci(10)` in this example.

## 4. Recursion Algorithm <a href="#4916" id="4916"></a>

Recursion is a technique where a function calls itself in order to solve a problem by dividing it into smaller sub-problems. The sub-problems are solved recursively, and the solutions to the sub-problems are combined to find the solution to the original problem. Recursion is useful for solving problems that have a recursive structure, where the solution to the problem can be expressed in terms of solutions to smaller instances of the same problem.

Here is an example of how to use recursion in JavaScript to calculate the factorial of a given number:

```javascript
function factorial(n) {
  if (n === 1) return 1;
  return n * factorial(n - 1);
}
console.log(factorial(5));
```

In this example, the `factorial` function calls itself recursively until the base case is reached, where `n === 1`. The function returns the product of `n` and the factorial of `n - 1`, which is the result of the recursive call. The solution to the original problem is obtained by combining the solutions to the sub-problems in this manner. The factorial of `5` can be calculated by calling `factorial(5)`, which will return `120`.

## 5. Divide & Conquer Algorithm <a href="#505b" id="505b"></a>

Divide and conquer is an algorithmic technique where a problem is divided into smaller sub-problems that can be solved more easily. The solutions to the sub-problems are then combined to find the solution to the original problem. The divide and conquer approach is useful for solving problems that can be broken down into smaller sub-problems that are similar to the original problem.

Here is an example of how to use divide and conquer in JavaScript to find the maximum number in an array:

```javascript
function max(array, start, end) {
  if (start === end) return array[start];
  const mid = Math.floor((start + end) / 2);
  const leftMax = max(array, start, mid);
  const rightMax = max(array, mid + 1, end);
  return Math.max(leftMax, rightMax);
}

const array = [1, 2, 3, 4, 5];
console.log(max(array, 0, array.length - 1));
```

In this example, the `max` function uses the divide and conquer approach to find the maximum number in the array. The array is divided into two halves, and the maximum number in each half is found by calling the `max` function recursively. The final result is the maximum of the two results, which is the maximum number in the entire array. The call to `max(array, 0, array.length - 1)` will return `5`, which is the maximum number in the array.

## 6. Hashing Technique <a href="#287e" id="287e"></a>

Hashing is a technique used in computer science to map data of arbitrary size to data of a fixed size. A hash function takes in an input, known as a message or pre-image, and returns a fixed-size string of characters, known as a hash or digest. The same input will always produce the same hash, but even a small change in the input will result in a completely different hash.

In JavaScript, hashes can be generated using the `crypto` module, which provides cryptographic functionality. Here is an example of how to use the `crypto` module to generate a SHA-256 hash:

```javascript
const crypto = require('crypto');

function hash(message) {
  return crypto.createHash('sha256')
    .update(message)
    .digest('hex');
}

const message = 'Hello, world!';
console.log(hash(message));
```

In this example, the `hash` function uses the `crypto` module to generate a SHA-256 hash of the input message. The call to `hash(message)` will return a string of hexadecimal characters that represents the hash of the input message. The same input will always produce the same hash, so this technique can be used for verifying the integrity of data.

[Written by Lelianto Eko Pradana](https://medium.com/@lelianto.eko?source=post\_page-----40d42d4208dc--------------------------------)

Frontend Engineer @Nanovest

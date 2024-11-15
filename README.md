<h1> NumPy 47 Exercises, Practice, and Solutions in Python</h1>
Welcome to the NumPy 47 Exercises, Practice, and Solutions repository. This repository is a comprehensive guide to mastering NumPy, one of the most powerful libraries in Python for numerical computing. Each topic is accompanied by a brief explanation and a practical code example.

<h2> Contents </h2>

<ol>
<li> Array Creation Basics 
<li> Basic Arithmetic Operations 
<li> Boolean Indexing: Greater Than
<li>Boolean Indexing: Even Numbers
<li>Broadcasting: Adding a Scalar to an Array
<li>Using choose for Multiple Conditions
<li>Clipping Array Values
<li>Combining Boolean and Fancy Indexing
<li>Combining Multiple Indexing Techniques
<li>Concatenation of Arrays
<li>Conditional Indexing: Set Even Numbers to -1
<li>Conditional Replacement with np.where
<li>Cumulative Sum and Product
<li>Ellipsis Indexing
<li>Exponential and Logarithmic Functions
<li>Extracting Diagonal Elements
<li>Extracting Lower Triangle of a Matrix
<li>Fancy Indexing
<li>Flattening a Multi-dimensional Array
<li>Indexing with Arrays
<li>Indexing with np.take
<li>Indexing with np.where
<li>Linear Space Array
<li>Masked Indexing
<li>Masked Indexing with np.ma.masked_where
<li>Meshgrid Creation
<li>Modifying Array Values Using Indexing
<li>Indexing Multi-dimensional Arrays with Slices
<li>Multi-dimensional Slicing
<li>Multi-dimensional Array Indexing with Mixed Types
<li>Indexing with Negative Indices
<li>Power and Square Root
<li>Random Array Generation
<li>Reshaping Arrays
<li>Reverse Array Using Indexing
<li>Setting Values Using Indexing
<li>Slicing with Step
<li>Sorting Arrays
<li>Statistical Functions: Mean, Median, Standard Deviation, and Variance
<li>Transposing Arrays
<li>Trigonometric Functions: Sine, Cosine, and Tangent
<li>Unique Elements and Counting
<li>Extracting Upper Triangle of a Matrix
<li>2D Array
<li>3D Array
<li>Advanced Indexing with Meshgrid
<li>Advanced Slicing with Step in 2D Arrays

</ol>

<h3> Array Creation Basics </h3>

```Python
import numpy as np

# Create a 1D array
arr1 = np.array([1, 2, 3])
print("1D Array:", arr1)

# Create a 2D array
arr2 = np.array([[1, 2], [3, 4]])
print("2D Array:\n", arr2)

# Create an array of zeros with a specified shape
zeros = np.zeros((2, 3))
print("Array of zeros:\n", zeros)

# Create an array with a range of values
range_array = np.arange(1, 10, 2)  # Start at 1, end before 10, step by 2
print("Range array:", range_array)

```

Explanation: This code demonstrates basic array creation in NumPy, from simple 1D and 2D arrays to arrays filled with zeros or generated with a specified range.


<h3> Basic Arithmetic Operations </h3>

```Python
# Create two arrays
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# Addition
print("Addition:", a + b)

# Subtraction
print("Subtraction:", a - b)

# Multiplication
print("Multiplication:", a * b)

# Division
print("Division:", a / b)
```
Explanation: This code performs basic arithmetic operations element-wise between two arrays (a and b), such as addition, subtraction, multiplication, and division.


<h3> Boolean Indexing: Greater Than</h3>

```Python
arr = np.array([10, 20, 30, 40])

# Select elements greater than 25
greater_than_25 = arr[arr > 25]
print("Elements greater than 25:", greater_than_25)

```
Explanation: Boolean indexing is used to filter elements based on a condition. Here, only elements greater than 25 are selected from the array arr.

<h3> Boolean Indexing: Even Numbers </h3>

```Python
arr = np.array([1, 2, 3, 4, 5, 6])

# Select even numbers
even_numbers = arr[arr % 2 == 0]
print("Even numbers:", even_numbers)
```
Explanation: This code filters out even numbers using Boolean indexing, where the condition arr % 2 == 0 checks for even elements.


<h3> Broadcasting: Adding a Scalar to an Array</h3>

```Python
arr = np.array([1, 2, 3])

# Add 5 to each element
broadcasted = arr + 5
print("Array after adding 5:", broadcasted)

```
Explanation: Broadcasting allows you to apply a scalar operation across an entire array. Here, 5 is added to each element in arr without needing an array of the same shape.


<h3> Using choose for Multiple Conditions</h3>

```Python
# Define choices and conditions
choices = np.array([100, 200, 300])
conditions = np.array([0, 2, 1])

# Use np.choose to select elements from 'choices' based on 'conditions'
result = np.choose(conditions, choices)
print("Result of choose:", result)

```
Explanation: The choose function allows selection from multiple options based on an index array (conditions). Each value in conditions corresponds to an index in choices.


<h3> Clipping Array Values</h3>

```Python
arr = np.array([5, 15, 25, 35])

# Clip values between 10 and 30
clipped = np.clip(arr, 10, 30)
print("Clipped Array:", clipped)

```
Explanation: np.clip limits the values in an array to a specified range, replacing values below 10 with 10 and above 30 with 30.


<h3> Combining Boolean and Fancy Indexing</h3>

```Python
arr = np.array([10, 20, 30, 40])

# Boolean mask for values greater than 20
mask = arr > 20

# Use fancy indexing with the boolean mask
result = arr[mask]
print("Values greater than 20:", result)

```
Explanation: Combining Boolean indexing and fancy indexing allows for flexible selections. Here, values greater than 20 are selected using a mask.


<h3>Combining Multiple Indexing Techniques</h3>

```Python
arr = np.array([[1, 2], [3, 4], [5, 6]])

# Use slicing and specific element indexing
result = arr[1:, 1]
print("Result of multiple indexing techniques:", result)

```
Explanation: Multiple indexing techniques, such as slicing and specific element selection, can be combined to retrieve precise subsets of an array. Here, we select elements in the last two rows, second column.


<h3>Concatenation of Arrays</h3>

```Python
a = np.array([1, 2])
b = np.array([3, 4])

# Concatenate two arrays along the first axis
concatenated = np.concatenate((a, b))
print("Concatenated Array:", concatenated)

```
Explanation: Array concatenation joins two or more arrays along a specified axis. Here, a and b are combined along the default axis to form a new array.


<h3>Conditional Indexing: Set Even Numbers to -1</h3>

```Python
arr = np.array([1, 2, 3, 4, 5, 6])

# Replace even numbers with -1
arr[arr % 2 == 0] = -1
print("Array with even numbers set to -1:", arr)

```
Explanation: This code uses conditional indexing to identify even numbers in the array and replaces them with -1.


<h3>Conditional Replacement with np.where</h3>

```Python
arr = np.array([10, 15, 20, 25])

# Use np.where to replace values greater than 18 with 0, others remain the same
result = np.where(arr > 18, 0, arr)
print("Array after conditional replacement:", result)

```
Explanation: np.where allows for conditional replacements. Here, values greater than 18 are replaced with 0, while other values remain unchanged.


<h3>Cumulative Sum and Product</h3>

```Python
arr = np.array([1, 2, 3, 4])

# Cumulative sum of elements
cumsum = np.cumsum(arr)
print("Cumulative Sum:", cumsum)

# Cumulative product of elements
cumprod = np.cumprod(arr)
print("Cumulative Product:", cumprod)

```
Explanation: Cumulative operations (cumsum and cumprod) compute the running sum or product of elements along a specified axis.


<h3>Ellipsis Indexing</h3>

```Python
arr = np.random.rand(2, 3, 4)

# Use ellipsis to select all elements along the last axis
result = arr[..., 1]
print("Ellipsis Indexing Result:\n", result)

```
Explanation: The ellipsis (...) is a shorthand in indexing to represent all dimensions up to a certain point. Here, it selects all elements along the last dimension for each slice.


<h3>Exponential and Logarithmic Functions</h3>

```Python
arr = np.array([1, 2, 3, 4])

# Compute the exponential of each element
exp_arr = np.exp(arr)
print("Exponential:", exp_arr)

# Compute the natural logarithm of each element
log_arr = np.log(arr)
print("Natural Logarithm:", log_arr)

# Compute the base-10 logarithm of each element
log10_arr = np.log10(arr)
print("Logarithm Base 10:", log10_arr)

```
Explanation: NumPy provides functions for exponential and logarithmic calculations. np.exp computes, while np.log and np.log10 compute the natural and base-10 logarithms, respectively.


<h3>Extracting Diagonal Elements</h3>

```Python
matrix = np.array([[1, 2, 3],
                   [4, 5, 6],
                   [7, 8, 9]])

# Extract the diagonal elements
diagonal = np.diag(matrix)
print("Diagonal Elements:", diagonal)

```
Explanation: np.diag extracts the diagonal elements of a matrix. The diagonal includes elements where the row index equals the column index.


<h3>Extracting Lower Triangle of a Matrix</h3>

```Python
matrix = np.array([[1, 2, 3],
                   [4, 5, 6],
                   [7, 8, 9]])

# Extract lower triangle elements
lower_triangle = np.tril(matrix)
print("Lower Triangle:\n", lower_triangle)

```
Explanation: np.tril returns the lower triangular part of a matrix by setting elements above the diagonal to zero.


<h3>Fancy Indexing</h3>

```Python
arr = np.array([10, 20, 30, 40, 50])

# Index specific elements using a list of indices
indices = [0, 2, 4]
fancy_indexed = arr[indices]
print("Fancy Indexed Elements:", fancy_indexed)

```
Explanation: Fancy indexing allows you to select specific elements using a list or array of indices.


<h3>Flattening a Multi-dimensional Array</h3>

```Python
matrix = np.array([[1, 2], [3, 4]])

# Flatten the array into a 1D array
flattened = matrix.flatten()
print("Flattened Array:", flattened)

```
Explanation: The flatten method converts a multi-dimensional array into a 1D array while preserving the order of elements.


<h3>Indexing with Arrays</h3>

```Python
arr = np.array([10, 20, 30, 40])

# Use an array of indices to select elements
indices = np.array([3, 0, 2])
indexed = arr[indices]
print("Array Indexing Result:", indexed)

```
Explanation: Arrays can be used as indices to extract elements at specific positions.


<h3>Indexing with np.take</h3>

```Python
arr = np.array([10, 20, 30, 40])

# Use np.take to extract elements based on indices
taken = np.take(arr, [1, 3])
print("Result of np.take:", taken)

```
Explanation: np.take is another way to index arrays, especially useful for applying along specific axes in multi-dimensional arrays.


<h3>Indexing with np.where</h3>

```Python
arr = np.array([10, 20, 30, 40])

# Get indices where elements are greater than 25
indices = np.where(arr > 25)
print("Indices where elements > 25:", indices)
print("Elements:", arr[indices])

```
Explanation: np.where returns indices that satisfy a condition. These indices can then be used for further operations.


<h3>Linear Space Array</h3>

```Python
# Generate 5 equally spaced values between 0 and 10
linspace = np.linspace(0, 10, 5)
print("Linear Space Array:", linspace)

```
Explanation: np.linspace generates a specified number of evenly spaced values over a given range.


<h3>Masked Indexing</h3>

```Python
arr = np.array([10, 20, 30, 40])

# Mask elements greater than 25
masked = arr[arr > 25]
print("Masked Elements:", masked)

```
Explanation: Masked indexing filters an array based on a Boolean condition.


<h3>Masked Indexing with np.ma.masked_where</h3>

```Python
arr = np.array([10, 20, 30, 40])

# Mask elements less than 25
masked = np.ma.masked_where(arr < 25, arr)
print("Masked Array with np.ma.masked_where:", masked)

```
Explanation: np.ma.masked_where masks elements based on a condition and produces a masked array.


<h3>Meshgrid Creation</h3>

```Python
x = np.array([1, 2, 3])
y = np.array([4, 5])

# Create a meshgrid
xx, yy = np.meshgrid(x, y)
print("Meshgrid X:\n", xx)
print("Meshgrid Y:\n", yy)

```
Explanation: np.meshgrid creates coordinate grids for vectorized evaluations over 2D space.


<h3>Modifying Array Values Using Indexing</h3>

```Python
arr = np.array([10, 20, 30, 40])

# Modify elements at specific indices
arr[[1, 3]] = [99, 77]
print("Modified Array:", arr)

```
Explanation: Arrays can be modified in-place by assigning new values to specific indices.



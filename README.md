# Numc Python Package

Welcome to Numc, a library for the Python programming language, adding support for very large and multi-dimensional matrix operations. The Numc package also provides an easy, convenient, and efficient way for these operations. This repository is developed in UC Berkeley CS61C as a class project by Rory Na and Stephen Yang.

## Sample commands:

#### CREATE NEW MATRIX:
Follow the following steps in order to create a matrix in the python terminal.
Import the Numc package: import Numc as nc

To create a new matrix, use the following syntax:
nc.Matrix([[a, b, c], … ]) where a, b, and c are integers or double-precision float numbers in the C language. You may create the matrix in any reasonable dimensions, by concatenating the numbers(a, b, c) or the rows [a, b, c]. You need to use commas to separate the values.
nc.Matrix(m, n) where m and n are the rows and the columns of the matrix. The matrix will be filled with all zeros. 
nc.Matrix(m, n, val) where m and n are the rows and the columns of the matrix and val is the value that the matrix will be filled with.

Example usage: 
~~~ 
a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
The variable a is now assigned to a representation of a 3x3 matrix with elements [1, -2, 3.0] in the first row, [-4, -5, 6] in the second row, and [7.0, 8, -9] in the third row.
b = nc.Matrix(3, 3)
The variable b is now assigned to a representation of a 3x3 matrix with elements [0, 0, 0] in the first row, [0, 0, 0] in the second row, and [0, 0, 0] in the third row.
c = nc.Matrix(3, 3, 2)
The variable c is now assigned to a representation of a 3x3 matrix with elements [2, 2, 2] in the first row, [2, 2, 2] in the second row, and [2, 2, 2] in the third row.
~~~ 
#### ADD: 
a = b + c, where a, b, and c are matrices.
Corresponding method in numc.c: Matrix61c_add
Corresponding method in matrix.c: add_matrix
Description: This operation adds two pre- allocated matrices.

Example usage: 
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> b = nc.Matrix(3, 3, 2)
>>> a + b
[[3.0, 0.0, 5.0], [-2.0, -3.0, 8.0], [9.0, 10.0, -7.0]]
~~~ 
#### SUB: 
a = b - c, where a, b, and c are matrices.
Corresponding method in numc.c: Matrix61c_sub
Corresponding method in matrix.c: sub_matrix
Description: This operation subtracts two pre- allocated matrices.

Example usage: 
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> b = nc.Matrix(3, 3, 2)
>>> a - b
[[-1.0, -4.0, 1.0], [86.0, -7.0, 4.0], [5.0, 6.0, -11.0]]
~~~ 

#### MULTIPLY: 
a = b * c, where a, b, and c are matrices.
Corresponding method in numc.c: Matrix61c_multiply
Corresponding method in matrix.c: mul_matrix
Description: This operation multiplies two pre- allocated matrices.

Example usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> b = nc.Matrix(3, 3, 2)
>>> a * b
[[4.0, 4.0, 4.0], [178.0, 178.0, 178.0], [12.0, 12.0, 12.0]]
~~~ 

#### NEG: 
a = - b, where a and b are matrices.
Corresponding method in numc.c: Matrix61c_neg
Corresponding method in matrix.c: neg_matrix
Description: This operation negates two pre- allocated matrices.

Example usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> -a
[[-1.0, 2.0, -3.0], [4.0, 5.0, -6.0], [-7.0, -8.0, 9.0]]
~~~ 

#### ABS: 
a = abs(b), where a and b are matrices.
Corresponding method in numc.c: Matrix61c_abs
Corresponding method in matrix.c: abs_matrix
Description: This operation takes the absolute value of a pre-allocated matrix.

Example usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> abs(a)
[[1.0, 2.0, 3.0], [4.0, 5.0, 6.0], [7.0, 8.0, 9.0]]
~~~ 

#### EXPONENTIATION: 
a = a ** n, where a is a matrix and n is an integer.
Corresponding method in numC: Matrix61c_pow
Corresponding method in matrix.c: pow_matrix
Description: This operation returns the nth power of a pre-allocated matrix.

Example usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> a ** 0
[[1.0, 0.0, 0.0], [0.0, 1.0, 0.0], [0.0, 0.0, 1.0]]
>>> a ** 1
[[1.0, -2.0, 3.0], [-4.0, -5.0, 6.0], [7.0, 8.0, -9.0]]
>>> a ** 2
[[30.0, 32.0, -36.0], [58.0, 81.0, -96.0], [-88.0, -126.0, 150.0]]
~~~ 
#### GET ELEMENT: 
a.get(i, j), where a is a matrix, i, and j are integer indices. 
Corresponding method in numC: Matrix61c_get_value
Corresponding method in matrix.c: get
Description: This operation retrieves an element from a matrix.

Example usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> a.get(1, 0)
-4.0
~~~ 
#### SET AN ELEMENT: 
a.set(i, j, val), where a is a matrix, val is a new double-precision float, and i and j are integers.
Corresponding method in numC: Matrix61c_set_value
Corresponding method in matrix.c: set
Description: This operation sets an element of a pre-allocated matrix to a new value.

Example usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> a.set(1, 0, 88)
>>>
~~~ 

#### SLICING GET: 
a[i][j] / a[i, j] / a[i, j:k] / a[i:j, k] / a[i:j, k:l], where a is a matrix, i, j, k and l are integer indices.
Corresponding method in numC: Matrix61c_subscript
Corresponding method in matrix.c: N/A
Description: This operation returns the slice of a pre-allocated matrix. The sliced matrix shares data with its parent matrix.

Example usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>>a[1]
[88.0, -5.0, 6.0]
>>> a[1][0]
88.0
>>> a[1: 3]
[[88.0, -5.0, 6.0], [7.0, 8.0, -9.0]]
>>> a[2, 2]
-9.0
>>> a[1: 3, 2]
[6.0, -9.0]
>>> a[2, 0:1]
7.0
>>> a[1: 2, 0: 1]
-5.0
~~~ 

#### SLICING SET: 
a[i][j] / a[i, j] / a[i, j:k] / a[i:j, k] / a[i:j, k:l] = val/ b, where a and b are matrices, i, j, k and val are integer indices.
where a is a matrix and i and j are integers.
Corresponding method in numC:Matrix61c_set_subscript
Corresponding method in matrix.c: N/A
Description: This operation sets the slice of a pre-allocated matrix into a new value or matrix. The sliced matrix shares data with its parent matrix, so the new values are reflected in the parent matrix.

Example usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>> a[1] = [10, 11, 12]
>>> a[1][0] = 13
>>> a[1: 3] = [[14, 15, 16], [17, 18, 19]]
>>> a[2, 2] = 20
>>> a[1: 3, 2] = [21, 22]
>>> a[2, 0:1] = 23
>>> a[1: 2, 0: 1] = 24
~~~ 

#### GET SHAPE: 
a.shape, where a is a matrix.
Corresponding method in numC: get_shape()
Corresponding method in matrix.c: N/A
Description: This operation retrieves the shape of a pre-assigned matrix.

Example Usage:
~~~ 
>>> a = nc.Matrix([[1, -2, 3.0], [-4, -5, 6], [7.0, 8, -9]])
>>>a.shape
(3, 3)
~~~ 
* Note that the dimensions need to be correct for corresponding operations for the operation to proceed.

## Performances:
The plugin supports SIMD, OpenMP, cache blocking and loop unrolling rendering you unprecedentedly fast performance improvements in large operations, such as taking a large square or multiplying large matrices.





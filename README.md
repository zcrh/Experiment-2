# PROGRAMMING ASSIGNMENT 2
## NUMERICAL PYTHON (NUMPY)
The core Python library for scientific computing is called NumPy. A multidimensional array object, different derived objects, and a variety of routines for quick array operations—like sorting, selecting, I/O, discrete Fourier transforms, basic linear algebra, basic statistical operations, random simulation, and much more—are all provided by this Python library.


### I. Intended Learning Outcomes:
  1. To identify the codes and functions incorporated in the Numpy library
  2. To be able to apply and use the different codes and functions in creating a Python program using a
    Numpy library

### II. Instructions:
Write a Python script/code in the Jupyter Notebook to do the given problems. You may submit your Jupyter
notebook in the dedicated submission bin.

## **_1. NORMALIZATION PROBLEM_** 
Normalization is one of the most basic preprocessing techniques in data analytics. This involves centering and scaling process. Centering means subtracting the data from the
mean and scaling means dividing with its standard deviation. Mathematically, normalization can be
expressed as:

![Screenshot 2024-09-23 021737](https://github.com/user-attachments/assets/06257872-e5d3-4193-9866-073a635aea23)

In Python, element-wise mean and element-wise standard deviation can be obtained by using .mean() and
.std() calls. In this problem, create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized
ndarray as X_normalized.npy

### In this project, we:
- Create a random 5x5 matrix using `numpy`.
- Normalize the matrix using the mean and standard deviation of its elements.
- Save the normalized matrix as a `.npy` file.

### 🖥️ INPUT CODE:
```python
# This line provides support for arrays or multidimensional array (ndarray)
import numpy as np

# Create a random 5x5 ndarray, storing it into X and then display
X = np.random.rand(5, 5)
print("Random 5x5 ndarray: ")
print(X)

# Calculating the mean and standard deviation of X
mean_of_X = X.mean()
std_of_X = X.std()

# Normalizing X using the given formula and displaying the result
X_normalized = (X - mean_of_X) / std_of_X
print("\nNormalized X: ")
print(X_normalized)

# Save the normalized ndarray 
np.save('X_normalized.npy', X_normalized)

```
### 🏁 EXPECTED OUTPUT:
```
Random 5x5 ndarray: 
[[0.59710917 0.30588285 0.32391373 0.49047258 0.83150912]
 [0.1229211  0.99224615 0.27504258 0.53338411 0.13024868]
 [0.50384816 0.13358147 0.21626588 0.72043821 0.59957076]
 [0.65373965 0.73555749 0.42341109 0.56515684 0.24705054]
 [0.82214312 0.21289679 0.50057632 0.05754141 0.50889845]]

Normalized X: 
[[ 0.55370345 -0.62355858 -0.55067004  0.12263248  1.50124889]
 [-1.3631687   2.15101713 -0.74822824  0.29609936 -1.33354746]
 [ 0.17670235 -1.3200749  -0.98582894  1.0522525   0.56365429]
 [ 0.78262823  1.11337112 -0.1484589   0.4245384  -0.86138409]
 [ 1.46338749 -0.99944826  0.16347615 -1.62746153  0.1971178 ]]
```
The expected output will produce a random 5x5 ndarray and normalize the produced data with the given formula we have set.

## **_2. DIVISIBLE BY THREE PROBLEM_** 
Create the following 10 x 10 ndarray. which are the squares of the first 100 positive integers.
From this ndarray, determine all the elements that are divisible by 3. Save the result as div_by_3.npy

![Screenshot 2024-09-23 012932](https://github.com/user-attachments/assets/5bc99446-a35d-4ab3-b11a-fc7126938882)

### In this project, we:
- Create a 10x10 matrix where the values are the squares of the first 100 integers.
- Find all elements in the matrix that are divisible by 3.
- Save the resulting array as div_by_3.npy.

### 🖥️ INPUT CODE:
```python
import numpy as np

def ndarray_and_div_by_3():
    # Create a 10x10 ndarray of the first 100 integers (.arange function), by squaring it (.square function) and arranging into a 10x10 ndarray (.reshape function)
    A = np.square(np.arange(1,101).reshape(10,10))
    print("A = ")
    print(A)

    #Finding elements in ndarray A that is divisible by 3
    div_by_3 = A[A % 3 == 0]
    print("\nElements divisible by 3: ")
    print(div_by_3)
    
    #Save the result of the elements that are divisble by 3 as div_by_3.npy
    np.save('div_by_3.npy',div_by_3)

ndarray_and_div_by_3()

```
### 🏁 EXPECTED OUTPUT:
```
A = 
[[    1     4     9    16    25    36    49    64    81   100]
 [  121   144   169   196   225   256   289   324   361   400]
 [  441   484   529   576   625   676   729   784   841   900]
 [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]
 [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]
 [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]
 [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]
 [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]
 [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]
 [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]

Elements divisible by 3: 
[   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
```
The matrix will be a 10x10 ndarray containing the squares of the first 100 integers. The elements that are divisible by 3 will be extracted and stored in the file div_by_3.npy.

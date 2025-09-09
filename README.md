# Programming-Assignment-2
## Experiment 2 - Numerical Python (Numpy)
### Intended Learning Outcomes
1. To identify the codes and functions incorporated in the Numpy library
2. To be able to apply and use the different codes and functions and functions in creating a Python program using a Numpy library
### Given Problems
1. NORMALIZATION PROBLEM
2. DIVISIBLE BY 3 PROBLEM
------------------------------------------
## NORMALIZATION PROBLEM
Normalization is one of the most basic preprocessing techniques in data analytics. This involves centering and scaling process. Centering means subtracting the data from the mean and scaling means dividing with its standard deviation. Mathematically, normalization can be expressed as:  
<img width="73" height="45" alt="image" src="https://github.com/user-attachments/assets/c3e78836-3507-426e-8456-175f299ac21e" />

In Python, element-wise mean and element-wise standard deviation can be obtained by using .mean() and .std() calls

For this problem, I have to create a random 5x5 ndarray and store it to variable X. I will then normalize X and save the normalized ndarray as X_normalized.npy
### My Code
```python
import numpy as np
```
```python
#Creates a 5x5 random array

X = np.random.random((5,5)) 
X
```
array([[0.46989959, 0.72312575, 0.674654  , 0.20175477, 0.99623477]
       [0.31470945, 0.36483306, 0.90875893, 0.10509999, 0.968184  ],
       [0.74253293, 0.2496707 , 0.20127984, 0.72175212, 0.02193033],
       [0.32642417, 0.76283562, 0.39010869, 0.4707242 , 0.62524118],
       [0.12036641, 0.38049324, 0.29683616, 0.88918224, 0.0142059 ]])
```python
#Will normalize the array and store it in variable X

X = (X - X.mean()) / X.std()
X
```
array([[-0.02605848,  0.82715393,  0.66383471, -0.92953734,  1.747359  ]
       [-0.54895131, -0.38006638,  1.4526206 , -1.25520295,  1.65284558],
       [ 0.89254388, -0.76809088, -0.93113754,  0.82252565, -1.53543223],
       [-0.5094801 ,  0.96095114, -0.29490345, -0.02328007,  0.49734467],
       [-1.20376476, -0.32730145, -0.60917304,  1.38665951, -1.56145867]])
```python
#The normalized array will be save as X_normalized.npy

np.save("X_normalized.npy", x) 
```
```python
#Double Check

result = np.load("X_normalized.npy")
print(result)
```
[[-0.78475898 -0.81009503 -0.30071264 -0.30414232  0.58615637]
 [ 1.56415734 -1.22542499 -1.04884381  1.37829152 -1.07778884]
 [-0.92786513 -0.55465612  1.16576805  0.63474369  1.62156848]
 [ 1.26744889  0.50998588 -0.99679651 -1.15964643 -1.02777718]
 [ 1.48649874 -0.40529622 -0.25643239  1.22983815 -0.56422052]]
### Explanation
1. **Accessing Numpy Library** - 
To access Numpy library, the import convention must be used: import numpy as np
2. **Create a 5x5 Random Array** -
np.random.random is a numpy function that generates values between 0 and 1. Therefore the code np.random.random((5,5)) will be used. The (5, 5) indicates the array will be in a 5x5 array.
3. **Storing the array to variable X** -
To store the randomized 5x5 array, we simply just equate X to the code. X = np.random.random((5,5)). We also place the variable again below the code so it can be updated
4. **Normalize X** -
To normalize the array, we use the formula (X - x̄) / σ. To do this, we will use the built-in codes .mean() and .std() making the code look like X = (X - X.mean()) / X.std(). This will normalize the array stored in variable X
5. **Saving the normalized ndarray as X_normalized.npy** -
To save the normalized array, .save function will be used. Therefore, the code will look like np.save("X_normalized.npy", X). The normalized array from variable X will now be saved.
6. **Double Checking** -
To double check, the .load function is used. The code will look like this, result = np.load("X_normalized.npy"). Then simply put print(result) at the new line and shall print the normalized array
------------------------------------------
## DIVISIBLE BY 3 PROBLEM
For the second problem, I have to create a 10x10 ndarray that contains the squares of the first 100 posiive integers. Once created, I will determine all the elements that are divisible by 3. Lastly is to save the result as div_by_3.npy.
### My Code
```python
#create an array where the values ranges from 1 to 100, each value is then squared

x = np.arange(1, 101)**2
x
```
array([    1,     4,     9,    16,    25,    36,    49,    64,    81,
         100,   121,   144,   169,   196,   225,   256,   289,   324,
         361,   400,   441,   484,   529,   576,   625,   676,   729, 
         784,   841,   900,   961,  1024,  1089,  1156,  1225,  1296, 
        1369,  1444,  1521,  1600,  1681,  1764,  1849,  1936,  2025,
        2116,  2209,  2304,  2401,  2500,  2601,  2704,  2809,  2916,
        3025,  3136,  3249,  3364,  3481,  3600,  3721,  3844,  3969,
        4096,  4225,  4356,  4489,  4624,  4761,  4900,  5041,  5184,
        5329,  5476,  5625,  5776,  5929,  6084,  6241,  6400,  6561,
        6724,  6889,  7056,  7225,  7396,  7569,  7744,  7921,  8100,
        8281,  8464,  8649,  8836,  9025,  9216,  9409,  9604,  9801,
       10000])
```python
#reshapes the array in a 10x10 array

x = x.reshape(10,10)
print(x)
```
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
```python
#an array that only has elements that is divisible by 3

data = x[x % 3 == 0]
data
```
array([   9,   36,   81,  144,  225,  324,  441,  576,  729,  900, 1089,
       1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600, 3969, 4356,
       4761, 5184, 5625, 6084, 6561, 7056, 7569, 8100, 8649, 9216, 9801])
```python
#the new array will be saved as div_by_3.npy

np.save("div_by_3.npy", data)
```
```python
#double checking

result = np.load("div_by_3.npy")
print(result)
```
[   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
### Explanation
1. **Accessing Numpy Library** - 
To access Numpy library, the import convention must be used: import numpy as np
2. **Squares of the first 100 positive Integers** -
np.arange is a numpy function that generates an array of values. Therefore the code x = np.arange(1, 101)**2 is used. The (1,101) indicates that the array will generates values from 1 to 100. With **2, this will allows the numbers to multiply by itself, making the 100 positive integers squared. Make sure to place the variable used below the code.
4. **Reshaping Array** -
.reshape is a function that reshapes the array to the desired row and columns. Thus, x = x.reshape(10,10) is used, indicating that the array will be reshaped to a 10x10 array. Once done, place the code print(x) below to show the updated output
3. **Elements Divisible by 3** -
To determine which elements are divisible by 3, we use the code x[x % 3 == 0]. This gathers all the elements that are divisible by 3 and will be stored in the data, data = x[x % 3 == 0].
4. **Saving the normalized ndarray as div_by_3.npy** -
To save the array that contains all the elements divisible by 3, .save function will be used. Therefore, the code will look like np.save("div_by_3.npy", data). The normalized array from data will now be saved.
5. **Double Checking** -
To double check, the .load function is used. The code will look like this, result = np.load("div_by_3.npy"). Then simply put print(result) at the new line and shall print the normalized array






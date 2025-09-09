# Programming-Assignment-1
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
array([[0.46989959, 0.72312575, 0.674654  , 0.20175477, 0.99623477],
       [0.31470945, 0.36483306, 0.90875893, 0.10509999, 0.968184  ],
       [0.74253293, 0.2496707 , 0.20127984, 0.72175212, 0.02193033],
       [0.32642417, 0.76283562, 0.39010869, 0.4707242 , 0.62524118],
       [0.12036641, 0.38049324, 0.29683616, 0.88918224, 0.0142059 ]])
```python
#Will normalize the array and store it in variable X

X = (X - X.mean()) / X.std()
X
```
array([[-0.02605848,  0.82715393,  0.66383471, -0.92953734,  1.747359  ],
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
3. **Normalize X** -
To normalize the array, we use the formula (X - x̄) / σ. To do this, we will use the built-in codes .mean() and .std() making the code look like X = (X - X.mean()) / X.std(). This will normalize the array stored in variable X
4. **Saving the normalized ndarray as X_normalized.npy** -
To save the normalized array, .save function will be used. Therefore, the code will look like np.save("X_normalized.npy", X). The normalized array from variable X will now be saved.
5. **Double Checking** -
To double check, the .load function is used. The code will look like this, result = np.load("X_normalized.npy"). Then simply put print(result) at the new line and shall print the normalized array
------------------------------------------
## DIVISIBLE BY 3 PROBLEM
For the second problem, I have to create a 10x10 ndarray that contains the squares of the first 100 posiive integers. Once created, I will determine all the elements that are divisible by 3. Lastly is to save the result as div_by_3.npy.
### My Code





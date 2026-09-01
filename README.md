# ECE2112_PA2
Written and made by Steven Andrew A. Cruz of 2ECE-D

# EXPERIMENT 2: NUMERICAL PYTHON (NUMPY)
The experiment tackles the use of numerical python functions (NumPy) to create and reshape NumPy arrays. To use these functions to perform vectorized numerical operations on an ndarray, compute array statistics and use Boolean conditions to select elements, and as well as save computed NumPy arrays as `.npy` files.



PART A. REPRODUCABLE NORMALIZATION PROBLEM 

Create a reproducible random 5 × 5 integer ndarray named X. Where `¯x` is the mean of all 25 elements and `σ` is their population standard deviation as returned by NumPy’s default `std()` call. Store the normalized array in `X_normalized`.


```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5)) 
X
```




```python
mean = np.mean(X)
mean
```



```python
std = np.std(X)
std
```



```python
Difference = X - mean
Difference
```



```python
X_normalized = Difference/std
X_normalized
```



```python
mean_X_nomralized = np.mean(X_normalized)
mean_X_nomralized
```



```python
np.save('X_normalized.npy', X_normalized)
```




PART B. CUBES DIVISIBLE BY 4 PROBLEM 

Using NumPy, create the first 100 positive integers, cube every element, and reshape the result into a
10 × 10 ndarray named `C`. Thus, `C` begins with 13 and ends with 1003. Use a Boolean condition on C to obtain every cubed value divisible by 4. Store the selected values in `div_by_4`. Preserve NumPy’s normal row-major selection order.


```python
c1=  (np.arange(1,101)).reshape(10,10)
c1
```


```python
C = np.power= c1**3
C
```


```python
div_by_4= C[C % 4 ==0]
div_by_4
```


```python
np.save('div_by_4.npy', div_by_4)
```







PART C. ABOVE-MEAN SQUARES PROBLEM 

Create a 6 × 6 ndarray named `S` containing the squares of the first 36 positive integers in increasing row-major order. Compute the mean of all elements of `S` and store it in `S_mean`. Then use Boolean filtering to select only the elements strictly greater than `S_mean`. Store these values in `above_mean`


```python
S1 = (np.arange(1,37)).reshape(6,6)
S1
```


```python
S = np.power = S1**2
S
```


```python
S_mean = np.mean(S)
S_mean
```


```python
above_mean = S[S>S_mean]
above_mean
```


```python
np.save('above_mean.npy', above_mean)
```


README FILE HISTORY:

September 1 2026 inputting codes used in the assignment 








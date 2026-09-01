# ECE2112_PA2
Written and made by Steven Andrew A. Cruz of 2ECE-D

# EXPERIMENT 2: NUMERICAL PYTHON (NUMPY)
The experiment tackles the use of numerical python functions (NumPy) to create and reshape NumPy arrays. To use these functions to perform vectorized numerical operations on an ndarray, compute array statistics and use Boolean conditions to select elements, and as well as save computed NumPy arrays as `.npy` files.



# PART A. REPRODUCABLE NORMALIZATION PROBLEM 

Create a reproducible random 5 × 5 integer ndarray named X. Where `¯x` is the mean of all 25 elements and `σ` is their population standard deviation as returned by NumPy’s default `std()` call. Store the normalized array in `X_normalized`.


Methods Used:

```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5)) 
X
```
The function `np.random.seed(2112)` is used to lock the 25 random elements. This means that the same random elements will be produce every time this code in ran. The ndarray `X` contains the function to create the 25 elements randomly between 10-101 in a 5 x 5 integer ndarray denoted by the function `np.random.radiant(10,101)`.  



```python
mean = np.mean(X)
mean
```
This ndarray named `mean` calculates the mean of the elements in ndarray `X` using the function `np.mean(X)`. The calculated value is `46.36`. 


```python
std = np.std(X)
std
```
The ndarray named `std` contains the calculated standard deviation of ndarray `X` denoted by the function `np.std`. This results in a standard deviation of `25.864075471588002`.


```python
Difference = X - mean
Difference
```
The ndarray `Difference` contains the numerator portion of the formula to gain the standard score / X_normalized denoted by the function `X - mean`. What this does is to simply subtract all of the elements in the ndarray `X` to the mean calculated from the same ndarray.  


```python
X_normalized = Difference/std
X_normalized
```
The ndarray `X_normalized` contains the function `Difference/std` which divides the elements in ndarray `Difference` to the standard deviation of ndarray `X`. 


```python
mean_X_nomralized = np.mean(X_normalized)
mean_X_nomralized
```
This ndarray named `mean_X_normalized` calculates the mean of the ndarray `X_normalized` using its elements. This results in a normalized mean of `0.0`. 


```python
std_X_nomralized = np.std(X_normalized)
std_X_nomralized
```
This ndarray named `std_X_normalized` calculates the standard deviation of the ndarray `X_normalized` using its elements. This results in a normalized standard deviation of `0.9999999999999999` or `1` to simplify.  


```python
np.save('X_normalized.npy', X_normalized)
```
This line of code is simply to save the elements created in ndarray `X_normalized` as a `.npy` file. 



# PART B. CUBES DIVISIBLE BY 4 PROBLEM 

Using NumPy, create the first 100 positive integers, cube every element, and reshape the result into a
10 × 10 ndarray named `C`. Thus, `C` begins with 13 and ends with 1003. Use a Boolean condition on C to obtain every cubed value divisible by 4. Store the selected values in `div_by_4`. Preserve NumPy’s normal row-major selection order.


Methods Used:

```python
c1=  (np.arange(1,101)).reshape(10,10)
c1
```
This line of code shows the ndarray named `c1`. In this ndarray a range of numbers are created from 1-100 given by function `np.arange(1,101)`. To put these numbers in a 10 x 10 ndarray, the function `.reshape(10,10.)` was used.  


```python
C = np.power= c1**3
C
```
The ndarray named `C` contains the previous ndarray `c1`, which all of its elements are cubed denoted by the function `np.power=c1**3`. 

```python
div_by_4= C[C % 4 ==0]
div_by_4
```
In this ndarray named `div_by_4` takes all of the elements from ndarray `C` and takes every element that is divisible by 4 denoted by the function `C[C % 4 ==0]`. 

```python
np.save('div_by_4.npy', div_by_4)
```
This line of code is simply to save the elements created in ndarray `div_by_4` as a `.npy` file. 






# PART C. ABOVE-MEAN SQUARES PROBLEM 

Create a 6 × 6 ndarray named `S` containing the squares of the first 36 positive integers in increasing row-major order. Compute the mean of all elements of `S` and store it in `S_mean`. Then use Boolean filtering to select only the elements strictly greater than `S_mean`. Store these values in `above_mean`


Methods Used:

```python
S1 = (np.arange(1,37)).reshape(6,6)
S1
```
The ndarray named `S1` contains the first 36 positive integers. To produce the 36 positive integers the function `np.arange(1,37)` is use. To put these integers in a 6 x 6 ndarray, the function `reshape(6,6)` is use.  

```python
S = np.power = S1**2
S
```
This ndarray named `S` stores all of the elements from the previous ndarray `S1` and squares them denoted by the function `np.power = S1**2`.

```python
S_mean = np.mean(S)
S_mean
```
This ndarray calculates the mean of the `S` ndarray by using the function `np.mean(S)`. This results in an output of `450.1666666666667`

```python
above_mean = S[S>S_mean]
above_mean
```
This ndarray compares the mean of the ndarray `S_mean` to the ndarray `S`, and strictly finds elements higher than the calculated mean. Anything higher will included and printed in the output. This line of code produces 15 selected elements; the first is 484 and the last is 1296. 

```python
np.save('above_mean.npy', above_mean)
```
This line of code is simply to save the elements created in ndarray `above_mean` as a `.npy` file. 

README FILE HISTORY:

September 1 2026 inputting codes used in the assignment 
September 2 2026 inputting explanation for each line of code








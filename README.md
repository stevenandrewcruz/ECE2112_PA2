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
The function `np.random.seed(2112)` is used to lock the 25 random elements. This means that the same random elements will be produce every time this code is ran. The ndarray `X` contains the function to create the 25 random elements between 10-101 in a 5 x 5 integer ndarray denoted by the function `np.random.radiant(10,101, size=(5,5))`.  



```python
mean = np.mean(X)
mean
```
This ndarray named `mean` calculates the mean of the elements in ndarray `X` using the function `np.mean(X)`. The calculated value is `46.36`. 


```python
std = np.std(X)
std
```
The ndarray named `std` contains the calculated standard deviation of ndarray `X` denoted by the function `np.std(X)`. This results in a standard deviation of `25.864075471588002`.


```python
Difference = X - mean
Difference
```
The ndarray `Difference` contains the numerator portion of the formula to gain the standard score / X_normalized denoted by the function `X - mean`. What this does is to simply subtract all of the elements in the ndarray `X` to the mean calculated from the same ndarray.  


```python
X_normalized = Difference/std
X_normalized
```
The ndarray `X_normalized` contains the function `Difference/std` which divides the elements in ndarray `Difference` to the `standard deviation` of ndarray `X`. 


```python
print(X_normalized)
array([[ 0.06340841, -1.36714726, -1.2124926 ,  0.79801809, -0.98051059],
       [-1.36714726, -0.20723725, -1.28981993,  0.75935442, -0.86451959],
       [ 0.95267275,  1.26198209,  0.25672675,  0.79801809,  0.91400909],
       [ 1.18465476, -0.43921926,  1.72594609, -1.05783793,  1.91926443],
       [-0.43921926,  0.29539042, -0.36189192, -0.20723725, -1.13516526]])
```
Expected Output


```python
mean_X_nomralized = np.mean(X_normalized)
mean_X_nomralized

print("Z mean:\n", mean_X_nomralized)
Z mean:
 0.0
```

This ndarray named `mean_X_normalized` calculates the mean of the ndarray `X_normalized` using its elements. This results in a normalized mean of `0.0`. 


```python
std_X_nomralized = np.std(X_normalized)
std_X_nomralized

print("Z std:\n",std_X_normalized)
Z std:
 0.9999999999999999
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
This line of code shows the ndarray named `c1`. In this ndarray a range of numbers are created from 1-100 given by function `np.arange(1,101)`. To put these numbers in a 10 x 10 ndarray, the function `.reshape(10,10.)` was used. The reason for the range being at `(1,101)` is to simply tell the code to start at `1` and end right before `101`, which in turn gives a result wherein there are 100 elements inside an ndarray.  


```python
C = np.power= c1**3
C
```
The ndarray named `C` contains the previous ndarray `c1`, which all of its elements are cubed denoted by the function `np.power=c1**3`. 

```python
print('C:',C)
C: [[      1       8      27      64     125     216     343     512     729
     1000]
 [   1331    1728    2197    2744    3375    4096    4913    5832    6859
     8000]
 [   9261   10648   12167   13824   15625   17576   19683   21952   24389
    27000]
 [  29791   32768   35937   39304   42875   46656   50653   54872   59319
    64000]
 [  68921   74088   79507   85184   91125   97336  103823  110592  117649
   125000]
 [ 132651  140608  148877  157464  166375  175616  185193  195112  205379
   216000]
 [ 226981  238328  250047  262144  274625  287496  300763  314432  328509
   343000]
 [ 357911  373248  389017  405224  421875  438976  456533  474552  493039
   512000]
 [ 531441  551368  571787  592704  614125  636056  658503  681472  704969
   729000]
 [ 753571  778688  804357  830584  857375  884736  912673  941192  970299
  1000000]]

```
Expected Output 


```python
div_by_4= C[C % 4 ==0]
div_by_4
```
In this ndarray named `div_by_4` takes all of the elements from ndarray `C` and takes every element that is divisible by 4 denoted by the function `C[C % 4 ==0]`. 
This line of code produces 50 selected elements from the first is 8 and the last is 1,000,000.

```python
print('Cubed values divisible by 4:\n ',div_by_4)
Cubed values divisible by 4:
  [      8      64     216     512    1000    1728    2744    4096    5832
    8000   10648   13824   17576   21952   27000   32768   39304   46656
   54872   64000   74088   85184   97336  110592  125000  140608  157464
  175616  195112  216000  238328  262144  287496  314432  343000  373248
  405224  438976  474552  512000  551368  592704  636056  681472  729000
  778688  830584  884736  941192 1000000]
```
Expected Output 


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
The ndarray named `S1` contains the first 36 positive integers. To produce the 36 positive integers the function `np.arange(1,37)` is use. To put these integers in a 6 x 6 ndarray, the function `reshape(6,6)` is use. The range being at `(1,37)` is similar to the first problem wherein in this case the code is told to create a range of numbers from `1` up to the number before `37`, which is `36`.  

```python
S = np.power = S1**2
S
```
This ndarray named `S` stores all of the elements from the previous ndarray `S1` and squares them denoted by the function `np.power = S1**2`.

```python
print('S:',S)
S: [[   1    4    9   16   25   36]
 [  49   64   81  100  121  144]
 [ 169  196  225  256  289  324]
 [ 361  400  441  484  529  576]
 [ 625  676  729  784  841  900]
 [ 961 1024 1089 1156 1225 1296]]
```
Expected Output 


```python
S_mean = np.mean(S)
S_mean
```
The ndarray `S_mean` calculates the mean of the `S` ndarray by using the function `np.mean(S)`. This results in an output of `450.1666666666667`

```python
print('Mean:\n',S_mean)
Mean:
 450.1666666666667
```
Expected Output


```python
above_mean = S[S>S_mean]
above_mean
```
The ndarray `above_mean` compares the mean of the ndarray `S_mean` to the ndarray `S`, and strictly finds elements higher than the calculated mean. Anything higher will be included and printed in the output. This line of code produces 15 selected elements; the first is 484 and the last is 1296. 

```python
print('Above the mean:\n',above_mean)
Above the mean:
 [ 484  529  576  625  676  729  784  841  900  961 1024 1089 1156 1225
 1296]
```
Expected Output 


```python
np.save('above_mean.npy', above_mean)
```
This line of code is simply to save the elements created in ndarray `above_mean` as a `.npy` file. 




README FILE HISTORY:
August 28 2026 Creation of repository 

August 30 2026 Inputting layout 

September 1 2026 Inputting codes used in the assignment 

September 2 2026 Inputting explanation for each line of code

September 2 2026 Final edits 








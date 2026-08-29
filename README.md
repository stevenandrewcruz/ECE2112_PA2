# ECE2112_PA2
Written and made by Steven Andrew A. Cruz of 2ECE-D

# EXPERIMENT 2: NUMERICAL PYTHON (NUMPY)
The experiment tackles the use of numerical python functions (NumPy) to create and reshape NumPy arrays. To use these functions to perform vectorized numerical operations on an ndarray, compute array statistics and use Boolean conditions to select elements, and as well as save computed NumPy arrays as `.npy` files.



PART A. REPRODUCABLE NORMALIZATION PROBLEM 
Create a reproducible random 5 × 5 integer ndarray named X. Where `¯x` is the mean of all 25 elements and `σ` is their population standard deviation as returned by NumPy’s default `std()` call. Store the normalized array in `X_normalized`.




PART B. CUBES DIVISIBLE BY 4 PROBLEM 
Using NumPy, create the first 100 positive integers, cube every element, and reshape the result into a
10 × 10 ndarray named `C`. Thus, `C` begins with 13 and ends with 1003. Use a Boolean condition on C to obtain every cubed value divisible by 4. Store the selected values in `div_by_4`. Preserve NumPy’s normal row-major selection order.





PART C. ABOVE-MEAN SQUARES PROBLEM 
Create a 6 × 6 ndarray named S containing the squares of the first 36 positive integers in increasing row-major order. Compute the mean of all elements of S and store it in S mean. Then use Boolean filtering to select only the elements strictly greater than S mean. Store these values in above mean

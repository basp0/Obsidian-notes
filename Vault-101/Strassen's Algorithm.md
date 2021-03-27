#CSE222
### Lecture 3
## Matrix Multiplication

$Z_{ij}$ : THe product of ith row of X and jth column of Y

$$Z_{ij} = \sum_{k=1}^{n} X_{i,k} . Y_{k,j} = O(n^3)$$

*Whats the best we can hope for?*
$O(n^2)$
### Divide and Conquer Idea

![[Pasted image 20210302114114.png]]


### Naive Recursive Algorithm

### Step 1: 
Recursively conpute the 8 products
Step 

### Step 2: 
Do the additions

### Runtime 
$T(n) = 8.T(n/2) + O(n^2)=O(n^{\log_28})$

### Optimized Recursive Algorithm

### Step 1: 
Recursively conpute the 7 products

### Step 2: 
Do the additions

### Runtime 
$T(n) = 7.T(n/2) + O(n^2)$
*Applying masters theorem*
$O(n^{2.8704})$


## Lecture 3
## Input
An input array A of (distinct) natural numbres, suppoes 1,2,...n (for this lecture) inn any arbitrary order

### Output
 The number of inversions in the array  = number of pairs (i,j) suck that i<j, but $A[i] >A[j]$

### Divide and Conquer Idea
Suppose A is divided in to X and Y[Each is of size n/2]
An inversion pair(i,j) is :
Suppose A is divided in to X and Y
An inversion pair(i,j) is:
 1. $Left \,inversion$ : Both $(i,j)$ in X
 2. $Right \,inversion$ : Both $(i,j)$ in Y
 3. $Split \,inversion$ :  $(i,j)$ in X,Y respectively

CountInv(array A,length n)
If n=1 return 0;
X  = A[1,2,.....n/2], Y = [n/2 +1,....n]

X = CountInv(X,n/2)
y = CountInv(Y,n/2)
 z= CountSplitInv(X,Y,n)
 Return x+y+z

### How can we count Split inversions in linear time?
* Sort X and Y in CountInv() recursive calls

## $Claim:$
The split inversions involving an element y in the
subarray Y is precisely n/2-i+1, where i is position of the
first pointer when y is copied to D
![[Pasted image 20210302121825.png]]

## Proof
* For all elements $X(1)...X(i-1), y>X(k),k=1,.....i-1$
* " " "  " " X(i)......X(n/2),y<X(k)


### Algorithm
```
X,Y: Sorted arrays of length n/2
Z: Output array of length n, count  = 0
i,j=I
for k= 1 to n
if(X(i) < Y())
D(k)= X(i)
i++
else 
D(k) = Y(j)
j++
count = count + (n/2-1 +I)
```
SortAndCountInv
```
SortAndCountInv(array A,length n)
if n =1 returm  0
X = A[1,2,....n/2], Y= A[n/2+1,...n]
(B, x) = SortAndCountInv (X, n/2)
(C, y) = SortAndCountInv (Y, n/2)
(D, z) = CountAndMerge (B, C, n)
Return x+y+z
```
#CSE222 
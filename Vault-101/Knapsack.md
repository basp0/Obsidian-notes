### Lecture 6

 ## Input
A knapsack of size W > 0 (integer)
n different indivisible items
item i has weight $w_i$> 0 and value $v_i$ > 0 (ints)

## Goal
Fill the knapsack (without overloading) so as
to maximize the total value
## DP Approach
$OPT[i,W]$: Optimal solution considering the items {1,2,.....$i$} and knapsack of size W

$Case\,1:$ item i is not part of the solution $OPT[i,W]$

=> OPT[i-1,W] = OPT[I,W]

$Proof$
Suppose OPT(I-1) $\neq$ OPT(I), and say OPT'(I-1) IS optimal for {1,2,....i-1} and W => OPT'(I-1) is also opt for {1,2,.....$i$}

$Case\,2:$ item i is  part of the solution $OPT[i]$

=> OPT[i,W] = $OPT[i-1,W-w_i]+v_i$) 


## Optimal Substructure

$Case\,1$
item i is not part of the solution $OPT[i-1,W]$
$Case\,2$
item i is part of the solution OPT[i,W] = $OPT[i-1,W-w_i]+v_i$) 

### Proof
#### Strong Induction
P(i,w) : The recursion is correct for all value k= 0,....,i; l=0,...w 
Base Case(s) : $P(0,l)\,\, \forall \,\,l=0,1,....W=0$


Suppose item k is part of the solution $OPT(k,l)$
By strong induction $P(k-1,l-w_k)$ is true
=> $OPT(k,l)$ = $OPT(k-1,l-w_k)+v_k$ 

### Algorithm
M[] = 2D array of size nW
Procedure(i,w):
for w = 0 to w
  	M[0,w] = 0
for i=0 to n
for w= 0 to W
	if($w_i$>$w$)
	M[i,w] = M[i-1,w]
else 
	M[i,w] = $max(Knap(i-1,w),Knap(i-1,w-w_i)+v_i)$
return M[n,W]

#CSE222
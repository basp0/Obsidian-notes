# Problem
Given elements and their frequency of access, arrage elements in a BST so as to minimize average search time.

$$\sum^n_{i=1}p_i.t_i$$

$t_i$ is the search time of $i^{th}$ element

# DP Approach

## Issue 
If we know the right for every subtree, then we are done.

## $Claim:$
If $T$ is $OPT$ for $\{1,2,....,n\}$ and $x$ is the root, then $T_1$ is $OPT$ for $\{1,2,...,x-1\}$, $T_2$ is $OPT$ for   $\{x+1,2,...,n\}$.
![[Pasted image 20210301182417.png]]
## $Proof:$ 
Suppose not true; suppose $T_1$ is not $OPT$ let ${T_1^*}$  be the optimal for subtree.
then, 
cost of presumed opt structure

 Let cost of BST $T_1,T_2,T$ be $C(T_1),C(T_2),C(T)$ respectively
 $$C(T_1) = \sum_{i=1}^{x-1}P_i.(depth\,of\,node)$$$$C(T_2) = \sum_{i=x+1}^{m}P_i.(depth\,of\,node)$$ 
Now, $$C(T) = P_x+\sum_{i=1}^{x-1}p_i*(depth\,of\,node\,+1)+\sum_{i=x+1}^{n}p_i*(depth\,of\,node\,+1)$$
 
 $$C(T)=\sum_{i=1}^{x-1}p_i+\sum_{i=x+1}^{n}p_i+C(T_1)+C(T_2)
$$
  $$but,\,C(T')=\sum_{i=1}^{x-1}p_i+\sum_{i=x+1}^{n}p_i+C(T_1')+C(T_2)
$$
$$and,C(T_1)>C(T_1')$$ $$\therefore C(T)>C(T')$$
$\therefore$C(T') is the optimal solution for i to n, which is a contradiction as we claimed that C(T) is the optimum 


### Reccurence
	
	
$$OPT[i,j] = \min_{k = i \,to\,j}\Bigg\{ \begin{align}P[i,k-1]+P[k+1,j] + P_k \end{align}   $$

$$P[i,i] = P_i \,\,\forall \,\,i={1,2,3..n} $$

### Correctness 
Induction on j-i 
Base case :- P(0) [j=1]
Apply Induction + optimal substructure


### Algorithm
P[1,2,....n][1,2,...m] : 2D Array

for i=1 to n
	$P[i][i] = p_i$
for s=1 to n-1
	$\,\,\,\,\,\,$	for i to n-s
	$$P[i][i+s] = \min_{k = i \,to\,i+s}\Bigg\{ \begin{align}P[i,k-1]+P[k+1,i+s] + P_k \end{align}$$  
return [1,n] 

### Runtime
$n^2 \, entries$ for each entry,  $j-i+1$ operations ~ $\theta(n^3)$
#CSE222
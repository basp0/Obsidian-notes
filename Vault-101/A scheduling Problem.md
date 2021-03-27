![[Pasted image 20210228231030.png]]

## Task 
#### Minimizing Weighted completion time

#### Input:
Jobs $j_1,j_2...j_n$
job $j_i$ has length $l_i$, weight $w_i$ (think as 'priorities')

$Output$: 
A schedule to minimize 
$$\sum_{i=1\,to\,n} w_i.c_i$$
$c_i =$ completion time of job i  

### Greedy Algorithm

Sort the jobs in decreasing (non-increasing) values of $w_i/l_i$

#### Proving correctness
We will use the technique of [[Exchange argument]]

Let $\sigma$ be the greedy schedule
Let $\sigma*$ be the optimal schedule(if possible)

$$
\begin{align}
\sigma\,\,\, = j_1\,j_2\,j_3...j_n \\
\sigma* = j_1\,j_2\,j_3...j_m
\end{align}
$$
 $$w_1/l_1  >w_2/l_2 >w_n/l_n$$
 
 $Claim:$ In $\sigma*$, there has to be two adjacent jobs $j_m,j_k$ such that $$m>k$$ 

$Proof:$ The only schedule where this will not happen is $

$$
\begin{align}
WCT(\sigma^*)  = \sum_{i\neq k,m}c_i^*w_i +c_k^*w_k+c_m^*w_m \\ 
WCT(\sigma')  = \sum_{i\neq k,m}c_i^*w_i +c_k'w_k+c_m'w_m \\
\end{align}

$$
$$
WCT(\sigma')-WCT(\sigma*) = (c'_k-c^*_k)w_k+(c'_m-c^*_m)w_m$$
#CSE222
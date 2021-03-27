## ADA - Lecture 4 
## Interval Selection

#### [[Greedy stays ahead technique]]

let $\sigma,\sigma*$ be two possible interval arrangements. Let $\sigma$ be the greedy arragement 
$$
\begin{align}

\sigma = j_1 \hspace 0.2cm j_2\hspace 0.2cm j_3\hspace 0.2cm ............ \hspace 0.2cmj_k \\
\sigma* =  j_1' \hspace 0.2cm j_2'\hspace 0.2cm j_3'\hspace 0.2cm .......... \hspace 0.2cmj_m
\end{align}
$$
##### Claim 
 For any $l >=1,$
$$ finish(j_l) <= finish(j_l')$$

##### Correctness Proof
** By induction on $l$:**
** Base Case **  
* $l = 1$
* $l$ is minimum
 * Clearly, $finish(j_1) <=finish(j_1')$ (by greedy)

**Induction hypthesis**
* Using strong induction
* True for 1,2,..k

** Inductive step **
$finish(j_k) \leq finish(j_k') \leq start(j_{k+1}')$ 
 
 $Claim:$   For any $l>1, finish(j_l) \leq finish(j_l')$ 
$Theorem:$   $k\geq m$

* $k$ is the number of intervals in greedy
* $m$ is the number of intervals in optimal

$Proof$
Suppose not, that is $k<m$
By Claim, $finish(j_k) \leq finish(j_k')\leq start(j_{k+1}')$
But then, greedy should have included $j_{k+1}'$ since it cannot conflict with any of the jobs $j_1,j_2 ...... j_k$

#CSE222
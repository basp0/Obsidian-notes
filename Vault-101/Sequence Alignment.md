### Lecture 7


## Word Alignment

### Needleman-Wunsch Score
Needleman-Wunsch Score = Cost of mismatches+ cost of gap
(for a specific alignment)
---
### Problem Definition
#### Input:
Two strings $X = X_1X_2X_3 ⋯ X_m$and $Y = Y_1Y_2Y_3 ⋯ Y_m$
where each $xi,i$ = 1,2, ⋯ $m$ and $y_j,j  = 1,2, ⋯ n$
Cost : $\alpha_{a.b}$≥ 0 if $a$ is aligned with $b,\alpha_{gap}$,≥ 0 if some
character is aligned with a gap (-)

### Output

Two strings $\hat{X} = X+gaps,\hat{Y} = Y+gaps$, 

**Minimize**
$$\sum_{r=1}^l \alpha_{\hat{x_r}\hat{y_r}}$$
---
### DP Approach

## Key Step
Identify the subproblems by thinking about the optimal solution
#### Structure of optimal :
$\_\,\_\_\,\_\_\,\_\_\,\_\_\,\_X+gaps\_\,\_\_\,\_\_\,\_\_\,\_\_\,\_$
$\_\,\_\_\,\_\_\,\_\_\,\_\_\,\_Y+gaps\_\,\_\_\,\_\_\,\_\_\,\_\_\,\_$

*How many possibilities for end posititon?*
2 possibilities
* $x_m$ matched with $y_m$ 
* $x_m\,or\,y_n$ matched with gap
 
 #### Subproblems/Opt Substructure

**Define** :
 $X'=X-X_m$ 
$Y'=Y-Y_n$

**Three cases**:
$Case\,\, 1:$
$(x_m,y_n)$ , residual alignment is opt for $(X',Y')$
$Case\,\, 2:$
$(x_m,\_)$ , residual alignment is opt for $(X',Y)$
$Case\,\, 3:$
$(\_,y_n )$ , residual alignment is opt for $(X,Y')$

#### Proof for optimal substructure


$Case\,1:$
 Suppose this is not an optimal solution, then there must be some other configuration of of $X',Y'$ which gives the maximum optimal solution for $X,Y$
Let $O$ be opt for $X',Y'$
Let $O'$ be opt for $X',Y'$ which gives the minimum cost configuration for $X,Y$

Then, 
$OPT[X,Y]$ = Cost($O'$ ) + $\alpha_{x_m,y_n}$
But, Cost (O') > Cost(O)
therefore we can interchange these values in the above equation to get an even smaller optimum which is a contradiction.
$\therefore$ Case 1 is proved
We can use the same logic to prove Case2,3

### Reccurence Relation

$$
OPT[X,Y] = \min\Bigg\{
\begin{align}
 OPT[X',Y']+\alpha_{x_m,y_n} \\OPT[X,Y']+\alpha_{\_,y_n}\,\,\,\,\, \\OPT[X',Y]+\alpha_{x_m,\_}\,\,\,\,
\end{align}$$

#### Base cases

$OPT[X_i,\phi]= i *\alpha_{gap}$  
$OPT[\phi,Y_j]= j *\alpha_{gap}$  

### Algorithm

Let $OPT[i,j]$ represent the optimal solution for matching $X_i$ with $Y_j$
here $1\leq i \leq m$ ** ,   **$1\leq j \leq n$
Procedure(X,Y):
1. for i  = 1 to m:
2. OPT[i,0]  = $i*\alpha_{gap}$
3. for j  = 1 to n:
4. OPT[0,j]  = $j*\alpha_{gap}$ 
5. for i = 1 to m:
6.    for j = 1 to n: 
7.    OPT[i,j] = min(OPT[i-1,j-1]+$\alpha_{i,j}$,OPT[i-1,j]+$\alpha_{i,gap}$,OPT[i,j-1]$\alpha_{gap,j}$)
8. return OPT[m,n]
9. end


### Runtime
$O(n^2)$ algorithm
as we have to iterate from i to m and j to n

#CSE222
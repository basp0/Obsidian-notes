## Input
$$P = {(x_1,y_1),(x2,y_2)....(x_n,y_n))}$$$$d(a,b) = \sqrt{(a_x-b_x)^2=(a_y-b_y)^2}$$$$d(a,b)  =Euclidian\,distance\,in\,2D$$

## Output: 
$a,b : d(a.b)$ is minimum

## Assumption

All points have distinct x and y coordinates
Actually possible to remove the assumption by 'perturbing ' the instance a little bit

### The  1D Case
* Sort the points according to x - coord
* Check every adjacent pair
### Note
Sorting reduces number of comparisons that we need to do

 ### Divide and Conquer : Idea

$P_{x}$: Sorted by x-coordinates
$P_{y}$: Sorted by x-coordinates

**Divide** Step:
Find the median in the pist $P_x$
Split into Q,R at the median 

### Algorithm : High Level

$Closest Pair(P_x,P_y,n)$
if n=2, return distance
Compute $Q_x,Q_y,R_x,R_y$
$\delta_q = ClosestPair(Q_x,Q_y,n/2)$
$\delta_r= ClosestPair(R_x,R_y,n/2)$
$\delta = min\{\delta_q,\delta_r\}$
$\delta_s = ClosestSplitPair(Q_x,Q_y,R_x,R_y,n)$
$return \, min(\delta_s,\delta)$


#### Observation

$$\delta_q = ClosestPair(Q_x,Q_y,n/2)$$$$\delta_r = ClosestPair(R_x,R_y,n/2)$$
We only need to compute the closest split pair correctly if and only if thet are closer than $\delta =min\{\delta_q,\delta_r\}$
#### Lemma
Suppose
(a,b) is the closest split pair and they are closer than $\delta$. Let $a$ appear before $b$ in the list $S_y$. Then $b$ can be at most 7 positions away from a the list.
#### Algorithm for split pair calculation

 $ComputeSplitPair(Q_x,Q_y,R_x,R_y,\delta)$
Compute $S_y$ using ..
$\delta_S=\delta$
for $i=1,2,....|S_y|$
for $j=1,2,...7$
$\delta_S = min\{\delta_s,d(S_y[i],S_y[i+1]) \}$
$return\,\,\delta_S$

#CSE222 
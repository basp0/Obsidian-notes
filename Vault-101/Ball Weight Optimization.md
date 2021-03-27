## Lecture 5
## Input
N balls where the $i^{ith}$ ball has weight $w_i$.
## Goal
Pick balls so that weight is maximum, no two adjacent balls
 
## DP Approach
The optimal soluton for balls $b_1,b_2,...b_n$
Consider ball $b_n$, there are two possible cases
* $Case\,1$:
	Supose $b_n$ is part of the solution, then the maximum possible weight will be W[n] = W[n-2] + $w_n$
* $Case\,2$:
	Supose $b_n$ is not part of the solution, then the maximum possible weight will be W[n] = W[n-1]
	
 ## Algorithm
Sol[i] Contains the maximum weight possible when considering balls till $i^{th}$ ball (inclusive) 
Procedure(i):
Sol[0] = 0
Sol[1] = $w_1$
for i = 2 to n:
 Sol[i]  = $max(Sol[i-2]+w_i,Sol[i-1])$
return Sol[n]
end
#CSE222

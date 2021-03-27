## Problem Statement
We are given a list of n songs, the $i^{th}$ song has a corresponding energy level $s_i$. Jatin has to perform for $n$ nights, the crowd on the $i^{th}$  night has energy level $e_i$ we have to minimize:
$$\sum_i(e_i-s_i)^2$$

#### Proposed Solution for optimal value

Sort the songs in increasing order of energies i.e. si is the song with the ith highest energy.

We will attempt to prove this using the *Exchange Argument* method.

Let $\sigma$ be the ordering produced by the greedy method, and let $\sigma^*$ be the optimal solution, and $\sigma\neq\sigma^*$.

$Claim\,1$:
There exists a pair of songs with energy levels $s_i,s_j$ such that they appear consecutively in $\sigma^*$ but $e_i>e_j$

$Proof$:
Suppose this is not true, then there exists no song suck that $s_i>s_j$ and $i<j$, But this is only true for the permutation $\sigma$, which contradicts our inital assumption, therefore the Claim is true.

$Exchange:$
Construct another solution by swapping positions of the two aforementioned songs.

$Claim\,2$ The sum is minimized after we exchange the two songs.
$Proof:$
The new total summation should evaulate to:
$$\sum_{k\neq i,j}(e_k-s_k)^2 \,\,-(e_i-s_i)^2 - (e_j-s_j)^2 +(e_j-s_i)^2+(e_i-s_j)^2$$

Here, $-(e_i-s_i)^2 -(e_j-s_j)^2 +(e_j-s_i)^2+(e_i-s_j)^2 < 0$, as the positive terms are smaller than the negative terms, as the overall difference between the matched songs is minimized as the higher energy song is matched with the higher energy night.


$\therefore$ the sum is smaller, and our greedy solution is an optimal solution.

 


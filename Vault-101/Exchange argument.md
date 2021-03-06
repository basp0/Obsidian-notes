
### Intro
Greedy algorithms generally take the following form. Select a candidate greedily according to some heuristic, and add it to your current solution if doing so doesn’t corrupt feasibility. Repeat if not finished. ”Greedy Exchange” is one of the techniques used in proving the correctness of greedy algorithms. The idea of a greedy exchange proof is to incrementally modify a solution produced by any other algorithm into the solution produced by your greedy algorithm in a way that doesn’t worsen the solution’s quality. Thus the quality of your solution is at least as great as that of any other solution. In particular, it is at least as great as an optimal solution, and thus, your algorithm does in fact return an optimal solution.

### Main Steps 
After describing your algorithm, the 3 main steps for a greedy exchange argument proof are as follows: 
#### Step 1
 Label your algorithm’s solution, and a general solution. For example, let $A = {a_1, a_2,...,a_k}$ be the solution generated by your algorithm, and let $O = {o_1, o_2,...,o_m}$ be an arbitrary (or optimal) feasible solution. 
#### Step 2
Compare greedy with other solution. Assume that your arbitrary/optimal solution is not the same as your greedy solution (since otherwise, you are done). Typically, you can isolate a simple example of this difference, such as one of the following: 
* there is an element of O that is not in A and an element of A that is not in O, or 
* there are 2 consecutive elements in O in a different order than they are in A (i.e. there is an inversion). 
#### Step 3
 Exchange. Swap the elements in question in O (either swap one element out and another in for the first case, or swap the order of the elements in the second case), and argue that you have a solution that is no worse than before. Then argue that if you continue swapping, you can eliminate all differences between O and A in a polynomial number of steps without worsening the quality of the solution. Thus, the greedy solution produced is just as good as any optimal (or arbitrary) solution, and hence is optimal itself.

 ### Comments 
 * Be careful about using proofs by contradiction starting with the assumption $G \neq O$. Just because your greedy solution is not equal to the selected optimal solution does not mean that greedy is not optimal – there could be many optimal solutions, and your greedy one just isn’t the optimal solution you selected. So assuming $G \neq O$ may not get you any contradiction at all, even if greedy works.
 * You need to argue why the 2 elements you’re swapping even exist out of order, or exist in O but not in A, etc. 1
 *  Remember you need to argue that multiple swaps can get you from your selected solution to greedy, as one single swap will usually not suffice. Also, make sure that any step you make (and not just the first one) doesn’t hurt the solution quality

http://www.cs.cornell.edu/courses/cs482/2007su/exchange.pdf
### Examples where Exchange Argument is Used:
* [[Minimum Spanning Tree]]
* [[A scheduling Problem]]
#CSE222
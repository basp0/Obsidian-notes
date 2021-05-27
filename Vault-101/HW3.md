
## Q2 part (B)
![[question.png]]
### Solution

We will attempt to prove this using an Exchange Argument. 
Let $T^*$ be the optimal spanning tree such that the path widths are maximized.

  
Consider the subgraph $T^*+\{e'\}$, this subgraph contains a cycle.
By the double cross lemma $\exists$ another edge $e$ which crosses the cut.
 $$e \in T^*$$ $$(as\,e\neq e', \,\therefore\,e\,must\, belong \, to \, T^*).$$
Now consider another spanning tree, $T'$ = $T^*$ - {$e$} + {$e'$}
This will be a spanning tree as e and e' form a cycle and cross the same cut.
$\therefore$ Any node reachable because of  $e$, is also reachable due to $e'$, as they both are connected to each other via a cycle.
 
Let u,v be two arbitrary vertices. If u,v lie on different sides of the cut, then let $P',P^*$ be the two different paths connecting the two vertices in the two different spanning trees.

IF e has the smallest weight of all the edges in the path, then  width($P^*$) = weight($e$);

Now, if weight($e'$) > weight($e$), width($P^*$) $<$ width($P'$) as the minimum weighted edge is replaced with a higher weighted edge, thereby  
guaranteeing an increase in the width of $P'$.

Therefore we have proven that at every step, choosing the highest weighted edge leads to path widths >= all alternative options, therefore the Maximum Spanning Tree contains the widest paths between every pair of vertices.    




![[noname.png]]$$Visual\,representation\,of\,cut\,and\,cycle$$



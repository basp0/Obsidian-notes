#CSE222 
# Checking 2-edge connectivity

### $Problem\, Statement$: 
Given an undirected graph, check if it is 2-edge connected

### $Definitions$:
$Two\, edge\,connected :$ If there is an edge in the graph such that if one edge is removed then all the nodes of the graph are still connected

$Bridge\,edge:$ An edge such that upon removal of edge the graph is disconnected

$Back\,edge:$ A back edge is an edge in a graph from one node to one of its ancestors.

### $Solution$:
Trivially, we can do this by removing one edge and checking if the graph is still connected.
This will be $O(|V|^2)$ where V is the number of verticies.

We can also solve this by doing a single DFS traversal, by keeping track of the back edges of nodes.
We can say that if there exists a back edge on a node or in one of its children, to an ancestor of the node, then that node is not part of a bridge edge. 
$\therefore$ if no node satisfies the aforementioned property, i.e no edge  is a bridge edge, then we can say that that graph is 2 edge connected.

### $DFS\, Algorithm$:
```
DFS (V,time):
   `returns the minimum arrival time for all connected nodes to Vertex V`
	 arrival(v) = time++;
	 min = arrival(v);
	 For i in connected(V): //iteration over conencted neighbours of V
		
			if (i is not discovered):
				min = min(min, DFS(i,arrival(v)))
			
			else if (i!= parent(v)):
				if arrival(i) < arrival(v):
				min = min (arrival(i),min);

	if (min < arrival(v)):
		(parent(v),v) form a bridge edge.
	return min 
``` 



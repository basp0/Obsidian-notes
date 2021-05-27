#CSE222 
## Graphs
1. **Adjacency list** An array of linked list
2. **Adjacency matrix**  A n x n array, showing connectivity, symmetric
 
## Graph Traversal Algorithms
### Depth first search:

```
DFS(v)
	Mark v visited

	for each edge (vx)
		if x is unvisited
			DFS(x)
	Mark v explored
```

$Main\, Principle$ : *Keep exploring edges until no new edges are to be found ,  then backtrack*




[[Checking 2-Edge Connectivity]]
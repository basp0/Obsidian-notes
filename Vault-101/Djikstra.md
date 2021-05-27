
# Dijkstra's Algorithm
## Implementation

```
S = {s} (source), dist(s) = 0
dist(v) = inf, for all v != s, S = empty
While S != V do
	w: Such a vertex with a minimum dist(w)
    S = S u {W}
    For all edges( wu ) such that u does not belong to S
    dist(u) = min(dist(u),dist(w) + length(wu))
return  dist
```

### Faster implementation
Use a min heap that contains vertices based on minimum index

### Runtime
1. Heap operation takes $O(logn)$ time
2. We perform this operation for each edge
3. Therefore, the time complexity for the algorithm is $O(|E|log|V|)$
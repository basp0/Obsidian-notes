#CSE222 

# Primm's Algorithm

## $High\,level\,idea$:
In each iteration increase the set size by one .

## $Claim\,1$
Primms returns a spanning tree of the graph.

## Cuts:
Parititon of vetrex set into two parts (not necessarily connected)

*How many cuts are possible?* $2^n$


### Empty cut lemma
G is not connected $\leftrightarrow$ There exists a cut such that no edge crosses the cut.
### Double cross lemma
If any edge e of a cycle crosses a cut C, then some other edge e of C must also cross it.

### Lonely edge collorary:
If e is the only edge crossing some cut, then e cannot be part of any cyle
(A direct consequence of Double Cross Lemma)

#### $Proof$
Suppose the only edge crossing some edge is part of a cycle, this implies there has to be another edge belonging to that cycle. To complete the cycle.

$Prooving\, Claim\,1$
(Primm returns a spanning tree in G)
1. Loop invariant : T spans vertices in S at every iteration.

(Proof by induction)

$Base\,Case$ 
S = {v}, it spans the vertex v
 
$Induction\,Hypothesis$: There is a new vertex has an edge to some vertex in current 

#CSE202
Relational algebra is a procedural query language, which takes instances of relations as input and yields instances of relations as output. It uses operators to perform queries. An operator can be either **unary** or **binary**. They accept relations as their input and yield relations as their output. Relational algebra is performed recursively on a relation and intermediate results are also considered relations.


### Fundamental Operators

*	Select
*	Project
*	Union
*	Set different 
*	Cartesian Product
*	Rename

### Select Operation ($\sigma$)
It selects tuples that satisfy the given predicate from a relation.
**Notation** − σ_p_(r)

Where **σ** stands for selection predicate and **r** stands for relation. _p_ is prepositional logic formula which may use connectors like **and, or,** and **not**. These terms may use relational operators like − =, ≠, ≥, < ,  >,  ≤.
$σ_{subject}$ = $_{"database"}(Books)$
*Output* Selects tuples from books where subject is 'database'
$σ_{subject}$ = $_{"database"\,and\ price = "450"}(Books)$
*Output* Selects tuples from books where subject is 'database'
$σ_{subject}$ = $_{"database"\,and\ price\ =\ "450"\ or\ year>\ "2010"}(Books)$

### Project Operation ($\prod$)
It projects column(s) that satisfy a given predicate.
Also called as vertical partitioning
Notation - $\prod_{A_{1}A_{2}A_{3}}(r)$
where $A_{1}A_{2}A_{3}$ are attribute names of relation $r$
Duplicate rows are automatically eliminated, as relation is a set.
∏subject, author (Books)

### Union Operation (U)
It performs binary union between two given relations and is defined as -  

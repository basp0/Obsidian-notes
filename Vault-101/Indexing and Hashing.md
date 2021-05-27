#CSE202 

# Indexing and Hashing

## Basic concepts
* Indexing used to speed up data accesss
* *Search key* - attribute to set of attributes used to look up records in a file
* An *index file* consists onf records (called index entries) of the form
	 `<search key> <pointer>` 
* Two basic kinds of indexes:
	1. **Ordered Indexes:** Search keys are stored in an oredered form
	2. **Hash Indexes** Search keys are distributed uniformly accross *buckets* using a *hash function*
	

### Index Evaluation metrics
* Access types supported efficiently. E.g.,
records with a specified value in the attribute or records with an attribute value falling in a specified range of values.

* Access time

* Insertion time

* Deletion time

* Space overhead

## Ordered Indexes

* In an ordered index, index entries are stored sorted on the search key value.
Eg author catalog in library

* *Primary Index* in a sequentially ordered file, the index whose search hey specifies the sequential order of the file.
* 

a type of associative array that can map keys to values

a hash table uses a hash function to compute an index into an array of buckets or slots which the desired value can be found.

Ideally - the hash function will assign each key to a unique bucket, but most hash table designs employ an imperfect hash function, which might cause hash collisions where the hash function gnerates the sam eindex for more than on ekey. such collissions must be accomodated in some way.

Advantages
----------

* the main advantage over other table data structures is speed. This advantage is more apparent when the number of entires is large. Hash tables are most efficient when the number of entries can be predicted in advance, so that the bucket array can be allocated once with the optimium size and never resized.
* if the set of key/value pairs is fixed and known ahead of time (i.e. no insertions or deletions) one may reduce the average lookip cost by a careful choice of hash function, bucket table size, and internal data structures. one may even create a perfect hash function.

Drawbacks
---------

* Hash tables are not as efficient when the number of entries is small. Although operations on a hash table take constant time on average, the cost of a good hash function can be significantly higher than the inner loop of the lookup algorithm for a sequential list or search tree
* The entries stored in a hash table can be enumerated efficiently (at constant cost per entry), but only in some pseudo-random order.
* If the keys are not stored (because the hash function is collision-free), there may be no easy way to enumerate the keys that are present in the table at any given moment
* Although the *average* cost per operation is constant and fairly small, the cost of a single operation may be quite high. In particular, if the hash table uses [dynamic resizing](https://www.wikiwand.com/en/Hash_table#Dynamic_resizing), an insertion or deletion operation may occasionally take time proportional to the number of entries. This may be a serious drawback in real-time or interactive applications.
* Hash tables in general exhibit poor [locality of reference](https://www.wikiwand.com/en/Locality_of_reference)—that is, the data to be accessed is distributed seemingly at random in memory.
* Hash tables become quite inefficient when there are many collisions

Hashing
-------

The idea of hasing is to distribute entires - key/value pairs - across an array of buckets.

Given a key, the algorithm computes an index that suggests where the entry can be found.

```haskell
hash = hashfunc key
index = hash % arraySize
```

Choosing a hash function
------------------------

a hash function should provide a uniform distribution of hash values.

### Perfect hash function

if all keys are known ahead of time , a perfect hash function can be used to create a perfect hash table that has no collissions. If minimal perfect hashing use used, every location in the hash table can be used as well.

Perfect hashing allows for constant time lookup in all cases. This is in contrast to most chaining and open addressing methods, where the time for lookup is low on average, but mamay be very large, O(n), for instance when all the keys hash to a few values.

Key statistics
--------------

**load factor = n / k**

where n is the number of entries occupied in the has table

 k is the number of buckets

as the load factor grows larger, the hashtable becomes slower and may even feel to work in some cases.

Collision resolution
--------------------

hash collisions are practically unavoidable when hashing a random subset of a large set of possible keys.

almost all hash table implementations have some collision resolution strategy.

all methods require that the keys (or pointers to them) be stored in a table, together with the associated values.

maybe detail different strategies?

Dynamic resizing
----------------

stuff about this too?
**Big O**

Access O(1)

Search O(n)

Insertion O(n)

Deletion O(n)

 RAM is *basically* an array already.

1. **Each item in the array is the *same size*** (takes up the same number of bytes).
2. **The array is *uninterrupted* (contiguous) in memory**. There can't be any gaps in the array...like to "skip over" a memory slot Spotify was already using.

can use pointers to point to items of variable size.

That's the tradeoff. This pointer-based array requires less uninterrupted memory and can accommodate elements that aren't all the same size, *but* it's *slower* because it's not cache-friendly.

#### Strengths:

* **Fast lookups**. Retrieving the element at a given index takes O(1)O(1) time, regardless of the length of the array.
* **Fast appends**. Adding a new element at the end of the array takes O(1)O(1) time.

#### Weaknesses:

* **Fixed size**. You need to specify how many elements you're going to store in your array ahead of time. (Unless you're using a fancy dynamic array.)
* **Costly inserts and deletes.** You have to ["scoot over" the other elements to fill in or close gaps](https://www.interviewcake.com/concept/cpp/array?course=fc1&section=array-and-string-manipulation#inserting), which takes worst-case O(n)O(n) time.
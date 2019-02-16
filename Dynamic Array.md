Other names: 
array list, growable array, resizable array, mutable array

#### Strengths:

* **Fast lookups**. Just like arrays, retrieving the element at a given index takes O(1)O(1) time.
* **Variable size**. You can add as many items as you want, and the dynamic array will expand to hold them.
* **Cache-friendly**. Just like arrays, dynamic arrays place items right next to each other in memory, making efficient use of caches.

#### Weaknesses:

* **Slow worst-case appends**. Usually, adding a new element at the end of the dynamic array takes O(1)O(1) time. *But* if the dynamic array doesn't have any room for the new item, [it'll need to expand](https://www.interviewcake.com/concept/cpp/dynamic-array?course=fc1&section=array-and-string-manipulation#doubling_appends), which takes O(n)O(n) time.
* **Costly inserts and deletes.** Just like arrays, elements are stored adjacent to each other. So adding or removing an item in the middle of the array [requires "scooting over" other elements](https://www.interviewcake.com/concept/array#inserting), which takes O(n)O(n) time.

When you allocate a dynamic array, your dynamic array implementation makes an *underlying fixed-size array*. The starting size depends on the implementation—let's say our implementation uses 10 indices. Now say we append 4 items to our dynamic array. At this point, our dynamic array has a length of 4\. But the *underlying array* has a length of 10.

We'd say this dynamic array's **size** is 4 and its **capacity** is 10\. The dynamic array stores an **endIndex** to keep track of where the dynamic array ends and the extra capacity begins.3£

When you allocate a dynamic array, your dynamic array implementation makes an underlying static array. The starting size depends on the implementation—let's say our implementation uses 10 indices:

![A blank dynamic array created by default with 10 indices.](resources/EA56737048945F902F71F64A46E89A90.svg?bust=190)

Say you append 4 items to your dynamic array:

![The same dynamic array storing the word "Dear."](resources/B24284EA8E8F05E556A67079C5B2BE5D.svg?bust=190)

At this point, our dynamic array contains 4 items. It has a length of 4\. But the underlying arrayhas a length of 10.

We'd say this dynamic array's size is 4 and its capacity is 10.

![Our dynamic array now has a size of 4 and a capacity of 10.](resources/D0E6612D07A78AE70FBB74E86872ECCB.svg?bust=190)

The dynamic array stores an end\_index to keep track of where the dynamic array ends and the extra capacity begins.

![The end\_index of our dynamic array is marked at index 3, where the last letter of the word "Dear" is stored.](resources/48967333318984F228F6B64215C2AD84.svg?bust=190)

If you keep appending, at some point you'll use up the full capacity of the underlying array:

![After adding 6 characters to form the string "Dear Mothe," the end\_index of our dynamic array is now marked at index 9, meaning the dynamic array is full.](resources/407C48EBF76CB06903C688A60C023BE5.svg?bust=190)

Next time you append, the dynamic array implementation will do a few things under the hood to make it work:

1\. Make a new, bigger array. Usually twice as big.

Why not just extend the existing array? Because that memory might already be taken. Say we have Spotify open and it's using a handful of memory addresses right after the end of our old array. We'll have to skip that memory and reserve the next 20 uninterrupted memory slots for our new array:

![A new dynamic array, twice as big as the old dynamic array, is created in order to make more room.](resources/F9446201F73B1A2DC2E163CDEF08F8D7.svg?bust=190)

2\. Copy each element from the old array into the new array.

![Each element from the old dynamic array is copied into the new dynamic array.](resources/CF32986CA6C1FF7D8CE5E440FBD49385.svg?bust=190)

3\. Free up the old array. This tells the operating system, "you can use this memory for something else now."

![The old array is forgotten because it is no longer necessary.](resources/77047EC0D13050D1D6914630B0048FCB.svg?bust=190)

4\. Append your new item.

![The new element, the letter "r," is finally appended to our new array.](resources/928475694003A4CD860ABC8CD0AE075B.svg?bust=190)

We could call these special appends "doubling" appends since they require us to make a new array that's (usually) double the size of the old one.

Appending an item to an array is usually an O(1)O(1) time operation, but a single doubling append is an O(n)O(n) time operation since we have to copy all nn items from our array.

Does that mean an append operation on a dynamic array is always worst-case O(n)O(n) time? Yes. So if we make an empty dynamic array and append nn items, that has some crazy time cost like O(n^2)O(n​2​​)or O(n!)O(n!)?!?! Not quite.

While the time cost of each special O(n)O(n) doubling append doubles each time, the number of O(1)O(1)appends you get until the next doubling append also doubles. This kind of "cancels out," and we can say each append has an average cost or amortized cost of O(1)O(1). ↴

Given this, in industry we usually wave our hands and say dynamic arrays have a time cost of O(1)O(1)for appends, even though strictly speaking that's only true for the average case or the amortizedcost.

In an interview, if we were worried about that O(n)O(n)-time worst-case cost of appends, we might try to use a normal, non-dynamic array.

The advantage of dynamic arrays over arrays is that you don't have to specify the size ahead of time, but the disadvantage is that some appends can be expensive. That's the tradeoff.
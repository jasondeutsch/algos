**a linked list is a linear collection of data elements, whose order is not given by their physical placement in memeory. Instead, each element points to the next. It is a data structure of a collection of nodes which together represent a sequence.**

**
**

Linked lists can be used to implement other abstract data types include lists, stcks, queues, associative arrays and S-expressions.

*the principle benefit of a linked list over a conventional array is that list elements can easily be inserted or removed without reallocation or reorganizatino of the entire structure because data items need not be stored contiguously in memeory or on disk.*

*
*

*however - linked lists by themselves do not allow random access to the data or any form of efficient indexing.*

*
*

*
*

### Disadvantges

1\. They use more memory than arrays because of the storage used by their pointers.

2\. Nodes in a linked list must be read in order from beggining as linked lists are inherently sequential access. 

3\. Nodes are stored incontiguously, greatly increasing the time periods requred to access individual elements within the list.

4\. difficulties arries when it comes to reverse traversing — a back pointer can work but requires additional space in memory.

So if linked lists are so great, why do we usually store strings in an array? **Because [arrays have O(1)O(1)-time lookups](https://www.interviewcake.com/article/cpp/data-structures-coding-interview?course=fc1&section=algorithmic-thinking#constant-time-array-lookups).** And those constant-time lookups *come from* the fact that all the array elements are lined up next to each other in memory.

Lookups with a linked list are more of a process, because we have no way of knowing where the iith node is in memory. So we have to walk through the linked list node by node, counting as we go, until we hit the iith item.

### Kinds of linked lists

**Singly linked list**

each node has a next pointer, a pointer to the next node in the sequence

**Doubly linked list**

each node has a next pointer as well as a back pointer the previous node

**Multiply linked list**

each node contains two or more link fields, each field being used to connect the same set of data records in a different order of the same et, eg by name, date of birth or some other arbitrary value.

**Circular linked list**

the last note of a linked linked list usually contains a null reference as its next pointer.

A less common convention is to make it point to the first node of the list.

### Big O

Access: O(1)

Search: O(n)

Insertion: O(1)

Deletion: O(1)

### Speeding up search[](https://en.wikipedia.org/w/index.php?title=Linked_list&action=edit&section=28)

Finding a specific element in a linked list, even if it is sorted, normally requires O(*n*) time ([linear search](https://www.wikiwand.com/en/Linear_search)). This is one of the primary disadvantages of linked lists over other data structures. In addition to the variants discussed above, below are two simple ways to improve search time.

In an unordered list, one simple heuristic for decreasing average search time is the *move-to-front heuristic*, which simply moves an element to the beginning of the list once it is found. This scheme, handy for creating simple caches, ensures that the most recently used items are also the quickest to find again.

Another common approach is to "[index](https://www.wikiwand.com/en/Index_(database) "Index (database)")" a linked list using a more efficient external data structure. For example, one can build a [red-black tree](https://www.wikiwand.com/en/Red-black_tree) or [hash table](https://www.wikiwand.com/en/Hash_table "Hash table") whose elements are references to the linked list nodes. Multiple such indexes can be built on a single list. The disadvantage is that these indexes may need to be updated each time a node is added or removed (or at least, before that index is used again).

### Random access lists[](https://en.wikipedia.org/w/index.php?title=Linked_list&action=edit&section=29)

A random access list is a list with support for fast random access to read or modify any element in the list.[[9]](https://www.wikiwand.com/en/Linked_list#citenoteokasaki10) One possible implementation is a skew binary random access list using the [skew binary number system](https://www.wikiwand.com/en/Skew_binary_number_system), which involves a list of trees with special properties; this allows worst-case constant time head/cons operations, and worst-case logarithmic time random access to an element by index.[[9]](https://www.wikiwand.com/en/Linked_list#citenoteokasaki10) Random access lists can be implemented as [persistent data structures](https://www.wikiwand.com/en/Persistent_data_structure).[[9]](https://www.wikiwand.com/en/Linked_list#citenoteokasaki10)

Random access lists can be viewed as immutable linked lists in that they likewise support the same O(1) head and tail operations.[[9]](https://www.wikiwand.com/en/Linked_list#citenoteokasaki10)

A simple extension to random access lists is the min-list, which provides an additional operation that yields the minimum element in the entire list in constant time (without[*[clarification needed](https://www.wikiwand.com/en/Wikipedia:Please_clarify)*] mutation complexities).

questions and things to know
----------------------------

1\. Implant 

2\. how to reverse a linked list
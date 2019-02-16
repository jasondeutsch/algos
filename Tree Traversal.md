the processes of visting each node in a tree structure exactly once.

traversals are classified by the order in whch the nodes are visited.

Depth first search
------------------

the general recursive pattern for traversing a non empty binary tree:

at node N do the following

(L) recursively traverser its left subtree. This step is finished at the node N again.

(R) recursivly traverse its right subtree. this step is finsed at the node N again

(N) Process N itself

Breadth first search
--------------------

trees can be traversed in level-order, where we visit every node on a loevel before going to a lower level.
ychamudot
jasonmg


=============================
=      File description     =
=============================
AvlTree.java: Implements the AvlTree class, which extends the BinarySearchTree class. Contains methods
used for adding and removing elements from an Avl Tree, while maintaining the BST and height-balance
properties of an Avl Tree. Also contains three different constructors for the class.
AvlNode.java: Implements the AvlNode class, which itself implements the TreeNode interface. Contains methods
for calculating the height of a node in an Avl Tree, as well as constructors specific to an Avl Node
TreeNode.java: An interface to be implemented by node objects to be used in BinarySearchTrees
BinarySearchTree.java: An abstract class representing any tree that implements the BST balance. Contains
concrete methods for determining whether a certain value is contained in the tree, finding the size of the
tree, and iterating over the elements of the tree.


=============================
=          Design           =
=============================
Our main class, AvlTree, extends the abstract BinarySearchTree class. The node used in the AvlTree, AvlNode,
implements the TreeNode interface.
Our design goal was to implement the Avl Tree while also providing a framework for implementations of other
types of Binary Search Trees. For this reason, we made the methods of AvlTree that are generally applicable to
 other BSTs, available in the abstract BinarySearchTree class. We also included a TreeNode interface to allow
 someone who wants to expand the project to understand what a node of a BST needs to be able to do.

=============================
=  Implementation details   =
=============================
1. in addition to AvlTree, we created an AvlNode class which is designed to work as part of an AvlTree. This
is because the AvlNode needs more specialized height and balance calculating abilities that nodes in other
types of trees may not necessarily use. AvlNode is an implementation of the TreeNode interface, and AvlTree is
an extension of the BinarySearchTree abstract class. The BinarySearchTree class contains methods for building
an iterator for any BST, calculating the size of a BST, and determining whether a BST contains a given value.
These two classes allow the project to be expanded relatively simply, by implementing the required methods
in TreeNode and BinarySearchTree and adding methods specific to a different class of BST.

2. Both the add() and remove() methods begin by performing a standard BST iteration to find the correct
location of the given value. That is, beginning at the root, the program recursively searches the left subtree
 if the value is less than the root value and the right subtree if the value is greater than the root value.
 Once the correct location is found, add() adds the new node, and climbs back up the tree while adjusting the
 heights of the nodes. For every node, the height and balance are checked and if the node is unbalanced it is
 rotated. This continues until the search has reached and balanced the tree's root.
 Delete works similarly, except when deleting the targeted node it must contend with reassigning the deleted
 node's children, if there are any. Once the node's children are properly reassigned, the tree is rebalanced
 recursively.
 We wrote a few helper methods that are shared by add and remove. In AvlNode we have a method to readjust a 
 node's height after an addition or deletion has occurred. In AvlTree we have two methods, rotateRight and 
 rotateLeft, to carry out the rotations on an unbalanced node. Finally we have a method to determine the 
 balance of an AvlNode.


=============================
=    Answers to questions   =
=============================
5.1:
The following 12 numbers, when inserted in this order into an AVL tree, will produce a tree with height 4:
8, 5, 11, 3, 7, 10, 12, 2, 4, 6, 9, 1

5.2:
1. The complexity of constructing an Avl Tree using the AvlTree(int[] data) constructor is O(nlogn). Each
insertion runs in O(logn) (performing rotations in O(1)), and we insert n nodes. So the result is n * logn.
2. The best possible runtime for constructing an Avl tree from an array is O(n). If we were given a sorted
array of integers, we could find the middle element in O(1). We would add that element first. Then we would
find the middle elements of the left and right subarrays and add them. We saw an example of adding elements
in this order in question 5.1. By doing this recursively, adding all the elements would only take O(n) runtime
.


5.3:
1. The asymptotic runtime of constructing a deep-copied Avl Tree is O(nlogn). The naive method of copying an
Avl Tree involves iterating over the elements of the old tree, creating new, copied nodes, and using the add
method to add them to the new tree. This would run in O(log n) for every node, therefore the runtime would
approach O(nlogn) for n nodes.
2. The best possible runtime for a specific case would be O(n), if the AvlTree to be copied is 
5.4:
1. Our implementation of findMinNodes uses a formula derived from the golden ratio to calculate the sum of two
 minimum subtrees. Therefore, it does not need to use recursion to traverse all the possible subtrees and
 calculate their heights. Therefore the asymptotic runtime is O(1).
 2. Our implementation has the best possible running time complexity.



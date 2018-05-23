ychamudot
jasonmg


=============================
=      File description     =
=============================


=============================
=          Design           =
=============================
=============================
=  Implementation details   =
=============================


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
1. The complexity of creating a deepCopy of an Avl Tree in our implementation is also O(nlogn). We iterate
over the elements of the old tree in O(n) in ascending order, and add the data to the new tree in O(log n).
Therefore the
runtime is n * logn = O(nlogn) as in the first constructor
2. The runtime of our constructor for deepcopying an Avl tree will always be O(nlogn). No matter how the
original tree is constructed, it will always take us the same amount of time to iterate over the elements
and add them to the new tree one by one.
5.4:
1. Our implementation of findMinNodes uses a formula derived from the golden ratio to calculate the sum of two
 minimum subtrees. Therefore, it does not need to use recursion to traverse all the possible subtrees and
 calculate their heights. Therefore the asymptotic runtime is O(1).
 2. Our implementation has the best possible running time complexity.



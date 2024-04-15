[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/9YUeXH71)
# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

Add your answers to this markdown file.

If the sorting algorithm can sort in O(n) time, then the time it would take to sort would increase linearly the larger the input size (n) gets. So we could do what we did in theory vs practice and give it a
smaller list, time it, then give it a larger list and time it. We should pass sorted lists, reverse sorted lists, and unsorted lists lists of every type such as strings, characters, etc to ensure that it grows
linearly nomatter the element type. We should also be sure to pass lists with duplicate values, and smaller and larger lists to see if it works with all sizes of lists. By timing these differences, we could see
if the time it took to sort the lists increased linearly. We should also run this a number of times to make sure our values are consistent. We must all consider how constant factors and dropped lower order terms
affect the time complexity. To minimize these, we should use the same, efficient machine to run the tests, and should minimize any other programs running concurrently. If after those kinds of tests, the time 
increases linearly with the input size, then we could say that it sorts in O(n) time. 

In class we discussed the complexity of a general sorting problem being at least $\Omega (n log n)$. This is true for any comparison based sorting algorithm. This can be shown by a tree, where 
every possible ordering of an array is a leaf and the decision points / comparisons are the branches. If we have an array that needs to be sorted of size n, then there must be n! leaves on the tree because there
are n! possible permutations of the array. So the number of leaves is n!. If the sorting algorithm X takes O(n) time, then it wouldn't actually be able to correctly sort the elements because it needs to be able 
to access all of the leaves, and not have leaves missing. There are n! leaves, and this cannot be done in O(n) time. For this reason, X is not correct.

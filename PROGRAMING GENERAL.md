PROGRAMING GENERAL


NICE LINKS:  [INTERVIEW QUESTIONS ](https://github.com/MaximAbramchuck/awesome-interview-questions#android)

## General Developer Questions
* How familiar you are with the Android and Google Guidelines?

* Describe Test-Driven Development. [[info]](http://en.wikipedia.org/wiki/Test-driven\_development)

* Explain unit tests versus functional tests.

* Describe Scrum and Kanban.

* What project management tools have you used?

* How do you ensure that you are working efficiently?

* Do you have basic familiarity with working on the command line i.e. Gradle, Ant, or the Java Compiler?

hero

### Data Structures And Algorithms

> The level of questions asked on the topic of Data Structures And Algorithms totally depends on the company for which you are applying.

#### Whiteboard Interview Series - Data Structures and Algorithms on Youtube - [Check here](https://www.youtube.com/playlist?list=PLqOiaH9id5qt_lZl2bFi8q9RQoV1JJUpf)

#### Tech Interview Preparation Kit - [Check here](https://afteracademy.com/tech-interview)

#### Android Developer should know these Data Structures for Next Interview - [Check here](https://blog.mindorks.com/android-developer-should-know-these-data-structures-for-next-interview)

* **Complexity Analysis** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/complexity-analysis)
    - What is Input, Output, Correctness, Efficiency of Algorithms?
    - What is Input Size and Running Time of Algorithms?
    - Explain the Worst, Best, and Average case analysis of Algorithms.
    - What is Big-O Notation with respect to Time and Space Complexity?

*  **Iteration and Two Pointer Approach** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/iteration-and-two-pointer-approach)
    - Explain Initialization, Maintenance, and Termination used in iteration.
    - Explain the use-case of Two Pointer approach

* **Recursion and Divide & Conquer Approach** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/recursion-and-divide-and-conquer-approach)
    - Explain Recursion with the help of an example and also draw the recursion call stack for the same.
    - How will you analyse the recursive solution of some problem?
    - Is there any difference between Recursion and Iteration?
    - Explain the Divide and Conquer technique with the help of a real-world example.

* **Arrays and Linked List** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/array-and-linked-list)
    - What do you mean by Linear Data Structures?
    - Explain the basic operations that can be performed on Arrays? Also, tell about Amortized analysis of array.
    - What is a Linked List? Explain with an example by performing some operations on Linked List.
    - What are the types of Linked List?
    - Can you tell the difference between an Array and a Linked List?

* **Stack and Queue** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/stack-and-queue)
    - What is a Stack? Explain various operations that can be performed on a Stack.
    - Can you implement Stack using an Array or using a Linked List? How?
    - What is a Queue? Explain various operations that can be performed on a Queue.
    - Can you implement Queue using an Array or using a Linked List? How?
    - Is there any difference between a Stack and a Queue?

* **Sorting Algorithms** - [Wikipedia](https://en.wikipedia.org/wiki/Sorting_algorithm?oldformat=true)
    - Using the most efficient sorting algorithm (and correct data structures that implement it) is vital for any program, because data manipulation can be one of the most significant bottlenecks in case of performance and the main purpose of spending time, determining the best algorithm for the job, is to drastically improve said performance. The efficiency of an algorithm is measured in its' "Big O" ([StackOverflow](https://stackoverflow.com/questions/487258/what-is-a-plain-english-explanation-of-big-o-notation)) score. Really good algorithms perform important actions in O(n log n) or even O(log n) time and some of them can even perform certain actions in O(1) time (HashTable insertion, for example). But there is always a trade-off - if some algorithm is really good at adding a new element to a data structure, it is, most certainly, much worse at data access than some other algorithm. If you are proficient with math, you may notice that "Big O" notation has many similarities with "limits", and you would be right - it measures best, worst and average performances of an algorithm in question, by looking at its' function limit. It should be noted that, when we are speaking about O(1) - constant time - we are not saying that this algorithm performs an action in one operation, rather that it can perform this action with the same number of operations (roughly), regrardless of the amount of elements it has to take into account. Thankfully, a lot of "Big O" scores have been already calculated, so you don't have to guess, which algorithm or data structure will perform better in your project. ["Big O" cheat sheet](http://bigocheatsheet.com/)
    - Bubble sort [Wikipedia](https://en.wikipedia.org/wiki/Bubble_sort?oldformat=true) 
        - Bubble sort is one of the simplest sorting algorithms. It just compares neighbouring elements and if the one that precedes the other is smaller - it changes their places. So over one iteration over the data list, it is guaranteed that **at least** one element will be in its' correct place (the biggest/smallest one - depending on the direction of sorting). This is not a very efficient algorithm, as highly unordered arrays will require a lot of reordering (upto O(n^2)), but one of the advantages of this algorithm is its' space complexity - only two elements are compared at once and there is no need to allocate more memory, than those two will occupy. 
            <table>
                <tr>
                    <th colspan="3" align="center">Time Complexity</th>
                    <th align="center">Space Complexity</th>
                </tr>
                <tr>
                    <th align="center">Best</th>
                    <th align="center">Average</th>
                    <th align="center">Worst</th>
                    <th align="center">Worst</th>
                </tr>
                <tr>
                    <td align="center">Ω(n)</td>
                    <td align="center">Θ(n^2)</td>
                    <td align="center">O(n^2)</td>
                    <td align="center">O(1)</td>
                </tr>
            </table>
    - Selection sort [Wikipedia](https://www.wikiwand.com/en/Selection_sort) 
        - Firstly, selection sort assumes that the first element of the array to be sorted is the smallest, but to confirm this, it iterates over all other elements to check, and if it finds one, it gets defined as the smallest one. When the data ends, the element, that is currently found to be the smallest, is put in the beginning of the array. This sorting algorithm is quite straightforward, but still not that efficient on larger data sets, because to assign just one element to its' place, it needs to go over all data.
            <table>
                <tr>
                    <th colspan="3" align="center">Time Complexity</th>
                    <th align="center">Space Complexity</th>
                </tr>
                <tr>
                    <th align="center">Best</th>
                    <th align="center">Average</th>
                    <th align="center">Worst</th>
                    <th align="center">Worst</th>
                </tr>
                <tr>
                    <td align="center">Ω(n^2)</td>
                    <td align="center">Θ(n^2)</td>
                    <td align="center">O(n^2)</td>
                    <td align="center">O(1)</td>
                </tr>
            </table>
    - Insertion sort [Wikipedia](https://en.wikipedia.org/wiki/Insertion_sort?oldformat=true)
        - Insertion sort is another example of an algorithm, that is not that difficult to implement, but is also not that efficient. To do its' job, it "grows" sorted portion of data, by "inserting" new encountered elements into already (innerly) sorted part of the array, which consists of previously encountered elements. This means that in best case (data is already sorted) it can confirm that its' job is done in Ω(n) operations, while, if all encountered elements are not in their required order as many as O(n^2) operations may be needed.
            <table>
            <tr>
                <th colspan="3" align="center">Time Complexity</th>
                <th align="center">Space Complexity</th>
            </tr>
            <tr>
                <th align="center">Best</th>
                <th align="center">Average</th>
                <th align="center">Worst</th>
                <th align="center">Worst</th>
            </tr>
            <tr>
                <td align="center">Ω(n)</td>
                <td align="center">Θ(n^2)</td>
                <td align="center">O(n^2)</td>
                <td align="center">O(1)</td>
            </tr>
            </table>
    - Merge sort [Wikipedia](https://en.wikipedia.org/wiki/Merge_sort?oldformat=true)
        - This is a "divide and conquer" algorithm, meaning it recursively "divides" given array in to smaller parts (up to 1 element) and then sorts those parts, combining them with each other. This approach allows merge sort to achieve very high speed, while  doubling required space, of course, but today memory space is more available than it was a couple of years ago, so this trade-off is considered acceptable.   
            <table>
            <tr>
                <th colspan="3" align="center">Time Complexity</th>
                <th align="center">Space Complexity</th>
            </tr>
            <tr>
                <th align="center">Best</th>
                <th align="center">Average</th>
                <th align="center">Worst</th>
                <th align="center">Worst</th>
            </tr>
            <tr>
                <td align="center">Ω(n log(n))</td>
                <td align="center">Θ(n log(n))</td>
                <td align="center">O(n log(n))</td>
                <td align="center">O(n)</td>
            </tr>
            </table>
    - Quicksort [Wikipedia](https://en.wikipedia.org/wiki/Quicksort?oldformat=true)
        - Quicksort is considered, well, quite quick. When implemented correctly, it can be a significant number of times faster than its' main competitors. This algorithm is also of "divide and conquer" family and its' first step is to choose a "pivot" element (choosing it randomly, statistically, minimizes the chance to get the worst performance), then by comparing elements to this pivot, moving it closer and closer to its' final place. During this process, the elements that are bigger are moved to the right side of it and smaller elements to the left. After this is done, quicksort repeats this process for subarrays on each side of placed pivot (does first step recursively), until the array is sorted.
                <table>
                <tr>
                    <th colspan="3" align="center">Time Complexity</th>
                    <th align="center">Space Complexity</th>
                </tr>
                <tr>
                    <th align="center">Best</th>
                    <th align="center">Average</th>
                    <th align="center">Worst</th>
                    <th align="center">Worst</th>
                </tr>
                <tr>
                    <td align="center">Ω(n log(n))</td>
                    <td align="center">Θ(n log(n))</td>
                    <td align="center">O(n^2)</td>
                    <td align="center">O(n)</td>
                </tr>
                </table>  
    - There are, of course, more sorting algorithms and their modifications. We strongly recommend all readers to familiarize themselves with a couple more, because knowing algorithms is very important quality of a candidate, applying for a job and it shows understanding of what is happening "under the hood".

* **Binary Tree** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/binary-tree)
    - What are non-linear data structures? Give example.
    - What is a Tree Data Structure? Explain the properties of tree with an example.
    - How is Binary Tree different from a normal Tree?
    - What is inorder, pre-order, post-order, and level-order traversal of a tree? Explain with an example.
    - Can you find the inorder, pre-order, and post-order of a tree using Stack? How?
    - Explain how searching, insertion, and deletion operations are performed on a Tree?

* **Binary Search Tree** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/binary-search-tree)
    - What is a Binary Search Tree? Explain its properties also.
    - Explain how searching, insertion, and deletion operations are performed on a Binary Search Tree?
    - How is Binary Search Tree different from Binary Tree?

* **Heap and Priority Queue** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/heap-and-priority-queue)
    - What is a Heap data structure and when it is used?
    - Explain the operations that can be performed on a Heap.
    - What is the difference between a min-heap and a max-heap? How to implement these two?
    - What do you mean by Priority Queue? How to implement Priority Queue?
    - What are the real-life applications of Priority Queue?

* **Hash Table** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/hash-table)
    - What do you mean by Direct Address Table?
    - Can you perform search, insert, and delete in O(1)? How?
    - Explain Hash Table and its properties.
    - How to remove collision in Hash Table by Chaining and Open Addressing?
    - What are the real-life applications of Hash Table?

* **Dynamic Programming** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/dynamic-programming)
    - What is Dynamic Programming and how to find if a problem can be solved using DP or not?
    - What are two approaches of solving a Dynamic Programming problem?
    - Explain Optimization and Combinatorial problems?

* **Greedy Algorithms** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/greedy-algorithms)
    - What do you mean by Greedy algorithms? How to find if a problem can be solved by Greedy approach or not?
    - Is there any difference between Dynamic Programming and Greedy Algorithms?

* **Backtracking** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/backtracking)
    - What is Backtracking?
    - How to find if a problem can be solved with Backtracking or not?
    - What is Exhaustive Searching?

* **Graph** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/graph)
    - What is Graph and how to represent a Graph?
    - Explain Depth First Search and Breadth First Search.
    - How to represent a Graph? 
    - What are the real-life applications of Graph?
    - What do you mean by Topological Sorting?
    - Explain Dijkstra algorithm with an example.
    - What is a Minimum Spanning Tree?



### Common Coding Programs
* <b>Arrays</b></br>
  * [Find Maximum Sell Profit](/src/arrays/FindMaximumSellProfit.java)
  * [Find Low & High Index of a key from a given array](/src/arrays/LowHighIndex.java)
  * [Merge Overlapping Intervals](/src/arrays/MergeOverlappingIntervals.java)
  * [Move all zeros in an array to the Left or Right](/src/arrays/MoveZeroesToLeft.java)
  * [Rotate an array](/src/arrays/RotateArray.java)
  * [Find the smallest common number in a given array](/src/arrays/SmallestCommonNumber.java)
  * [Find the sum of two elements in a given array](/src/arrays/SumOfTwoValues.java)
  * [Find the minimum distance between two numbers in an array](/src/arrays/MinimumDistanceBetweenTwoNumbers.java)
  * [Find the maximum difference between the values in an array such that the largest values always comes after the smallest value](/src/arrays/FindMaxDifference.java)
  * [Find second largest element in an array](/src/arrays/FindSecondLargestElement.java)
  * [Find the 3 numbers in an array that produce the max product](/src/arrays/FindMaxProduct.java)
  * [Find missing number from an array](/src/arrays/FindMissingNumber.java)  
  </br>



* <b>Dynamic Programming</b></br>
   * [Fibonacci Series](/src/dynamicprogramming/FibonacciSeries.java)
   * [Given an array, find the contiguous subarray with the largest sum](/src/dynamicprogramming/LargestSumSubarray.java)
   * [Find the maximum sum of a subsequence such that no consecutive elements are part of the subsequence](/src/dynamicprogramming/MaxSumSubsequenceOfNonadjacentElements.java)
   * [Given a score "n", find the total number of ways score "n" can be reached](/src/dynamicprogramming/GameScoring.java)
   * [Compute Levenshtein distance between two strings](/src/dynamicprogramming/LevenshteinDistance.java)
   * [Given coin denominations and the total amount, find out the number​ of ways to make the change](/src/dynamicprogramming/CoinChangingProblem.java)   
   </br>
   
   
   
* <b>Queues</b></br>
   * [Find the Maximum in a Sliding Window](/src/queue/Dequeue.java)
   * [Implement a queue using stack](/src/queue/QueuesUsingStack.java)
   </br>


   
* <b>LinkedList</b></br>
   * [Reverse a Linked List](/src/linkedlist/ReverseLinkedList.java)
   * [Remove duplicates from a Linked List](/src/linkedlist/RemoveDuplicates.java)
   * [Delete Node of a given key from a Linked List](/src/linkedlist/DeleteNodeWithKey.java)   
   * [Find the Middle Node of a Linked List](/src/linkedlist/FindMiddleNode.java)
   * [Find the Nth Node of a Linked List](/src/linkedlist/FindNthNode.java)
   * [Check if a Linked List is cyclic](/src/linkedlist/CheckIfContainsCycle.java)
   * [Insertion Sort of a Linked List](/src/linkedlist/InsertSortLinkedList.java)
   * [Intersection Point of Two Lists](/src/linkedlist/IntersectionPoints.java)
   * [Nth from last node](/src/linkedlist/NthFromLastNode.java)
   * [Swap Nth Node with Head](/src/linkedlist/SwapNthNodeWithHead.java)
   * [Merge Two Sorted Linked Lists](/src/linkedlist/MergeLinkedList.java)
   * [Sorting LinkedList using merge sort](/src/linkedlist/MergeSortList.java)
   * [Reverse nodes at even indices](/src/linkedlist/ReverseEvenNodes.java)
   * [Rotate linked list by n](/src/linkedlist/RotateLinkedList.java)
   * [Reverse every 'k' elements in a linked list](/src/linkedlist/ReversekElements.java)
   * [Add the head pointers of two linked lists](/src/linkedlist/AddTwoIntegers.java)   
   </br>   
   
   
   
* <b>Stacks</b></br>
   * [Evaluate an expression](/src/stacks/EvaluationExpression.java)
   * [Implement a stack using queues](/src/stacks/StacksUsingQueues.java)
   * [Check if paranthesis are equal](/src/stacks/EqualDelimiters.java)
   * [Tower of Hanoi](/src/stacks/TowerOfHanoi.java)
   * [ReverseAStack](/src/stacks/ReverseStack.java)
   </br>
   
   

* <b>Back Tracking</b></br>
   * [Solve Boggle](/src/backtracks/Boggle.java)
   * [Print paranthesis combination for a given value](/src/backtracks/Parenthesis.java)
   * [Solve N queen problem](/src/backtracks/NQueenProblem.java)
   * [find all the subsets of the given array that sum up to the number K](/src/backtracks/KSumSubsets.java)
   </br>
   
   
* <b>Graphs</b></br>
   * [Clone a Directed Graph](/src/graphs/CloneDirectedGraph.java)
   * [Minimum Spanning Tree](/src/graphs/MinimumSpanningTree.java)
   * [Form circular chain by given list of words](/src/graphs/WordChaining.java)   
   </br> 
   
   
* <b>Trees</b></br>
   * [Implements an InOrder Iterator on a Binary Tree](/src/trees/BinaryTreeIterator.java)
   * [Convert a binary tree to a doubly linked list](/src/trees/BinaryTreeToLinkedList.java)
   * [Connect a sibling pointer of a binary tree to next node in the same level](/src/trees/ConnectAllSiblings.java)
   * [Given a binary tree, connect its siblings at each level](/src/trees/ConnectSiblings.java)
   * [Delete any subtrees whose nodes sum up to zero](/src/trees/DeleteZeroSumSubTrees.java)
   * [Given roots of two binary trees, determine if these trees are identical](/src/trees/IdenticalBinaryTree.java)
   * [Find the Inorder successor of a node in binary Search Tree](/src/trees/InOrderSuccessor.java)
   * [Algorithm to traverse the tree inorder](/src/trees/InOrderTraversal.java)
   * [Check if a given tree is a binary search tree](/src/trees/IsBST.java)
   * [Display node values at each level in a binary tree](/src/trees/LevelOrderTraversal.java)
   * [Swap the 'left' and 'right' children for each node in a binary tree](/src/trees/MirrorBinaryTreeNodes.java)
   * [Find nth highest node in a Binary Search Tree](/src/trees/NthHighestBST.java)
   * [Print nodes forming the boundary of a Binary Search Tree](/src/trees/PrintTreePerimeter.java)
   * [Serialize binary tree to a file and then deserialize back to tree](/src/trees/SerializeBinaryTree.java)   
   </br>


* <b>Strings</b></br>
   * [Reverse String](/src/strings/ReverseString.java)
   * [Palindrone String](/src/strings/PalindroneStrings.java)
   * [Regular Expression](/src/strings/RegularExpression.java)
   * [Remove Duplicates](/src/strings/RemoveDuplicates.java)
   * [Remove White Spaces](/src/strings/RemoveWhiteSpaces.java)
   * [Remove a String](/src/strings/ReverseString.java)
   * [String Segmentation](/src/strings/StringSegmentation.java)
   * [Find next highest permutation of a given string](/src/strings/NextHighestPermutation.java)
   * [Check if two strings are anagrams](/src/strings/CheckIfAnagram.java)   
   </br>
   
   
* <b>Integers</b></br>
   * [Reverse Integer](/src/math/ReverseInteger.java)
   * [Find sum of digits of an integer](/src/math/FindSumOfInteger.java)   
   * [Find Next highest Number from a Integer](/src/math/NextHighestNumber.java)
   * [Check if it is an Armstrong number](/src/math/CheckIfArmstrongNumber.java)
   * [Find the factorial of a number](/src/math/FindFactorial.java)
   * [Print all prime numbers upto the given number](/src/math/PrintPrimeNumbers.java)
   * [Find all the prime factors of a given integer](/src/math/FindPrimeFactors.java)
   * [Check if a given number is binary](/src/math/CheckIfBinary.java)
   * [Find kth permutation](/src/math/KthPermutation.java)
   * [Integer Division](/src/math/IntegerDivision.java)
   * [Find Pythagorean Triplets](/src/math/FindPythagoreanTriplets.java)
   * [Print all possible sum combinations using positive integers](/src/math/SumCombinations.java)
   * [Find Missing Number](/src/math/FindMissingNumber.java)   
   * [Find all subsets of a given set of integers](/src/math/IntegerSubsets.java)
   * [Given an input string, determine if it makes a valid number](/src/math/NumberValidity.java)
   * [Calculate 'x' raised to the power 'n'](/src/math/PowerOfNumber.java)
   * [Calculate square root of a number](/src/math/CalculateRoot.java)
   * [Minimum Number of Platforms Required for a Railway/Bus Station](/src/math/MinimumPlatforms.java)   
   </br>   
   
   
* <b>Miscellaneous</b></br>
   * [Find three integers in the array with sum equal to the given value](/src/misc/SumOfThreeValues.java)
   * [Find position of a given key in 2D matrix](/src/misc/SearchMatrix.java)
   * [Determine the host byte order of any system](/src/misc/HostByteOrder.java)
   * [Find the point that requires the least total distance covered by all the ​people to meet at that point](/src/misc/ClosestMeetingPoint.java)
   * [Given a two dimensional array, if any element in it is zero make its whole row and column zero](/src/misc/SumOfThreeValues.java)
   </br>   
  
  
### Data Structure Coding Programs
* <b>Sorting</b></br>
   * [BubbleSort](/src/sort/BubbleSort.java)
   * [InsertionSort](/src/sort/InsertionSort.java)
   * [SelectionSort](/src/sort/SelectionSort.java)
   * [QuickSort](/src/sort/QuickSort.java)
   * [MergeSort](/src/sort/MergeSort.java)
     * <b>Question: Why is quicksort preferred over merge sort for sorting arrays?</b></br>
         * Quicksort does not require any extra storage whereas merge sort requires O(n) space allocation. Allocating/de-allocating memory space can increase the run time.</br>
     * <b>Question: Why is merge sort preferred over quicksort for sorting linked lists?</b></br>
         * There is a difference in linked lists due to memory allocation. In linked lists we can insert items in the middle in O(n) space and time. There is no extra memory allocation required.     
   </br>
   
   
* <b>Searching</b></br>
   * [Binary Search](/src/search/BinarySearch.java)
   * [Rotated Binary Search](/src/search/RotatedBinarySearch.java)
   * [Ternary Search](/src/search/TernarySearch.java)  
     * <b>Question: Why is binary search preferred over ternary search?</b></br>
         * When dividing an array by k ( 2(binary) or 3(ternary)), it reduces the array size to 1/k. But it increases the no of comparisons by k.
   </br>
   
   
* <b>Runtime Complexity Table:</b></br>
   <a href="https://github.com/anitaa1990/Android-Cheat-sheet/blob/master/media/4.png" target="_blank"><img src="https://github.com/anitaa1990/Android-Cheat-sheet/blob/master/media/4.png"></a></br>
   
   



   1) <a href="https://www.geeksforgeeks.org/find-minimum-element-in-a-sorted-and-rotated-array/">https://www.geeksforgeeks.org/find-minimum-element-in-a-sorted-and-rotated-array/</a>

2) <a href="https://www.geeksforgeeks.org/largest-subarray-with-equal-number-of-0s-and-1s/">https://www.geeksforgeeks.org/largest-subarray-with-equal-number-of-0s-and-1s//</a>

3) <a href="https://www.geeksforgeeks.org/find-triplets-array-whose-sum-equal-zero/">https://www.geeksforgeeks.org/find-triplets-array-whose-sum-equal-zero/</a>

4) <a href="https://www.geeksforgeeks.org/level-order-traversal-in-spiral-form/">https://www.geeksforgeeks.org/level-order-traversal-in-spiral-form/</a>

5) <a href="https://www.geeksforgeeks.org/construct-tree-from-given-inorder-and-preorder-traversal/">https://www.geeksforgeeks.org/construct-tree-from-given-inorder-and-preorder-traversal/</a>

6) <a href="https://www.geeksforgeeks.org/write-an-efficient-c-function-to-convert-a-tree-into-its-mirror-tree/">https://www.geeksforgeeks.org/write-an-efficient-c-function-to-convert-a-tree-into-its-mirror-tree/</a>

7) <a href="https://www.geeksforgeeks.org/maximum-sum-such-that-no-two-elements-are-adjacent/">https://www.geeksforgeeks.org/maximum-sum-such-that-no-two-elements-are-adjacent/</a>

8) [https://www.geeksforgeeks.org/longest-common-subarray-in-the-given-two-arrays/?ref=leftbar-rightbar](https://www.geeksforgeeks.org/longest-common-subarray-in-the-given-two-arrays/?ref=leftbar-rightbar)

9) [https://www.geeksforgeeks.org/maximum-sum-path-across-two-arrays/](https://www.geeksforgeeks.org/maximum-sum-path-across-two-arrays/)

10) [https://www.geeksforgeeks.org/merge-two-sorted-arrays-o1-extra-space/](https://www.geeksforgeeks.org/merge-two-sorted-arrays-o1-extra-space/)

11) [https://www.geeksforgeeks.org/segregate-0s-and-1s-in-an-array-by-traversing-array-once/](https://www.geeksforgeeks.org/segregate-0s-and-1s-in-an-array-by-traversing-array-once/)

12) [https://www.geeksforgeeks.org/construction-of-longest-monotonically-increasing-subsequence-n-log-n/](https://www.geeksforgeeks.org/construction-of-longest-monotonically-increasing-subsequence-n-log-n/)

13) [https://www.geeksforgeeks.org/kth-smallestlargest-element-unsorted-array/](https://www.geeksforgeeks.org/kth-smallestlargest-element-unsorted-array/)

14) [https://www.geeksforgeeks.org/find-zeroes-to-be-flipped-so-that-number-of-consecutive-1s-is-maximized/](https://www.geeksforgeeks.org/find-zeroes-to-be-flipped-so-that-number-of-consecutive-1s-is-maximized/)

15) [https://www.geeksforgeeks.org/reverse-a-doubly-linked-list/](https://www.geeksforgeeks.org/reverse-a-doubly-linked-list/)

16) [https://www.geeksforgeeks.org/longest-common-increasing-subsequence-lcs-lis/](https://www.geeksforgeeks.org/longest-common-increasing-subsequence-lcs-lis/)

17) [https://www.geeksforgeeks.org/fix-two-swapped-nodes-of-bst/](https://www.geeksforgeeks.org/fix-two-swapped-nodes-of-bst/)

18) [https://www.geeksforgeeks.org/backttracking-set-2-rat-in-a-maze/](https://www.geeksforgeeks.org/backttracking-set-2-rat-in-a-maze/)

19) [https://www.geeksforgeeks.org/detect-and-remove-loop-in-a-linked-list/](https://www.geeksforgeeks.org/detect-and-remove-loop-in-a-linked-list/)

20) [https://www.geeksforgeeks.org/find-minimum-element-in-a-sorted-and-rotated-array/](https://www.geeksforgeeks.org/find-minimum-element-in-a-sorted-and-rotated-array/)

21) [https://www.geeksforgeeks.org/maximum-product-subarray/](https://www.geeksforgeeks.org/maximum-product-subarray/)

22) [https://www.geeksforgeeks.org/merge-k-sorted-arrays/](https://www.geeksforgeeks.org/merge-k-sorted-arrays/)

23) [https://www.geeksforgeeks.org/sort-an-array-of-0s-1s-and-2s/](https://www.geeksforgeeks.org/sort-an-array-of-0s-1s-and-2s/)

24) [https://www.geeksforgeeks.org/a-product-array-puzzle/](https://www.geeksforgeeks.org/a-product-array-puzzle/)

25) [https://www.geeksforgeeks.org/count-frequencies-elements-array-o1-extra-space-time/](https://www.geeksforgeeks.org/count-frequencies-elements-array-o1-extra-space-time/)

26) [https://www.geeksforgeeks.org/median-of-two-sorted-arrays-of-different-sizes/](https://www.geeksforgeeks.org/median-of-two-sorted-arrays-of-different-sizes/)

27) [https://www.geeksforgeeks.org/find-maximum-path-sum-in-a-binary-tree/](https://www.geeksforgeeks.org/find-maximum-path-sum-in-a-binary-tree/)

28) [https://www.geeksforgeeks.org/lowest-common-ancestor-in-a-binary-search-tree/](https://www.geeksforgeeks.org/lowest-common-ancestor-in-a-binary-search-tree/)

29) [https://www.geeksforgeeks.org/lowest-common-ancestor-binary-tree-set-1](https://www.geeksforgeeks.org/lowest-common-ancestor-binary-tree-set-1)

30) [https://www.geeksforgeeks.org/sorted-linked-list-to-balanced-bst/](https://www.geeksforgeeks.org/sorted-linked-list-to-balanced-bst/)

31) [https://www.geeksforgeeks.org/given-an-array-a-and-a-number-x-check-for-pair-in-a-with-sum-as-x/](https://www.geeksforgeeks.org/given-an-array-a-and-a-number-x-check-for-pair-in-a-with-sum-as-x/)

32) [https://www.educative.io/edpresso/how-to-find-the-most-frequent-word-in-an-array-of-strings](https://www.educative.io/edpresso/how-to-find-the-most-frequent-word-in-an-array-of-strings)

33) Continuation Question to `32`, What is the time complexity of your solution and how can you improve it?

34) What is the time complexity of mergeSort, quickSort and Binary search?

35) What is the time complexity for removing an element from LinkedList?



# Scrum vs Kanban

## Scrum 

Scrum is an agile process that helps to deliver the business value in the shortest time. It rapidly and repeatedly inspects actual working software. It emphasizes on teamwork and iterative progress of the software. Its goal is to deliver new software every 1-4 weeks.

## Kanban

Kanban is a visual system for managing work. It visualizes both the process and the actual work passing through that process. The main objective of implementing Kanban is to identify potential bottlenecks in the process and fix them. Kanban goal is that work flow should proceed smoothly at an optimal speed.

## Conclusion

| Scrum | Kanban |
|---|---|
| Scrum stresses on planning. It starts with sprint planning and ends up with sprint retrospective.  | Kanban is open to making changes on the go. It means there is less rigidity and things can change frequently. |
| It recommends collection of time measurements made during sprints  | Kanban recommends graphs to get an overview of team's progress over time.  |
| Estimation has a very important role in Scrum  | No mandatory requirements for estimation.  |
| Every individual has their role and responsibilities. | No set roles so flexibility in term of individual responsibilities. |
| It is not possible to add items to ongoing iterations. | New items can easily add if the additional capacity is available. |
| Measures production using velocity through sprints.  | Measures production using cycle time or the exact time it takes to complete one full piece of a project. |



# Concurrency vs Parallelism

**Concurrency** means that an application is making progress on more than one task at the same time (concurrently). Concurrency is a approach that is used for decreasing the response time of the system by using the single processing unit. Concurrency is that the illusion of parallelism, however in actual the chunks of a task aren’t parallelly processed, but inside the application, there are more than one task is being processed at a time. It does not completely finish one task before it begins the next.

Concurrency is achieved through the interleaving operation of processes on the central processing unit(CPU) or in other words by the context switching, that’s rationale it’s like parallel processing. It increases the amount of work finished at a time.

![](assets/concurrency.png "Concurrency")

**Parallelism** Parallelism means that an application splits its tasks up into smaller subtasks which can be processed in parallel, for instance on multiple CPUs at the exact same time. It is used for increasing the throughput and computational speed of the system by using the multiple processors. It is the technique that do lot of things simultaneously.

Parallelism leads to overlapping of central processing unit and input-output tasks in one process with the central processing unit and input-output tasks of another process. Whereas in concurrency the speed is increased by overlapping the input-output activities of one process with CPU process of another process.

![](assets/parallelism.png "Concurrency")

To get more idea about the distinction between concurrency and parallelism, consider the following points −
- *Concurrent but not parallel*: An application can be concurrent but not parallel means that it processes more than one task at the same time but the tasks are not broken down into subtasks.
- *Parallel but not concurrent*: An application can be parallel but not concurrent means that it only works on one task at a time and the tasks broken down into subtasks can be processed in parallel.
- *Neither parallel nor concurrent*: An application can be neither parallel nor concurrent. This means that it works on only one task at a time and the task is never broken into subtasks.
- *Both parallel and concurrent*: An application can be both parallel and concurrent means that it both works on multiple tasks at a time and the task is broken into subtasks for executing them in parallel.

| Concurrency | Parallelism |
|---|---|
| Is the task of running and managing the multiple computations at the same time  | Is the task of running multiple computations simultaneously  |
| Achieved through the interleaving operation of processes on the central processing unit(CPU) or in other words by the context switching  | Achieved by through multiple central processing units(CPUs)  |
| Increases the amount of work finished at a time  | Improves the throughput and computational speed of the system  |
| Deals lot of things simultaneously  | Do lot of things simultaneously |
| Non-deterministic control flow approach  | Deterministic control flow approach  |



# git pull vs git fetch

`git-fetch` - Download objects and refs from another repository. Fetch branches and/or tags (collectively, "refs") from one or more other repositories, along with the objects necessary to complete their histories.

By default, any tag that points into the histories being fetched is also fetched; the effect is to fetch tags that point at branches that you are interested in. `git fetch` can fetch from either a single named repository or URL, or from several repositories at once. When no remote is specified, by default the `origin` remote will be used, unless there’s an upstream branch configured for the current branch.

`git-pull` - Fetch from and integrate with another repository or a local branch. Incorporates changes from a remote repository into the current branch. In its default mode, `git pull` is shorthand for `git fetch` followed by `git merge FETCH_HEAD`.

More precisely, `git pull` runs `git fetch` with the given parameters and calls `git merge` to merge the retrieved branch heads into the current branch. With `--rebase`, it runs `git rebase` instead of `git merge`.



  **git merge**
  *`git merge`* simply remembers the history as it happened. It takes the two current versions, merge them together based on their common ancestor, fix any conflicts, and then record the history exactly as it happened.
  
  **git rebase**
 *`git rebase`* attempts to make the history look as simple as possible. It picks one of the two sides to be the base  and all the changes on the other side are flattened into a linear series of changes happening afterwards.
 git rebase  | git merge |
| ------------- | ------------- |
| 1.   **git rebase**  gets all unique commits from both branches and applies them one by one  | 1. **git merge**  apply all unique commits from branch A into branch B in one commit with final result.  |
| 2.  **git rebase** rewrites commit history but doesn’t create extra commit for merging  | 2.  **git merge** doesn’t rewrite commit history, just adds one new commit.  |


# OOP Principles

Some sources claim that there are 3 main principles of object-oriented programming - **Inheritance**, **Polymorphism** and **Encapsulation**. Other sources added one more  principle - **Abstraction**. In this answer we will consider all these principles. From my point of view, **Abstraction** is not a principle of object-oriented programming.

## Inheritance
Inheritance is a mechanism that lets you describe a new class based on an existing (parent or super) class. In doing so, the new class borrows the properties and functionality of the parent class. Inheritance supports the concept of hierarchical classification, this allows classes to be arranged in a hierarchy that represents "is-a-type-of" relationships.

Important terminology:
- *Super Class*: The class whose features are inherited is known as superclass(or a base class or a parent class).
- *Sub Class*: The class that inherits the other class is known as subclass(or a derived class, extended class, or child class). The subclass can add its own fields and methods in addition to the superclass fields and methods.
- *Reusability*: Inheritance supports the concept of “reusability”, i.e. when we want to create a new class and there is already a class that includes some of the code that we want, we can derive our new class from the existing class. By doing this, we are reusing the fields and methods of the existing class.

Subclasses can override the methods defined by superclasses. Multiple inheritance is allowed in some languages, though this can make resolving overrides complicated. Some languages have special support for mixins, though in any language with multiple inheritance, a mixin is simply a class that does not represent an is-a-type-of relationship.

A real-world example of inheritance is a mother and child. The child may inherit attributes such as height, Voice patters, color. The mother can reproduce other children with the same attributes as well. 

In summary, **Inheritance** is concerned with the relationship between classes and method, which is like a parent and a child. A child can be born with some of the attributes of the parents. Inheritance ensures reusability of codes just the way multiple children can inherit the attributes of their parents.

## Polymorphism
Polymorphism is the ability to work with several types as if they were the same type. Moreover, the objects' behavior will be different depending on their type. 

An excellent example of Polymorphism in Object-oriented programing is a cursor behavior. A cursor may take different forms like an arrow, a line, cross, or other shapes depending on the behavior of the user or the program mode. With polymorphism, a method or subclass can define its behaviors and attributes while retaining some of the functionality of its parent class. This means you can have a class that displays date and time, and then you can create a method to inherit the class but should display a welcome message alongside the date and time. The goals of Polymorphism in Object-oriented programming is to enforce simplicity, making codes more extendable and easily maintaining applications.

Inheritance allows you to create class hierarchies, where a base class gives its behavior and attributes to a derived class. You are then free to modify or extend its functionality. Polymorphism ensures that the proper method will be executed based on the calling object’s type. 

Polymorphism could be static and dynamic both. Method Overloading is static polymorphism while, Method overriding is dynamic polymorphism.
- Overloading in simple words means more than one method having the same method name that behaves differently based on the arguments passed while calling the method. This called static because, which method to be invoked is decided at the time of compilation
- Overriding means a derived class is implementing a method of its super class. The call to overriden method is resolved at runtime, thus called runtime polymorphism

## Encapsulation

Encapsulation is defined as the wrapping up of data under a single unit. It is the mechanism that binds together code and the data it manipulates. Other way to think about encapsulation is, it is a protective shield that prevents the data from being accessed by the code outside this shield. Attributes and behaviors are defined by code inside the class template. Then, when an object is instantiated from the class, the data and methods are encapsulated in that object.

- Technically in encapsulation, the variables or data of a class is hidden from any other class and can be accessed only through any member function of own class in which they are declared.
- As in encapsulation, the data in a class is hidden from other classes using the data hiding concept which is achieved by making the members or methods of class as private and the class is exposed to the end user or the world without providing any details behind implementation using the abstraction concept, so it is also known as combination of data-hiding and abstraction.
- Encapsulation can be achieved by: Declaring all the variables in the class as private and writing public methods in the class to set and get the values of variables.

Encapsulation adds security. Attributes and methods can be set to private, so they can’t be accessed outside the class. To get information about data in an object, public methods & properties are used to access or update data. This adds a layer of security, where the developer chooses what data can be seen on an object by exposing that data through public methods in the class definition.

Benefits of encapsulation:
- Adds security
- Protects developers from common mistakes
- Protects IP
- Supportable
- Developer can change internal code in the class without alerting users
- Hides complexity

## Abstraction
Abstraction means that the user interacts with only selected attributes and methods of an object. Abstraction uses simplified, high level tools, to access a complex object.

Data Abstraction may also be defined as the process of identifying only the required characteristics of an object ignoring the irrelevant details.The properties and behaviors of an object differentiate it from other objects of similar type and also help in classifying/grouping the objects.

Consider a real-life example of a man driving a car. The man only knows that pressing the accelerators will increase the speed of car or applying brakes will stop the car but he does not know about how on pressing the accelerator the speed is actually increasing, he does not know about the inner mechanism of the car or the implementation of accelerator, brakes etc in the car. This is what abstraction is.

Benefits of abstraction:
- Simple, high level user interfaces
- Complex code is hidden
- Security. Only chosen parts of object are accessible
- Easier software maintenance. Code updates rarely change abstraction



# SOLID Principles

SOLID is a mnemonic acronym for five design principles intended to make software designs more understandable, flexible and maintainable. The theory of SOLID principles was introduced by Martin in his 2000 paper Design Principles and Design Patterns, although the SOLID acronym was introduced later by Michael Feathers.

## Concepts
- **Single-responsibility principle** - A class should only have a single responsibility, that is, only changes to one part of the software's specification should be able to affect the specification of the class.
- **Open–closed principle** - Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.
- **Liskov substitution principle** - Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.
- **Interface segregation principle** - Many client-specific interfaces are better than one general-purpose interface.
- **Dependency inversion principle** - Depend on abstractions, not on concretions.





# GET vs POST

**GET** - It requests the data from a specified resource

Example:
```
https://api.themoviedb.org/3/movie/1/account_states
```

Feature: 
- Remains in the browser history
- Can be bookmarked
- Can be cached
- Have length restrictions
- Should never be used when dealing with sensitive data
- Should only be used for retrieving the data

**POST** - It submits the processed data to a specified resource
Example: 
```
https://api.themoviedb.org/3/movie/1/rating

RequestBody
{
  "value": 8.5
}
```
Feature: 
- Cannot be bookmarked
- Have no restrictions on length of data
- Never cached
- Do not retain in the browser history

| GET| POST |
|---|---|
| Passes request parameter in URL  | Passes request parameter in request body  |
| Parameters remain in browser history because they are part of the URL  | Parameters are not saved in browser history  |
| Can be bookmarked  | Cannot be bookmarked  |
| URL length is restricted. A safe URL length limit is often 2048  | No restrictions for data length  |
| Only ASCII characters allowed  | No restrictions. Binary data is also allowed  |
| Mostly used for view purpose (e.g. SQL SELECT)  | Mainly use for update purpose (e.g. SQL INSERT or UPDATE)  |


# PUT vs POST

**PUT** - It is used to send data to a server to create/update a resource.

Example:
```
http://www.google.com/users/234

PUT /new.html HTTP/1.1
Host: example.com
Content-type: text/html
Content-length: 20

<p>New File</p>
```

Feature: 
- Cannot be bookmarked
- Should only be used for update the data
- Never cached
- Do not retain in the browser history

**POST** - It submits the processed data to a specified resource
Example: 
```
https://api.themoviedb.org/3/movie/1/rating

RequestBody
{
  "value": 8.5
}
```
Feature: 
- Cannot be bookmarked
- Have no restrictions on length of data
- Never cached
- Do not retain in the browser history

| PUT| POST |
|---|---|
| Is idempotent | Is not idempotent  |
| If you send the same request multiple times, the result will remain the same  | If you send the same POST request more than one time, you will receive different results  |
| Mostly used for UPDATE query | Mainly use for create query |



# HTTP vs HTTPS

**HTTP (Hypertext Transfer Protocol)** - is an application protocol for distributed, collaborative, hypermedia information systems. **HTTP** is the foundation of data communication for the World Wide Web, where hypertext documents include hyperlinks to other resources that the user can easily access, for example by a mouse click or by tapping the screen in a web browser. **HTTP** offers set of rules and standards which govern how any information can be transmitted on the World Wide Web. **HTTP** provides standard rules for web browsers & servers to communicate.

**HTTP** is an application layer network protocol which is built on top of TCP. **HTTP** uses Hypertext structured text which establishes the logical link between nodes containing text. It is also known as "stateless protocol" as each command is executed separately, without using reference of previous run command.

**HTTPS (Hypertext Transfer Protocol Secure)** - is an extension of the **HTTP** . It is used for secure communication over a computer network, and is widely used on the Internet. In **HTTPS**, the communication protocol is encrypted using Transport Layer Security (TLS) or, formerly, its predecessor, Secure Sockets Layer (SSL).

The principal motivations for **HTTPS** are authentication of the accessed website, protection of the privacy and integrity of the exchanged data while in transit. It protects against man-in-the-middle attacks. The bidirectional encryption of communications between a client and server protects against eavesdropping and tampering of the communication. In practice, this provides a reasonable assurance that one is communicating without interference by attackers with the website that one intended to communicate with, as opposed to an impostor.

| HTTP | HTTPS |
|---|---|
| It uses port 80 by default  | It was use port 443 by default  |
| URLs begin with *http://*  | URLs begin with *https://*  |
| No encryption before sending data.  | Data encrypted before sending |
| Website don't need SSL | Website need SSL |
| Works at Application Layer  | Works at Transport Layer  |


# TCP vs UDP

## TCP (Transmission Control Protocol)
Is connection-oriented, and a connection between client and server is established (passive open) before data can be sent. Three-way handshake (active open), retransmission, and error-detection adds to reliability but lengthens latency. TCP employs network congestion avoidance. However, there are vulnerabilities to TCP including denial of service, connection hijacking, TCP veto, and reset attack. For network security, monitoring, and debugging, TCP traffic can be intercepted and logged with a packet sniffer.

TCP guarantees the recipient will receive the packets in order by numbering them. The recipient sends messages back to the sender saying it received the messages. If the sender does not get a correct response, it will resend the packets to ensure the recipient received them. Packets are also checked for errors. TCP is all about this reliability — packets sent with TCP are tracked so no data is lost or corrupted in transit. This is why file downloads do not become corrupted even if there are network hiccups.

## UDP (User Datagram Protocol)
Uses a simple connectionless communication model with a minimum of protocol mechanisms. UDP provides checksums for data integrity, and port numbers for addressing different functions at the source and destination of the datagram. It has no handshaking dialogues, and thus exposes the user's program to any unreliability of the underlying network, there is no guarantee of delivery, ordering, or duplicate protection.

UDP is suitable for purposes where error checking and correction are either not necessary or are performed in the application. UDP avoids the overhead of such processing in the protocol stack. Time-sensitive applications often use UDP because dropping packets is preferable to waiting for packets delayed due to retransmission, which may not be an option in a real-time system.

| TCP| UDP |
|---|---|
| Guarantees delivery of data to the destination router | Delivery of data is not guarantess |
| Provides extensive error checking mechanisms. It is because it provides flow control and acknowledgment of data | Has only the basic error checking mechanism using checksums |
| Sequencing of data, packets arrive in-order at the receiver | There is no sequencing of data. If ordering is required, it has to be managed by the application layer |
| Retransmission of lost packets is possible | There is no retransmission of lost packets |
| Has a (20-80) bytes variable length header | Has a 8 bytes fixed length header |
| Doesn’t supports Broadcasting | Supports Broadcasting |
| Used by HTTP, HTTPs, FTP, SMTP and Telnet | used by DNS, DHCP, TFTP, SNMP, RIP, and VoIP |
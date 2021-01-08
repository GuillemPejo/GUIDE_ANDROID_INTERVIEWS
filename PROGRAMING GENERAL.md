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
   
   
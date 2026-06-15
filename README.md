# 🧩 LeetCode Progress

> My DSA journey for technical interviews. Every problem tracked with its pattern, complexity, and the key idea behind the solution.

**69 solved**  ·  🟢 Easy 40  ·  🟡 Medium 29  ·  🔴 Hard 0  ·  Last solved: **2026-06-15**

_Source of truth: [`leetcode_tracker.xlsx`](./leetcode_tracker.xlsx). This page is auto-generated from it._

## By Topic

| Topic | Solved |
|-------|-------:|
| Array | 30 |
| Tree | 9 |
| Math | 6 |
| String | 6 |
| Linked List | 6 |
| Hash Table | 3 |
| Heap / Priority Queue | 2 |
| Two Pointers | 2 |
| Matrix | 1 |
| ArrayPrefix Sum | 1 |
| Stack | 1 |
| Depth-First Search | 1 |
| Binary Search | 1 |

## All Solved

| # | Date | Problem | Difficulty | Pattern | Key Idea |
|--:|------|---------|------------|---------|----------|
| 1 | 2026-06-15 | 1929. Concatenation of Array | Easy | Array Construction (Double Append) | Initialize an empty list ans. Loop twice; in each pass append every element of nums in order. The result is nums concatenated with itself. O(n) time, O(n) space. |
| 2 | 2026-05-08 | 374. Guess Number Higher or Lower | Easy | Binary Search (Standard) | Use binary search with L <= R. Compute mid = L + (R - L) // 2 to avoid overflow. Call guess(mid): if it returns 1, the pick is higher so move L = mid + 1; if -1, the pick is lower so move R = mid - 1; if 0, return mid. |
| 3 | 2026-05-08 | 69. Sqrt(x) | Easy | Binary Search on Answer | Binary search on the answer space [0, x]. Compute mid and compare mid² to x: if mid² > x, search lower (r = mid - 1); if mid² < x, search higher (l = mid + 1) and save mid as the current best result; if mid² == x, return mid. Return the saved result when the loop ends. |
| 4 | 2026-04-09 | 735. Asteroid Collision | Medium | Stack (Collision Simulation) | Use a stack to simulate collisions. For each asteroid, if it's negative and the stack top is positive, compare sizes: if the negative asteroid is larger (diff < 0), pop the stack and keep checking; if the positive is larger (diff > 0), discard the negative; if equal (diff == 0), pop and discard both. Use a while loop to handle chain collisions. After the loop, append the asteroid only if it survived (a != 0). |
| 5 | 2026-04-05 | 35. Search Insert Position | Easy | Binary Search (Standard) | Use binary search with L <= R. If target == nums[mid], return mid. If target > nums[mid], move L = mid + 1. Otherwise move R = mid - 1. When the loop ends without finding the target, L is the correct insertion index since it points to the first element greater than target. |
| 6 | 2026-03-27 | 110. Balanced Binary Tree | Easy | DFS (Post-order) with Early Termination | Use DFS returning [balanced, height] for each subtree. Base case: null node returns [True, 0]. At each node, a tree is balanced if both subtrees are balanced and their height difference is at most 1. Return [balanced, 1 + max(left height, right height)] to the parent. |
| 7 | 2026-03-26 | 543. Diameter of Binary Tree | Easy | DFS (Post-order) with Global Max | Use DFS to compute the height of each subtree. At each node, the diameter passing through it is left height + right height. Track the global maximum diameter. Return 1 + max(left, right) as the height to the parent. |
| 8 | 2026-03-25 | 230. Kth Smallest Element in a BST | Medium | Iterative Inorder Traversal (Stack) | Use iterative inorder traversal with a stack. Push all left children onto the stack. Pop a node, increment counter. If counter equals k, return the node's value. Otherwise, move to the right child and repeat. |
| 9 | 2026-03-24 | 33. Search in Rotated Sorted Array | Medium | Modified Binary Search on Rotated Array | Determine which half is sorted (nums[l] <= nums[mid]). If target lies outside the sorted half's range, search the other half. Otherwise, search within the sorted half. O(log n) time. |
| 10 | 2026-03-23 | 739. Daily Temperatures | Medium | Monotonic Stack | Use a stack of [temp, index] pairs. For each temperature, while the stack is non-empty and current temp is greater than the top of stack, pop and set res[stackIndex] = currentIndex - stackIndex. Push current [temp, index] onto stack. Return res (initialized to all 0s). |
| 11 | 2026-03-22 | 680. Valid Palindrome II | Easy | Two Pointers (Greedy Check) | Use two pointers (l=0, r=len(s)-1). While they haven't met, if s[l] != s[r], create two substrings — one skipping l, one skipping r — and return true if either equals its reverse. Otherwise, move both pointers inward. Return true after the loop since all characters matched. |
| 12 | 2026-03-21 | 219. Contains Duplicate II | Easy | Sliding Window / Hash Set | Use a sliding window of size k with a hash set. Expand the window by adding nums[R]; if the window exceeds size k, remove nums[L] and advance L. If nums[R] is already in the set, return true. |
| 13 | 2026-03-21 | 344. Reverse String | Easy | Two Pointers (Swap) | Use two pointers at both ends. Swap s[l] and s[r], then move l inward and r inward until they meet. In-place reversal with O(1) space. |
| 14 | 2026-03-20 | 2. Add Two Numbers | Medium | Dummy Node / Carry Propagation | Use a dummy node and iterate both lists simultaneously, summing values with carry. Create new nodes for each digit and propagate carry until both lists and carry are exhausted. |
| 15 | 2026-03-19 | 567. Permutation in String | Medium | Sliding Window / Frequency Count | Use a fixed-size sliding window equal to s1's length. Compare character frequency maps of the window and s1; slide right and update counts incrementally. |
| 16 | 2026-03-18 | 11. Container With Most Water | Medium | Two Pointers (Greedy Shrink) | Use two pointers at both ends. Calculate area, then move the shorter pointer inward to search for a larger container. |
| 17 | 2026-03-17 | 150. Evaluate Reverse Polish Notation | Medium | Stack (LIFO) | Use a stack to process tokens left to right: push numbers, pop two operands on operators, push result back. Division truncates toward zero. |
| 18 | 2026-03-16 | 98. Validate Binary Search Tree | Medium | DFS with Valid Range | Use DFS with a valid range (left, right) for each node. Start with (-inf, inf). For each node, check if its value is within the range. Recurse left with updated right bound (node.val) and right with updated left bound (node.val). |
| 19 | 2026-03-15 | 1046. Last Stone Weight | Easy | Max-Heap Simulation | Negate values to simulate a max-heap with Python's min-heap. Repeatedly pop two largest, push their difference if nonzero. |
| 20 | 2026-02-7 | 102. Binary Tree Level Order Traversal | Medium | Level-order BFS using queue | Use a queue and process nodes level by level by iterating len(queue) each round to collect values per level. |
| 21 | 2026-02-6 | 100. Same Tree | Easy | Recursive DFS with simultaneous traversal | Recursively compare both nodes’ values and ensure left and right subtrees are identical at every step. |
| 22 | 2026-02-6 | 572. Subtree of Another Tree | Easy | DFS traversal / same-tree comparison | Traverse each node of the main tree and recursively check structural and value equality with the subtree root. |
| 23 | 2026-02-6 | 235. Lowest Common Ancestor  of a Binary Search Tree | Medium | Iterative BST traversal using value bounds | Move left or right based on p and q relative to current node and return the first node where their paths diverge or match. |
| 24 | 2026-02-5 | 104. Maximum Depth of Binary Tree | Easy | DFS recursion, BFS, DFS iterative | 1. Recursively compute depth as 1 plus the maximum depth of left and right subtrees. 2. Traverse the tree level by level using a queue and increment depth after each level. 3. Use a stack storing nodes with their depths and track the maximum depth reached. |
| 25 | 2026-02-4 | 143. Reorder List | Medium | Fast–slow pointer / reverse second half / merge | Split the list in half, reverse the second, then interleave nodes from first and second. |
| 26 | 2026-02-4 | 19. Remove Nth Node From End of List | Medium | Two pointers / dummy node | Use a dummy node and two pointers with n-step gap to remove the target node. |
| 27 | 2026-02-4 | 226. Invert Binary Tree | Easy | DFS recursion (preorder) | Recursively swap left and right children at each node. |
| 28 | 2026-02-3 | 141. Linked List Cycle | Easy | Floyd’s Tortoise and Hare (Two Pointers) | Use slow and fast pointers moving at different speeds to detect a cycle when  they meet. |
| 29 | 2026-02-2 | 3. Longest Substring Without Repeating Characters | Medium | Two Pointers / Hash Set | Use a sliding window that shrinks on duplicates to keep all characters unique. |
| 30 | 2026-02-2 | 424. Longest Repeating Character Replacement | Medium | Two Pointers / Frequency HashMap | Shrink the window when window size minus max frequency exceeds k. |
| 31 | 2026-02-11 | 703. Kth Largest Element in a Stream | Easy | Min-Heap of Size K | Maintain a min-heap of size k so the root always represents the kth largest element. |
| 32 | 2026-02-1 | 153. Find Minimum in Rotated Sorted Array | Medium | Modified binary search on rotated array | Compare mid with boundaries to discard the sorted half and keep the minimum candidate |
| 33 | 2026-02-1 | 121. Best Time to Buy and Sell Stock | Easy | Two pointers / sliding window | Track minimum buy price so far and update maximum profit as prices increase |
| 34 | 2026-01-31 | 875. Koko Eating Bananas | Medium | Binary Search on Answer | Binary search the minimum eating speed using the monotonic relationship |
| 35 | 2026-01-30 | 74. Search a 2D Matrix | Medium | Two-Phase Binary Search (Iterative) | Search row range first; then search within row using L ≤ R |
| 36 | 2026-01-29 | 704. Binary Search | Easy | Two-Pointer (Iterative) | Maintain L and R pointers; check mid while L <= R |
| 37 | 2026-01-27 | 155. Min Stack | Medium | Two Stacks / Pair Tracking | Maintain a parallel stack that tracks the minimum value seen so far |
| 38 | 2026-01-23 | 20. Valid Parentheses | Easy | Stack (LIFO) | Match each closing bracket with the most recent opening one using a stack. |
| 39 | 2026-01-22 | 238. Product of Array Except Self | Medium | Prefix & Suffix Product (Two-pass traversal) | Compute prefix products and suffix products separately to get each index’s result . |
| 40 | 2026-01-21 | 347. Top K Frequent Elements | Medium | Bucket Sort (Frequency Bucket) / Hash Map | Groups elements by frequency and retrieves the top K from highest frequency. |
| 41 | 2026-01-17 | 15. 3Sum | Medium | Two Pointers | Fix one value and use two pointers to find zero-sum pairs. |
| 42 | 2026-01-15 | 169. Majority Element | Easy | Boyer-Moore Voting | Cancel elements to identify the majority candidate. |
| 43 | 2026-01-15 | 229. Majority Element II | Medium | Boyer-Moore Extended | Track up to two candidates occurring more than n/3 times. |
| 44 | 2026-01-15 | 242. Valid Anagram | Easy | Frequency Count | Compare character frequency maps of both strings. |
| 45 | 2026-01-15 | 167. Two Sum II - Input Array Is Sorted | Medium | Two Pointers | Adjust pointers based on sum comparison in sorted array. |
| 46 | 2025-12-17 | 49. Group Anagrams | Medium | Sorted Key Mapping | Group strings using sorted characters as keys. |
| 47 | 2025-12-17 | 125. Valid Palindrome | Easy | Two Pointers | Compare characters from both ends while skipping invalid ones. |
| 48 | 2025-12-16 | 1. Two Sum | Easy | Hash Map | Store seen values and check for required complements. |
| 49 | 2025-11-11 | 217. Contains Duplicate | Easy | Hash Set | Use a set to detect if any value appears more than once. |
| 50 | 2025-11-09 | 581. Shortest Unsorted Continuous Subarray | Medium | Boundary Detection | Identify boundaries where array order is violated. |
| 51 | 2025-11-09 | 657. Robot Return to Origin | Easy | Direction Counting | Track movements and check if the net position is origin. |
| 52 | 2025-11-02 | 1572. Matrix Diagonal Sum | Easy | Index Traversal | Sum both diagonals while avoiding double counting the center. |
| 53 | 2025-09-16 | 206. Reverse Linked List | Easy | Iterative Reversal | Reverse the linked list by reassigning pointers iteratively. |
| 54 | 2025-09-05 | 75. Sort Colors | Medium | Dutch National Flag | Partition array into three color regions using pointers. |
| 55 | 2025-09-05 | 21. Merge Two Sorted Lists | Easy | Two Pointers | Merge nodes by comparing values from both lists. |
| 56 | 2025-09-01 | 1768. Merge Strings Alternately | Easy | Two Pointers | Alternate characters from both strings sequentially. |
| 57 | 2025-08-29 | 54. Spiral Matrix | Medium | Boundary Traversal | Traverse the matrix layer by layer while shrinking boundaries. |
| 58 | 2025-08-29 | 1491. Average Salary Excluding the Minimum and Maximum Salary | Easy | Min-Max Exclusion | Exclude the minimum and maximum values before averaging. |
| 59 | 2025-08-29 | 1502. Can Make Arithmetic Progression From Sequence | Easy | Difference Check | Sort the array and verify equal adjacent differences. |
| 60 | 2025-08-28 | 1523. Count Odd Numbers in an Interval Range | Easy | Arithmetic Count | Use arithmetic to count odd numbers without looping. |
| 61 | 2025-08-28 | 896. Monotonic Array | Easy | Trend Checking | Check if the array is monotonic in one direction. |
| 62 | 2025-08-27 | 709. To Lower Case | Easy | Character Transformation | Convert each character to lowercase using ASCII rules. |
| 63 | 2025-07-30 | 2469. Convert the Temperature | Easy | Direct Formula | Apply the temperature conversion formulas directly. |
| 64 | 2025-07-30 | 2119. A Number After a Double Reversal | Easy | Digit Reversal | A double reversal changes nothing unless trailing zeros exist. |
| 65 | 2025-07-30 | 1281. Subtract the Product and Sum of Digits of an Integer | Easy | Digit Traversal | Traverse digits to compute product and sum. |
| 66 | 2025-07-30 | 1431. Kids With the Greatest Number of Candies | Easy | Max Comparison | Check if candies plus extra reaches the maximum value. |
| 67 | 2025-07-30 | 2180. Count Integers With Even Digit Sum | Easy | Digit Sum | Count numbers whose digit sum is even. |
| 68 | 2025-07-30 | 3522. Calculate Score After Performing Instruction | Medium | Prefix Simulation | Simulate instructions while updating the score incrementally. |
| 69 | 2025-07-30 | 66. Plus One | Easy | Carry Propagation | Process digits from the end while handling carry. |

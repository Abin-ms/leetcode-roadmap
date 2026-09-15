# leetcode-roadmap
# The Complete DSA Mastery Roadmap (Java Edition)
 
A structured course — not a problem dump. ~150 hand-picked problems, ordered so every problem teaches you something the next problem needs.
 
---
 
## 0. How To Use This Roadmap
 
### The Problem-Solving Method (follow this for EVERY problem)
1. Understand the problem — restate it in your own words
2. Write 2–3 examples by hand (including an edge case)
3. Identify exact input/output types and constraints
4. Think of a brute-force approach first
5. Work out brute-force time/space complexity
6. Look for a pattern (see the Cheat Sheet at the end)
7. Design the optimized approach
8. Code it in Java
9. Test edge cases (empty input, single element, duplicates, negatives, overflow)
10. State time complexity
11. State space complexity
12. Write 2–3 lines: "What I learned from this problem"
**Never look at a solution before finishing steps 1–9 yourself**, unless you're stuck for 25–30+ minutes on an Easy or 40+ minutes on a Medium — then use the Hint System below.
 
### Hint System (ask for these one at a time)
- **Hint 1** — a tiny conceptual nudge ("think about what changes when the window grows")
- **Hint 2** — names the pattern ("this is a sliding window problem")
- **Hint 3** — the approach in plain English, no code
- **Hint 4** — pseudocode
- **Solution** — only given if you explicitly ask for it
### Difficulty Progression Scale
Instead of Easy→Easy→Medium→Hard, problems move through:
**Easy → Easy+ → Medium− → Medium → Medium+ → Hard**
- Easy = pure syntax/logic
- Easy+ = Easy but with a twist or an added constraint
- Medium− = Medium LC rating but a very standard/templated pattern
- Medium = genuine Medium — combines 2 ideas
- Medium+ = Medium but with an optimization trap
- Hard = multiple patterns, or a non-obvious insight
### Markers
⭐ Must Solve &nbsp;&nbsp; 🔥 Very common interview problem &nbsp;&nbsp; 🧠 Defines the pattern &nbsp;&nbsp; 💀 Advanced/Hard
 
### Table Columns Key
`Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode`
"Mode" = **Solo** (attempt fully independently) or **Solo→Study** (attempt first, then read an editorial even if you solve it, to see alternate approaches).
 
---
 
## 1. Master Progress Checklist
 
```
[ ] Phase 0 — Programming Foundations
[ ] Arrays Basics
[ ] Strings Basics
[ ] Hashing & Frequency Counting
[ ] Prefix Sums
[ ] Two Pointers
[ ] Sliding Window
[ ] Basic Sorting & Binary Search
[ ] Basic Recursion
[ ] Linked List
[ ] Stack
[ ] Queue / Deque
[ ] Trees / Binary Trees
[ ] Binary Search Trees
[ ] Heap / Priority Queue
[ ] Advanced Binary Search
[ ] Backtracking
[ ] Sorting Algorithms (implementation-level)
[ ] Greedy
[ ] Intervals
[ ] Matrix
[ ] Bit Manipulation
[ ] Graphs (BFS/DFS)
[ ] Topological Sort
[ ] Union-Find (DSU)
[ ] Shortest Path
[ ] Dynamic Programming — 1D
[ ] Dynamic Programming — 2D / Knapsack
[ ] Dynamic Programming — Subsequence
[ ] Advanced Greedy
[ ] Tries
[ ] Monotonic Stack
[ ] Advanced Sliding Window
[ ] Phase 5 — Interview Mixed Problems
```
 
For each topic, track (in your own notes):
- Problems assigned / Problems completed
- Skills acquired
- Mistakes made
- Ready for next topic? (Y/N)
---
 
## Phase 0 — Programming Foundations
 
### Topic 0.1 — Arrays, Loops & Basic Math
**Concept:** Comfort with iterating arrays, tracking running values (sum/max/min), basic conditionals.
**Why it matters:** Every DSA pattern is built on top of clean iteration.
**Prerequisites:** None.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 1 | Two Sum (brute force first) | Easy | Iteration | Nested loop scanning, then set up for hashing later | 20m | Solo |
| 2 | 7 | Reverse Integer | Easy | Math | Digit extraction, overflow awareness | 20m | Solo |
| 3 | branchless | Find Max/Min in Array (self-practice, no LC#) | Easy | Iteration | Tracking running extremes | 10m | Solo |
| 4 | 258 | Add Digits | Easy | Math | Loops vs. math shortcuts (digital root) | 15m | Solo |
 
**"When you see this, think..."**: "Sum/count/track something while scanning once" → single-pass iteration.
**Next:** Strings Basics.
 
### Topic 0.2 — Strings Basics
**Concept:** String traversal, character comparisons, building new strings, ASCII/char math.
**Why it matters:** Strings behave like arrays of chars — same iteration skills, new edge cases (immutability in Java, StringBuilder).
**Prerequisites:** Arrays basics.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 344 | Reverse String | Easy | Two Pointers (intro) | In-place swapping | 15m | Solo |
| 2 | 125 | Valid Palindrome | Easy⭐ | Two Pointers | Skipping non-alnum chars, `Character.isLetterOrDigit` | 20m | Solo |
| 3 | 383 | Ransom Note | Easy | Frequency Count (preview) | `int[26]` counting array | 15m | Solo |
| 4 | 14 | Longest Common Prefix | Easy+ | String scanning | Comparing across multiple strings | 20m | Solo |
 
**Java tools introduced:** `StringBuilder`, `char[]`, `String.toCharArray()`, `Character` methods.
**Next:** Hashing & Frequency Counting.
 
---
 
## Phase 1 — Basic DSA
 
### Topic 1.1 — Hashing & Frequency Counting
**Concept:** Using `HashMap`/`HashSet`/`int[]` counting arrays to trade space for O(1) average lookup time.
**Why it matters:** Turns O(n²) brute forces into O(n). This is the single highest-leverage concept in early DSA.
**Prerequisites:** Arrays, Strings.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 1 | Two Sum (optimized) | Easy⭐🧠 | Hashing | Complement lookup while scanning | 20m | Solo |
| 2 | 242 | Valid Anagram | Easy | Frequency Count | Counting array vs HashMap tradeoff | 15m | Solo |
| 3 | 349 | Intersection of Two Arrays | Easy | HashSet | Set operations | 15m | Solo |
| 4 | 387 | First Unique Character in a String | Easy | Frequency Count | Two-pass counting | 15m | Solo |
| 5 | 49 | Group Anagrams | Medium−🔥 | Hashing (key construction) | Using sorted string / char-count as map key | 30m | Solo→Study |
| 6 | 128 | Longest Consecutive Sequence | Medium🔥🧠 | HashSet | O(n) trick: only start counting from sequence beginnings | 35m | Solo→Study |
 
**"When you see this, think..."**: "Find a pair/duplicate/complement" or "count occurrences" → Hashing.
**Next:** Prefix Sums.
 
### Topic 1.2 — Prefix Sums
**Concept:** Precompute cumulative sums so range-sum queries become O(1).
**Why it matters:** Foundation for subarray-sum problems and later DP.
**Prerequisites:** Arrays, Hashing.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 303 | Range Sum Query - Immutable | Easy🧠 | Prefix Sum | Building and querying a prefix array | 15m | Solo |
| 2 | 560 | Subarray Sum Equals K | Medium⭐🔥🧠 | Prefix Sum + Hashing | Combining prefix sums with a hashmap of seen sums | 35m | Solo→Study |
| 3 | 724 | Find Pivot Index | Easy | Prefix Sum | Left-sum vs total-sum trick | 15m | Solo |
 
**"When you see this, think..."**: "Sum of a subarray/range, repeatedly" → Prefix Sum.
**Next:** Two Pointers.
 
### Topic 1.3 — Two Pointers
**Concept:** Two indices moving through a structure (same or opposite direction) to avoid nested loops.
**Prerequisites:** Arrays, sorting basics.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 26 | Remove Duplicates from Sorted Array | Easy | Two Pointers | Slow/fast pointer, in-place writes | 20m | Solo |
| 2 | 167 | Two Sum II - Input Array Is Sorted | Easy⭐🧠 | Two Pointers | Opposite-direction pointers on sorted data | 20m | Solo |
| 3 | 15 | 3Sum | Medium⭐🔥 | Two Pointers + Sorting | Fixing one element, two-pointer on the rest, dedup | 40m | Solo→Study |
| 4 | 11 | Container With Most Water | Medium🔥🧠 | Two Pointers (greedy shrink) | Why moving the shorter wall is always optimal | 30m | Solo→Study |
| 5 | 42 | Trapping Rain Water | Hard💀🔥 | Two Pointers | Combining left-max/right-max tracking | 45m | Solo→Study |
 
**"When you see this, think..."**: "Pair/triplet in sorted array" or "shrink a range from both ends" → Two Pointers.
**Next:** Sliding Window.
 
### Topic 1.4 — Sliding Window
**Concept:** A window (subarray/substring) that expands and contracts, avoiding recomputation.
**Prerequisites:** Two Pointers, Hashing.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 643 | Maximum Average Subarray I | Easy🧠 | Fixed Window | Fixed-size window sum maintenance | 15m | Solo |
| 2 | 3 | Longest Substring Without Repeating Characters | Medium⭐🔥🧠 | Variable Window | Expand/contract with a HashSet/Map | 35m | Solo→Study |
| 3 | 209 | Minimum Size Subarray Sum | Medium−🧠 | Variable Window | Shrinking window when condition is satisfied | 30m | Solo |
| 4 | 424 | Longest Repeating Character Replacement | Medium🔥 | Variable Window | Window validity via "majority count" trick | 35m | Solo→Study |
| 5 | 76 | Minimum Window Substring | Hard💀🔥 | Variable Window | Two-map matching inside a window | 50m | Solo→Study |
 
**"When you see this, think..."**: "Longest/shortest/max/min subarray or substring satisfying a condition" → Sliding Window.
**Next:** Basic Sorting & Searching.
 
### Topic 1.5 — Basic Sorting & Binary Search
**Concept:** How comparison sorting works; searching sorted data in O(log n).
**Prerequisites:** Arrays.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 704 | Binary Search | Easy⭐🧠 | Binary Search | The core template: lo/hi/mid, when to move which | 20m | Solo |
| 2 | 35 | Search Insert Position | Easy | Binary Search | Boundary (lower-bound) search | 15m | Solo |
| 3 | 34 | Find First and Last Position of Element in Sorted Array | Medium−🔥 | Binary Search | Two binary searches for left/right boundary | 30m | Solo→Study |
| 4 | 912 | Sort an Array (implement Merge Sort) | Medium− | Sorting | Divide & conquer, merge step | 35m | Solo |
 
**"When you see this, think..."**: "Search in a sorted (or sorted-like/rotated) array" → Binary Search.
**Next:** Basic Recursion.
 
### Topic 1.6 — Basic Recursion
**Concept:** Base case + recursive case; how the call stack works.
**Prerequisites:** Functions, basic math.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 509 | Fibonacci Number | Easy🧠 | Recursion | Recursion tree, exponential blow-up (motivates memoization later) | 20m | Solo |
| 2 | 50 | Pow(x, n) | Medium−🧠 | Recursion | Divide-and-conquer recursion (fast exponentiation) | 25m | Solo→Study |
| 3 | 206 | Reverse Linked List (recursive version) | Easy | Recursion | Recursing over a structure, not just numbers | 20m | Solo |
 
**"When you see this, think..."**: "Problem breaks into smaller identical subproblems" → Recursion.
**Next:** Linked Lists (Phase 2).
 
---
 
## Phase 2 — Core Data Structures
 
### Topic 2.1 — Linked Lists
**Concept:** Node-based sequential structure; pointer manipulation without array shifting.
**Why it matters:** Teaches pointer discipline that later underlies trees and graphs.
**Prerequisites:** Recursion, basic pointers/objects in Java.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 206 | Reverse Linked List (iterative) | Easy⭐🧠 | Pointer manipulation | prev/curr/next rewiring | 20m | Solo |
| 2 | 876 | Middle of the Linked List | Easy🧠 | Fast/Slow Pointers | Slow/fast pointer to find midpoint | 15m | Solo |
| 3 | 141 | Linked List Cycle | Easy⭐🧠 | Fast/Slow Pointers | Floyd's cycle detection | 20m | Solo |
| 4 | 21 | Merge Two Sorted Lists | Easy | Merge technique | Dummy head node trick | 20m | Solo |
| 5 | 19 | Remove Nth Node From End of List | Medium− | Two Pointers on List | Gap-based pointer technique | 25m | Solo |
| 6 | 143 | Reorder List | Medium🔥 | Combined technique | Middle-find + reverse + merge (combines 3 prior skills) | 35m | Solo→Study |
| 7 | 25 | Reverse Nodes in k-Group | Hard💀 | Pointer manipulation | Reversing in chunks recursively/iteratively | 45m | Solo→Study |
 
**"When you see this, think..."**: "In-place list rewiring" or "cycle/midpoint" → Fast/Slow pointers, dummy nodes.
**Next:** Stacks.
 
### Topic 2.2 — Stacks
**Concept:** LIFO structure; used for matching, undo operations, and expression evaluation.
**Prerequisites:** Arrays.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 20 | Valid Parentheses | Easy⭐🧠 | Stack matching | Push/pop matching pairs | 20m | Solo |
| 2 | 155 | Min Stack | Medium−🧠 | Stack design | Auxiliary stack to track min in O(1) | 25m | Solo |
| 3 | 150 | Evaluate Reverse Polish Notation | Medium− | Stack | Postfix expression evaluation | 25m | Solo |
| 4 | 739 | Daily Temperatures | Medium🔥🧠 | Monotonic Stack (preview) | Decreasing stack of indices | 30m | Solo→Study |
 
**Java tool:** Use `Deque<Integer>` as a stack (`push`/`pop`/`peek`) — **not** the legacy `Stack` class.
**Next:** Queues / Deques.
 
### Topic 2.3 — Queues / Deques
**Concept:** FIFO structure; deque supports both ends — key for BFS and sliding-window-max later.
**Prerequisites:** Stacks (contrast LIFO vs FIFO).
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 232 | Implement Queue using Stacks | Easy | Queue via Stack | Amortized O(1) transfer trick | 20m | Solo |
| 2 | 933 | Number of Recent Calls | Easy | Queue | Sliding time-window with a queue | 15m | Solo |
| 3 | 649 | Dota2 Senate | Medium− | Queue simulation | Round-based elimination simulation | 30m | Solo→Study |
 
**Next:** HashMap/HashSet were already introduced — move to Trees.
 
### Topic 2.4 — Trees / Binary Trees
**Concept:** Hierarchical structure; DFS (pre/in/post-order) and BFS (level order) traversals.
**Prerequisites:** Recursion, Queues (for BFS).
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 144 | Binary Tree Preorder Traversal | Easy | DFS | Recursive traversal template | 15m | Solo |
| 2 | 104 | Maximum Depth of Binary Tree | Easy⭐🧠 | DFS | Bottom-up recursive aggregation | 15m | Solo |
| 3 | 226 | Invert Binary Tree | Easy | DFS | Recursive mutation of structure | 15m | Solo |
| 4 | 102 | Binary Tree Level Order Traversal | Medium−⭐🧠 | BFS | Queue-based level-by-level processing | 25m | Solo |
| 5 | 100 | Same Tree | Easy | DFS | Structural comparison recursion | 15m | Solo |
| 6 | 543 | Diameter of Binary Tree | Medium−🔥 | DFS (post-order aggregation) | Computing a global answer during height recursion | 30m | Solo→Study |
| 7 | 105 | Construct Binary Tree from Preorder and Inorder Traversal | Medium🔥 | DFS + Hashing | Rebuilding structure from traversal orders | 40m | Solo→Study |
| 8 | 124 | Binary Tree Maximum Path Sum | Hard💀🔥 | DFS (post-order aggregation) | Local vs global max distinction | 45m | Solo→Study |
 
**"When you see this, think..."**: "Process every node / compute something bottom-up on a tree" → DFS. "Level-by-level" → BFS.
**Next:** Binary Search Trees.
 
### Topic 2.5 — Binary Search Trees (BST)
**Concept:** Ordering invariant (left < node < right) enables O(log n) search/insert on balanced trees.
**Prerequisites:** Binary Trees, Binary Search.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 700 | Search in a Binary Search Tree | Easy | BST property | Using the ordering to prune search | 15m | Solo |
| 2 | 701 | Insert into a Binary Search Tree | Easy | BST property | Recursive insertion | 15m | Solo |
| 3 | 98 | Validate Binary Search Tree | Medium−⭐🧠 | BST + DFS | Passing min/max bounds down recursion | 30m | Solo→Study |
| 4 | 230 | Kth Smallest Element in a BST | Medium−🔥 | In-order traversal | In-order traversal gives sorted order | 25m | Solo |
| 5 | 235 | Lowest Common Ancestor of a BST | Easy+🔥 | BST property | Using ordering to skip subtrees | 20m | Solo |
 
**Next:** Heaps / Priority Queues.
 
### Topic 2.6 — Heaps / Priority Queues
**Concept:** Binary heap gives O(log n) insert and O(1) access to min/max — critical for "top-K" and "repeatedly find min/max" problems.
**Prerequisites:** Trees (conceptually), Java `PriorityQueue`.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 703 | Kth Largest Element in a Stream | Easy🧠 | Min-Heap of size K | Maintaining a fixed-size heap | 20m | Solo |
| 2 | 215 | Kth Largest Element in an Array | Medium−⭐🔥🧠 | Heap / Quickselect | Heap approach vs. Quickselect tradeoff | 30m | Solo→Study |
| 3 | 347 | Top K Frequent Elements | Medium⭐🔥 | Heap + Hashing | Combining frequency count with a heap | 30m | Solo→Study |
| 4 | 973 | K Closest Points to Origin | Medium− | Heap | Custom comparator heaps | 25m | Solo |
| 5 | 295 | Find Median from Data Stream | Hard💀🔥🧠 | Two Heaps | Balancing a max-heap and min-heap | 45m | Solo→Study |
 
**"When you see this, think..."**: "Repeatedly get the min/max" or "Top-K / Kth largest" → Heap.
**Next:** Advanced Binary Search (Phase 3).
 
---
 
## Phase 3 — Core Algorithms
 
### Topic 3.1 — Advanced Binary Search
**Concept:** Binary search on answer spaces, rotated arrays, and 2D grids — not just plain sorted arrays.
**Prerequisites:** Binary Search basics.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 153 | Find Minimum in Rotated Sorted Array | Medium−🧠 | Binary Search on rotated array | Deciding which half is sorted | 25m | Solo |
| 2 | 33 | Search in Rotated Sorted Array | Medium⭐🔥 | Binary Search on rotated array | Combining rotation logic with target search | 30m | Solo→Study |
| 3 | 74 | Search a 2D Matrix | Medium− | Binary Search on grid | Treating 2D as flattened 1D index space | 20m | Solo |
| 4 | 875 | Koko Eating Bananas | Medium🔥🧠 | Binary Search on Answer | Binary searching a feasibility function, not a value | 35m | Solo→Study |
| 5 | 1011 | Capacity To Ship Packages Within D Days | Medium🔥 | Binary Search on Answer | Same pattern reinforced | 30m | Solo |
 
**"When you see this, think..."**: "Minimize the maximum / maximize the minimum, subject to a feasibility check" → Binary Search on Answer.
**Next:** Backtracking.
 
### Topic 3.2 — Backtracking
**Concept:** Explore all choices via recursion, undoing (backtracking) invalid/explored choices.
**Prerequisites:** Recursion, basic DFS.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 78 | Subsets | Medium−⭐🧠 | Backtracking | The core "choose/explore/unchoose" template | 30m | Solo |
| 2 | 46 | Permutations | Medium−🔥 | Backtracking | Tracking used elements | 30m | Solo |
| 3 | 39 | Combination Sum | Medium🔥 | Backtracking | Reusing elements + pruning by sum | 35m | Solo→Study |
| 4 | 22 | Generate Parentheses | Medium🔥🧠 | Backtracking | Pruning with validity constraints | 30m | Solo |
| 5 | 79 | Word Search | Medium🔥 | Backtracking on Grid | Grid DFS with visited marking | 35m | Solo→Study |
| 6 | 51 | N-Queens | Hard💀🔥 | Backtracking | Constraint propagation across rows/cols/diagonals | 50m | Solo→Study |
 
**"When you see this, think..."**: "All possible combinations/subsets/permutations/arrangements" → Backtracking.
**Next:** Greedy.
 
### Topic 3.3 — Greedy
**Concept:** Make the locally optimal choice at each step and prove (or trust) it leads to a global optimum.
**Prerequisites:** Sorting, basic proofs-by-intuition.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 121 | Best Time to Buy and Sell Stock | Easy⭐🧠 | Greedy | Tracking running min while scanning | 20m | Solo |
| 2 | 455 | Assign Cookies | Easy | Greedy + Sorting | Sort both sides, greedily match | 20m | Solo |
| 3 | 55 | Jump Game | Medium−🔥🧠 | Greedy | Tracking furthest reachable index | 25m | Solo |
| 4 | 45 | Jump Game II | Medium🔥 | Greedy | Level-by-level greedy (BFS-like greedy) | 30m | Solo→Study |
| 5 | 134 | Gas Station | Medium🔥🧠 | Greedy | Total-sum feasibility + reset-on-negative trick | 30m | Solo→Study |
 
**"When you see this, think..."**: "Locally best choice never hurts the final answer" → Greedy (verify with a small proof/counterexample check).
**Next:** Intervals.
 
### Topic 3.4 — Intervals
**Concept:** Sorting by start/end and sweeping through to merge, insert, or count overlaps.
**Prerequisites:** Sorting, Greedy.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 56 | Merge Intervals | Medium−⭐🔥🧠 | Intervals | Sort by start, merge on overlap | 30m | Solo |
| 2 | 57 | Insert Interval | Medium− | Intervals | Three-phase scan (before/overlap/after) | 30m | Solo |
| 3 | 435 | Non-overlapping Intervals | Medium🔥 | Intervals + Greedy | Sort by end, greedily keep earliest-ending | 30m | Solo→Study |
| 4 | 252 | Meeting Rooms (Premium alt: check overlap logic) | Easy | Intervals | Basic overlap detection | 15m | Solo |
| 5 | 253 | Meeting Rooms II | Medium🔥🧠 | Intervals + Heap | Min-heap of end times to track concurrent rooms | 35m | Solo→Study |
 
**Next:** Matrix problems.
 
### Topic 3.5 — Matrix Problems
**Concept:** Traversal patterns (spiral, rotate, transpose) and DFS/BFS on 2D grids.
**Prerequisites:** Arrays, DFS/BFS basics.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 48 | Rotate Image | Medium−🔥 | Matrix manipulation | Transpose + reverse trick | 25m | Solo |
| 2 | 54 | Spiral Matrix | Medium−🔥 | Matrix traversal | Boundary-shrinking traversal | 30m | Solo |
| 3 | 73 | Set Matrix Zeroes | Medium− | Matrix manipulation | O(1) space marking using first row/col | 30m | Solo→Study |
| 4 | 200 | Number of Islands | Medium⭐🔥🧠 | Grid DFS/BFS | Connected components on a grid (bridges into Graphs) | 35m | Solo |
 
**Next:** Bit Manipulation.
 
### Topic 3.6 — Bit Manipulation
**Concept:** AND/OR/XOR/shifts to solve problems in O(1) extra space or spot patterns numerically.
**Prerequisites:** Basic math.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 136 | Single Number | Easy⭐🧠 | XOR | XOR cancels duplicates | 15m | Solo |
| 2 | 191 | Number of 1 Bits | Easy | Bit shifting | `n & (n-1)` trick | 15m | Solo |
| 3 | 338 | Counting Bits | Easy+🧠 | Bit DP (preview) | Building on smaller subproblem bit counts | 20m | Solo |
| 4 | 371 | Sum of Two Integers | Medium− | Bit manipulation | Simulating addition with XOR/AND/shift | 30m | Solo→Study |
 
**"When you see this, think..."**: "Find the unique/odd-one-out number" or "no extra space allowed" → XOR/Bit tricks.
**Next:** Graphs (Phase 4).
 
---
 
## Phase 4 — Advanced DSA
 
### Topic 4.1 — Graphs: BFS & DFS
**Concept:** Representing graphs (adjacency list), traversal, connected components.
**Prerequisites:** Trees, Queues, Matrix DFS/BFS (Number of Islands was the bridge).
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 133 | Clone Graph | Medium−🔥🧠 | Graph DFS/BFS | HashMap to track visited/cloned nodes | 35m | Solo→Study |
| 2 | 207 | Course Schedule | Medium⭐🔥🧠 | Graph DFS (cycle detection) | Detecting cycles = prerequisite for topological sort | 40m | Solo→Study |
| 3 | 417 | Pacific Atlantic Water Flow | Medium🔥 | Multi-source DFS/BFS | Reverse-thinking: flow from the oceans inward | 40m | Solo→Study |
| 4 | 994 | Rotting Oranges | Medium−🔥🧠 | Multi-source BFS | BFS layer-by-layer = shortest time simulation | 30m | Solo |
 
**"When you see this, think..."**: "Connections / reachability / spreading outward" → Graph DFS/BFS.
**Next:** Topological Sort.
 
### Topic 4.2 — Topological Sort
**Concept:** Ordering nodes in a DAG so every edge points forward.
**Prerequisites:** Graph DFS/BFS, cycle detection.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 207 | Course Schedule (revisit via Kahn's algorithm) | Medium−🧠 | Topological Sort | BFS-based (in-degree) topological sort | 25m | Solo |
| 2 | 210 | Course Schedule II | Medium🔥 | Topological Sort | Producing the actual ordering | 30m | Solo |
 
**Next:** Union-Find.
 
### Topic 4.3 — Union-Find (DSU)
**Concept:** Efficiently track and merge connected components with path compression and union by rank.
**Prerequisites:** Graphs (conceptually).
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 547 | Number of Provinces | Medium−🧠 | Union-Find | Basic DSU template | 30m | Solo→Study |
| 2 | 684 | Redundant Connection | Medium🔥🧠 | Union-Find | Detecting the edge that creates a cycle | 30m | Solo |
| 3 | 200 | Number of Islands (redo with DSU) | Medium | Union-Find | Same problem, alternate technique — compare vs. DFS | 25m | Solo |
 
**"When you see this, think..."**: "Connected components / merge groups / detect a cycle in an undirected graph" → Union-Find.
**Next:** Shortest Path.
 
### Topic 4.4 — Shortest Path
**Concept:** BFS for unweighted graphs, Dijkstra for weighted non-negative graphs.
**Prerequisites:** Graph BFS, Heaps.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 1091 | Shortest Path in Binary Matrix | Medium− | BFS Shortest Path | BFS = shortest path in unweighted graphs | 25m | Solo |
| 2 | 743 | Network Delay Time | Medium🔥🧠 | Dijkstra | Heap-based Dijkstra implementation | 40m | Solo→Study |
| 3 | 787 | Cheapest Flights Within K Stops | Medium+🔥💀 | Modified Dijkstra / Bellman-Ford | Constraint on number of edges changes the algorithm | 45m | Solo→Study |
 
**Next:** Dynamic Programming.
 
### Topic 4.5 — Dynamic Programming — 1D
**Concept:** Breaking a problem into overlapping subproblems, storing results (memoization/tabulation).
**Prerequisites:** Recursion, Fibonacci (Topic 1.6) as the bridge.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 70 | Climbing Stairs | Easy⭐🧠 | 1D DP | Recursion → memoization → tabulation progression | 25m | Solo |
| 2 | 198 | House Robber | Medium−⭐🔥🧠 | 1D DP | "Take or skip" decision DP | 30m | Solo |
| 3 | 213 | House Robber II | Medium− | 1D DP | Handling a circular constraint | 25m | Solo |
| 4 | 322 | Coin Change | Medium⭐🔥🧠 | 1D DP (unbounded) | Unbounded choice DP, `dp[amount]` | 35m | Solo→Study |
| 5 | 139 | Word Break | Medium🔥 | 1D DP + Hashing | DP over string boundaries | 35m | Solo→Study |
 
**"When you see this, think..."**: "Number of ways / min-max cost, with choices at each step, and overlapping subproblems" → DP.
**Next:** 2D DP / Knapsack.
 
### Topic 4.6 — Dynamic Programming — 2D & Knapsack Patterns
**Concept:** DP states depending on two changing variables (two strings, or item+capacity).
**Prerequisites:** 1D DP.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 62 | Unique Paths | Medium−🧠 | 2D DP (grid) | Grid DP, base row/column | 25m | Solo |
| 2 | 64 | Minimum Path Sum | Medium− | 2D DP (grid) | Grid DP with cost accumulation | 25m | Solo |
| 3 | 416 | Partition Equal Subset Sum | Medium🔥🧠 | 0/1 Knapsack | Classic knapsack "can we reach target sum" | 35m | Solo→Study |
| 4 | 494 | Target Sum | Medium🔥 | 0/1 Knapsack (variant) | Reframing +/- assignment as a subset-sum knapsack | 35m | Solo→Study |
 
**Next:** Subsequence DP.
 
### Topic 4.7 — Dynamic Programming — Subsequence Patterns
**Concept:** DP over pairs of strings/sequences (LCS-style) — a very common interview family.
**Prerequisites:** 2D DP.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 1143 | Longest Common Subsequence | Medium⭐🔥🧠 | Subsequence DP | The canonical 2D subsequence DP table | 35m | Solo→Study |
| 2 | 300 | Longest Increasing Subsequence | Medium⭐🔥🧠 | Subsequence DP | O(n²) DP, then patience-sorting O(n log n) optimization | 40m | Solo→Study |
| 3 | 72 | Edit Distance | Hard💀🔥 | Subsequence DP | Three-way transition (insert/delete/replace) | 45m | Solo→Study |
 
**Next:** Advanced Greedy.
 
### Topic 4.8 — Advanced Greedy
**Concept:** Greedy problems that require a non-obvious proof/insight, often paired with sorting or a heap.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 621 | Task Scheduler | Medium🔥🧠 | Greedy + Math/Heap | Frequency-driven greedy scheduling | 35m | Solo→Study |
| 2 | 763 | Partition Labels | Medium−🔥 | Greedy + Intervals | Last-occurrence tracking as an implicit interval merge | 25m | Solo |
 
**Next:** Tries.
 
### Topic 4.9 — Tries
**Concept:** A tree structure specialized for prefix-based string storage/search.
**Prerequisites:** Trees, HashMap.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 208 | Implement Trie (Prefix Tree) | Medium−⭐🧠 | Trie | Node structure with children map + end-of-word flag | 35m | Solo |
| 2 | 211 | Design Add and Search Words Data Structure | Medium🔥 | Trie + DFS | Wildcard search via DFS through trie | 35m | Solo→Study |
 
**"When you see this, think..."**: "Prefix search / autocomplete / word dictionary" → Trie.
**Next:** Monotonic Stack.
 
### Topic 4.10 — Monotonic Stack
**Concept:** A stack kept increasing or decreasing to answer "next greater/smaller element" style queries in O(n).
**Prerequisites:** Stacks (Daily Temperatures was the preview).
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 496 | Next Greater Element I | Easy🧠 | Monotonic Stack | Basic decreasing-stack template | 20m | Solo |
| 2 | 739 | Daily Temperatures (revisit) | Medium−🧠 | Monotonic Stack | Reinforce with indices instead of values | 20m | Solo |
| 3 | 84 | Largest Rectangle in Histogram | Hard💀🔥 | Monotonic Stack | Using the stack to find left/right boundaries per bar | 45m | Solo→Study |
 
**"When you see this, think..."**: "Next/previous greater or smaller element" → Monotonic Stack.
**Next:** Advanced Sliding Window.
 
### Topic 4.11 — Advanced Sliding Window
**Concept:** Sliding window combined with a deque or heap to track window max/min in O(1) amortized.
**Prerequisites:** Sliding Window, Deque, Monotonic Stack.
 
| Order | LC# | Problem | Diff | Pattern | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 239 | Sliding Window Maximum | Hard💀🔥🧠 | Monotonic Deque | Deque holding decreasing candidates for window max | 45m | Solo→Study |
| 2 | 1004 | Max Consecutive Ones III | Medium🔥 | Sliding Window | Window with a "budget" of flips allowed | 30m | Solo |
 
**Next:** Phase 5 — Interview Preparation.
 
---
 
## Phase 5 — Interview Preparation (Mixed / Multi-Pattern)
 
These combine two or more patterns from earlier phases. By now you should attempt every problem with **zero hints for the first 30–40 minutes**.
 
| Order | LC# | Problem | Diff | Patterns Combined | What You Learn | Time | Mode |
|---|---|---|---|---|---|---|---|
| 1 | 5 | Longest Palindromic Substring | Medium🔥 | Two Pointers + DP (expand-around-center) | Expand-around-center vs DP tradeoffs | 35m | Solo→Study |
| 2 | 33 | (revisit) Search in Rotated Sorted Array | Medium | Binary Search | Speed drill — should now take <15 min | 15m | Solo |
| 3 | 146 | LRU Cache | Medium⭐🔥 | HashMap + Doubly Linked List | Designing a data structure combining two structures | 45m | Solo→Study |
| 4 | 236 | Lowest Common Ancestor of a Binary Tree | Medium🔥 | Tree DFS | LCA without the BST ordering shortcut | 30m | Solo |
| 5 | 621 | (revisit) Task Scheduler | Medium | Greedy + Heap | Speed drill | 20m | Solo |
| 6 | 128 | (revisit) Longest Consecutive Sequence | Medium | Hashing | Speed drill — target O(n) in one pass | 15m | Solo |
| 7 | handling | Merge K Sorted Lists (LC 23) | Hard💀🔥 | Heap + Linked List | Combining heap with linked-list merging | 40m | Solo→Study |
| 8 | 79 | (revisit) Word Search | Medium | Backtracking + Grid | Speed drill | 20m | Solo |
| 9 | 76 | (revisit) Minimum Window Substring | Hard | Sliding Window + Hashing | Speed drill — full mastery check | 30m | Solo |
| 10 | productive | Word Ladder (LC 127) | Hard💀🔥 | BFS on implicit graph | Recognizing a graph hidden inside a word problem | 45m | Solo→Study |
| 11 | productive | Trapping Rain Water II (LC 407) | Hard💀 | Heap + BFS/Matrix | 2D generalization of a 1D pattern you already know | 50m | Solo→Study |
| 12 | productive | Word Break II (LC 140) | Hard💀 | Backtracking + DP (memoized) | Combining backtracking with memoization to avoid recomputation | 45m | Solo→Study |
| 13 | productive | Alien Dictionary (LC 269, Premium — use a similar free alt if unavailable) | Hard💀🔥 | Topological Sort | Extracting graph edges from an unusual input format | 45m | Solo→Study |
| 14 | productive | Serialize and Deserialize Binary Tree (LC 297) | Hard💀🔥 | Tree DFS/BFS + Design | Encoding/decoding structure, not just values | 40m | Solo→Study |
| 15 | productive | Median of Two Sorted Arrays (LC 4) | Hard💀🔥 | Binary Search (advanced) | The hardest binary-search-on-answer problem on this list | 60m | Solo→Study (this one, study without shame) |
 
---
 
## 2. Complete Problem Checklist (In Solving Order)
 
1. Two Sum (brute force) — LC1
2. Reverse Integer — LC7
3. Find Max/Min in Array (self-practice)
4. Add Digits — LC258
5. Reverse String — LC344
6. Valid Palindrome — LC125
7. Ransom Note — LC383
8. Longest Common Prefix — LC14
9. Two Sum (hashmap) — LC1
10. Valid Anagram — LC242
11. Intersection of Two Arrays — LC349
12. First Unique Character in a String — LC387
13. Group Anagrams — LC49
14. Longest Consecutive Sequence — LC128
15. Range Sum Query - Immutable — LC303
16. Subarray Sum Equals K — LC560
17. Find Pivot Index — LC724
18. Remove Duplicates from Sorted Array — LC26
19. Two Sum II — LC167
20. 3Sum — LC15
21. Container With Most Water — LC11
22. Trapping Rain Water — LC42
23. Maximum Average Subarray I — LC643
24. Longest Substring Without Repeating Characters — LC3
25. Minimum Size Subarray Sum — LC209
26. Longest Repeating Character Replacement — LC424
27. Minimum Window Substring — LC76
28. Binary Search — LC704
29. Search Insert Position — LC35
30. Find First and Last Position of Element in Sorted Array — LC34
31. Sort an Array (Merge Sort) — LC912
32. Fibonacci Number — LC509
33. Pow(x, n) — LC50
34. Reverse Linked List (recursive) — LC206
35. Reverse Linked List (iterative) — LC206
36. Middle of the Linked List — LC876
37. Linked List Cycle — LC141
38. Merge Two Sorted Lists — LC21
39. Remove Nth Node From End of List — LC19
40. Reorder List — LC143
41. Reverse Nodes in k-Group — LC25
42. Valid Parentheses — LC20
43. Min Stack — LC155
44. Evaluate Reverse Polish Notation — LC150
45. Daily Temperatures — LC739
46. Implement Queue using Stacks — LC232
47. Number of Recent Calls — LC933
48. Dota2 Senate — LC649
49. Binary Tree Preorder Traversal — LC144
50. Maximum Depth of Binary Tree — LC104
51. Invert Binary Tree — LC226
52. Binary Tree Level Order Traversal — LC102
53. Same Tree — LC100
54. Diameter of Binary Tree — LC543
55. Construct Binary Tree from Preorder and Inorder Traversal — LC105
56. Binary Tree Maximum Path Sum — LC124
57. Search in a Binary Search Tree — LC700
58. Insert into a Binary Search Tree — LC701
59. Validate Binary Search Tree — LC98
60. Kth Smallest Element in a BST — LC230
61. Lowest Common Ancestor of a BST — LC235
62. Kth Largest Element in a Stream — LC703
63. Kth Largest Element in an Array — LC215
64. Top K Frequent Elements — LC347
65. K Closest Points to Origin — LC973
66. Find Median from Data Stream — LC295
67. Find Minimum in Rotated Sorted Array — LC153
68. Search in Rotated Sorted Array — LC33
69. Search a 2D Matrix — LC74
70. Koko Eating Bananas — LC875
71. Capacity To Ship Packages Within D Days — LC1011
72. Subsets — LC78
73. Permutations — LC46
74. Combination Sum — LC39
75. Generate Parentheses — LC22
76. Word Search — LC79
77. N-Queens — LC51
78. Best Time to Buy and Sell Stock — LC121
79. Assign Cookies — LC455
80. Jump Game — LC55
81. Jump Game II — LC45
82. Gas Station — LC134
83. Merge Intervals — LC56
84. Insert Interval — LC57
85. Non-overlapping Intervals — LC435
86. Meeting Rooms — LC252
87. Meeting Rooms II — LC253
88. Rotate Image — LC48
89. Spiral Matrix — LC54
90. Set Matrix Zeroes — LC73
91. Number of Islands — LC200
92. Single Number — LC136
93. Number of 1 Bits — LC191
94. Counting Bits — LC338
95. Sum of Two Integers — LC371
96. Clone Graph — LC133
97. Course Schedule (DFS) — LC207
98. Pacific Atlantic Water Flow — LC417
99. Rotting Oranges — LC994
100. Course Schedule (Kahn's/BFS revisit) — LC207
101. Course Schedule II — LC210
102. Number of Provinces — LC547
103. Redundant Connection — LC684
104. Number of Islands (DSU redo) — LC200
105. Shortest Path in Binary Matrix — LC1091
106. Network Delay Time — LC743
107. Cheapest Flights Within K Stops — LC787
108. Climbing Stairs — LC70
109. House Robber — LC198
110. House Robber II — LC213
111. Coin Change — LC322
112. Word Break — LC139
113. Unique Paths — LC62
114. Minimum Path Sum — LC64
115. Partition Equal Subset Sum — LC416
116. Target Sum — LC494
117. Longest Common Subsequence — LC1143
118. Longest Increasing Subsequence — LC300
119. Edit Distance — LC72
120. Task Scheduler — LC621
121. Partition Labels — LC763
122. Implement Trie (Prefix Tree) — LC208
123. Design Add and Search Words Data Structure — LC211
124. Next Greater Element I — LC496
125. Daily Temperatures (revisit) — LC739
126. Largest Rectangle in Histogram — LC84
127. Sliding Window Maximum — LC239
128. Max Consecutive Ones III — LC1004
129. Longest Palindromic Substring — LC5
130. Search in Rotated Sorted Array (revisit) — LC33
131. LRU Cache — LC146
132. Lowest Common Ancestor of a Binary Tree — LC236
133. Task Scheduler (revisit) — LC621
134. Longest Consecutive Sequence (revisit) — LC128
135. Merge K Sorted Lists — LC23
136. Word Search (revisit) — LC79
137. Minimum Window Substring (revisit) — LC76
138. Word Ladder — LC127
139. Trapping Rain Water II — LC407
140. Word Break II — LC140
141. Alien Dictionary — LC269 (or nearest free equivalent)
142. Serialize and Deserialize Binary Tree — LC297
143. Median of Two Sorted Arrays — LC4
---
 
## 3. Pattern Recognition Cheat Sheet
 
| Signal in the problem statement | Pattern | Example problems |
|---|---|---|
| "Find a pair/triplet that sums to..." | Two Pointers (if sortable) or Hashing | Two Sum, 3Sum |
| "Longest/shortest subarray or substring satisfying X" | Sliding Window | LC3, LC76, LC424 |
| "Count occurrences / detect duplicates / anagram" | Hashing / Frequency Count | LC242, LC49 |
| "Repeatedly find min/max, top-K, Kth largest" | Heap / Priority Queue | LC215, LC295, LC347 |
| "Search in sorted (or rotated) array" | Binary Search | LC704, LC33, LC153 |
| "Minimize the max / maximize the min, feasibility check" | Binary Search on Answer | LC875, LC1011 |
| "All possible subsets/combinations/permutations/arrangements" | Backtracking | LC78, LC46, LC51 |
| "Locally optimal choice, sorted order helps" | Greedy | LC55, LC134, LC763 |
| "Overlapping ranges, scheduling, merging times" | Intervals | LC56, LC253 |
| "Number of ways to reach a target / min-max cost with choices" | Dynamic Programming | LC70, LC322, LC416 |
| "Compare/align two strings or sequences" | Subsequence DP | LC1143, LC300, LC72 |
| "Connected components / islands / reachability" | Graph DFS/BFS or Union-Find | LC200, LC547 |
| "Shortest number of steps/hops in an unweighted graph" | BFS | LC994, LC127 |
| "Shortest path with weighted edges" | Dijkstra | LC743, LC787 |
| "Order tasks given dependencies" | Topological Sort | LC207, LC210 |
| "Next greater/smaller element" | Monotonic Stack | LC496, LC739, LC84 |
| "Sliding window maximum/minimum efficiently" | Monotonic Deque | LC239 |
| "Prefix search / autocomplete / word dictionary" | Trie | LC208, LC211 |
| "No extra space / find the unique number" | Bit Manipulation (XOR) | LC136, LC371 |
| "Sum of a range, repeatedly" | Prefix Sum | LC303, LC560 |
| "Reverse/rearrange a linked list in place" | Pointer manipulation (prev/curr/next) | LC206, LC25 |
| "Detect a cycle" | Fast/Slow pointers (list) or DFS coloring (graph) | LC141, LC207 |
 
---
 
## 4. Spaced Repetition / Revision Schedule
 
Every problem marked 🧠 or ⭐ goes into your revision rotation:
 
- **Day 0** — Solve it (using the 12-step method).
- **Day 3** — Re-solve from scratch, no notes. If stuck >10 min, re-read your Day 0 notes, don't re-read the solution.
- **Day 7** — Re-solve from scratch. Time yourself against your Day 0 time.
- **Day 30** — Re-solve from scratch. This is the real test of retention.
- **Day 90 (topic-level)** — Instead of a single problem, re-solve 2–3 random problems from that whole topic to confirm the *pattern*, not just the problem, stuck.
**Practical tracking tip:** keep a simple spreadsheet or the LC "list" feature with columns: `Problem | Day 0 date | Day 3 done? | Day 7 done? | Day 30 done? | Confidence (1-5)`.
 
**Priority order for revision if you're short on time:** ⭐ Must-Solve first, then 🔥 interview-frequent, then 🧠 pattern-defining, then 💀 hard problems last (these consolidate everything above).
 
---
 
## 5. Common DSA Mistakes (and how to avoid them)
 
1. **Jumping to code before understanding the problem.** → Force yourself to write 2 examples by hand first (Step 2 of the method).
2. **Only memorizing solutions instead of the pattern.** → After solving, always write "what pattern was this?" and "what phrase in the problem signaled it?"
3. **Skipping brute force.** → Brute force almost always reveals *why* the optimized approach works; skipping it makes the "trick" feel like magic instead of logic.
4. **Not testing edge cases** (empty array, single element, all duplicates, negative numbers). → Make this a mandatory step before considering a problem "done."
5. **Over-relying on hints.** → Use Hint 1 before Hint 2; never skip straight to the solution. Track how often you need hints per topic — rising hint usage on a topic means you should slow down there.
6. **Treating every Medium/Hard the same.** → Some Mediums are templated (Medium−), some need real insight (Medium+). Mislabeling difficulty leads to false confidence.
7. **Not revisiting old problems.** → Without the Day 3/7/30 revision cycle, patterns fade in 2–3 weeks even after a "successful" solve.
8. **Writing Java without knowing the right built-in tool** (e.g., manually implementing a stack instead of using `Deque`). → Learn the standard library methods listed per topic as you go.
9. **Confusing "I understood the editorial" with "I can solve this independently."** → Always re-attempt a studied problem cold, a few days later, with zero references.
10. **Avoiding Hard problems entirely.** → Even attempting for 20–30 minutes (then studying) builds pattern recognition faster than skipping them.
---
 
## 6. Progression Rules
 
- If you can solve **Easy Two Pointers/Hashing problems in under 15 minutes** with no hints → move from Phase 1 into Phase 2 Linked Lists/Trees.
- If you can **write a BFS/DFS template from memory** without looking it up → move from Trees into Graphs.
- If you can **identify "Binary Search on Answer" vs "Binary Search on Array"** correctly on sight → move into Backtracking.
- If you can **explain why a Greedy solution works** (not just that it passes) → move into Intervals and Advanced Greedy.
- If you can **write the 1D DP recurrence on paper before coding** → move into 2D DP and Knapsack.
- If you can **solve Medium DP problems in under 35 minutes** → move into Subsequence DP and Phase 5.
- If, in Phase 5, you can **identify which pattern (or combination) applies within the first 5 minutes of reading a new Medium problem** → you are ready for real interview-style mock sessions and timed contests.
---
 
## 7. Final Interview Readiness Checklist
 
After completing this roadmap, you should be able to, independently and without hints:
 
- Recognize the underlying pattern of most Easy/Medium LeetCode problems within the first few minutes of reading them
- Implement, from memory: binary search, DFS/BFS (tree and graph), backtracking template, sliding window template, monotonic stack, Dijkstra, topological sort (both DFS and Kahn's), and 1D/2D DP with both memoization and tabulation
- Comfortably use Java's `HashMap`, `HashSet`, `Deque` (as stack and queue), `PriorityQueue` (with custom comparators), `Arrays.sort`, and `Collections` utilities
- Analyze time/space complexity of your own solutions correctly on the first attempt
- Solve most "medium" interview problems in 25–35 minutes, and know when to ask clarifying questions on ambiguous ones
- Attempt hard problems by decomposing them into 2–3 patterns you already know, rather than freezing
- Explain your thought process out loud clearly — this roadmap's 12-step method doubles as your "think-aloud" interview structure
You are ready for real interview loops when you can consistently do the above across **all 6 phases**, not just isolated topics.
 
---
 
*Work through this top to bottom. Don't skip phases even if a topic looks "easy" — each one is deliberately positioned to set up the next. Good luck.*
 

# Technical Interview: Core Questions
| Category  | Name                                      |   Notes
| -         | -                                         |   -
| Array     | Two Sum                                   | single pass over array -> keep track of numbers and their indices -> if target - current number is in the hashmap, return the indices of current number and its compliment -> add current number and its indice to the hashmap  
| Array     | Best Time to Buy & Sell Stock             | single pass over the array -> min(current minimum, todays price) -> max(current max profit, todays price - minimium price);
| Array     | Contains Duplicate                        |
| Array     | Product of Array Except Self              |
| Array     | Maximum Subarray                          |
| Array     | Maximum Product Subarray                  |
| Array     | Find Minimum in Rotated Sorted Array      |
| Array     | Search in Rotated Sorted Array            |
| Array     | 3Sum                                      |
| Array     | Container w/ Most Water                   |
| Array     | Fruits in Baskets                         |
| Graph     | Clone Graph                               | BFS so keep a queue of original nodes -> Visited nodes will be kept in a HashMap<Node, Node> that maps original->clone -> While the queue has stuff in it, grab the front of the queue (queue only contains unvisited originals)-> for each neighbor node that has not yet been visited, enqueue it and create a clone of it in our hash table -> add the clone of the neighbor to list of the clone of THIS (polled Node) node's neighbors
| Graph     | Course Schedule                           | This is a directed graph problem, we are looking for cycles (circular dependencies of prereqs) -> Create an adjacency list with HashMap (key, val) = (course, list of prereqs) -> iterate over all course (even those without prereqs) and DFS to find any cycles, make sure to keep track of visited -> DFS rules: if a course has no prereqs then it can be completed, if a course has already been visited this cycle it cannot be completed -> DFS: visit this course and recursively search all children to there base cases, any failures propogate ALL THE WAY up -> DFS: if no children fail, we are done visiting THIS course and IT CAN BE completed so remove it from the adjaceny list and return true.
| Graph     | Pacific Atlantic Water Flow               |
| Graph     | Number of Islands                         | iterate over matrix -> if cell is '1' then it is an island -> BFS island to find boundaries, search unvisited cells with values == '1' (keep track of visited nodes in a set) -> When BFS determines boundaries, increment island count and continue matrix iteration -> when you find another '1' cell, only increment islands and BFS it if it has not already been visited (it is not part of another island) --> return island count
| Graph     | Longest Consecutive Sequence              |
| Graph     | Alien Dictionary                          |
| Graph     | Graph Valid Tree                          |
| Graph     | Connected Components in Undirecetd Graph  |
| Tree      | Maximum Depth Binary Tree                 |
| Tree      | Same Tree                                 |
| Tree      | Invert Tree                               |
| Tree      | Binary Tree Maximum Path Sum              |
| Tree      | Binary Tree Level Order Traversal         |
| Tree      | Serialize & Deserialize Binary Tree       |
| Tree      | Subtree of Another Tree                   |
| Tree      | Construct Tree from Preorder Inorder      |
| Tree      | Validate BST                              |
| Tree      | Kth Smallest Element in a BST             |
| Tree      | Lowest Common Ancestor of BST             |
| Tree      | Implement Trie                            |
| Tree      | Add and Search Word                       |
| Tree      | Word Search II                            |
| String    | Longest Substring w/o Repeating Char      |
| String    | Minimum Window Substring                  |
| String    | Valid Anagram                             |
| String    | Group Anagrams                            |
| String    | Palindromic Substring                     |
| String    | Encode and Decode String                  |

## Tags
#interview #datastructures #algorithms

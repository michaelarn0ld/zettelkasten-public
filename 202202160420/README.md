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
| Graph     | Course Schedule                           | This is a directed graph problem, we are looking for cycles (circular dependencies of prereqs) -> Create an adjacency list with HashMap (key, val) = (course, list of prereqs) -> iterate over all course (even those without prereqs) and DFS to find any cycles, make sure to keep track of visited -> DFS rules: if a course has no prereqs then it can be completed, if a course is visited twice before the search ends, there is a cycle, and it cannot be completed -> DFS: visit this course and recursively search all children to there base cases, any failures propogate ALL THE WAY up -> DFS: if no children fail, we are done visiting THIS course and IT CAN BE completed so remove it from the adjaceny list and return true.
| Graph     | Pacific Atlantic Water Flow               | DFS problem, created one set of nodes which can reach the atlantic ocean, create another set of nodes which can reach the pacific ocean -> iterate over top row and DFS for pacific ocean reachable nodes -> do the same for bottom node and atlantic set -> repeat the previous two steps for the left and right matrix borders -> Iterate over the entire matrix and check if nodes exist in both the pacific and atlantic set, for nodes that exist in both, add them to the result -> DFS Rules: do not search already visited nodes, do not search nodes that are out of bounds, do not search nodes that are LOWER in elevation than the caller (we are searching from sea to inland so inland nodes must be higher elevation!) -> If node meets DFS rules, add it to the visited set and search its neighbors
| Graph     | Number of Islands                         | iterate over matrix -> if cell is '1' then it is an island -> BFS island to find boundaries, search unvisited cells with values == '1' (keep track of visited nodes in a set) -> When BFS determines boundaries, increment island count and continue matrix iteration -> when you find another '1' cell, only increment islands and BFS it if it has not already been visited (it is not part of another island) --> return island count
| Graph     | Longest Consecutive Sequence              |
| Graph     | Alien Dictionary                          |
| Graph     | Graph Valid Tree                          |
| Graph     | Connected Components in Undirecetd Graph  |
| Tree      | Maximum Depth Binary Tree                 |
| Tree      | Same Tree                                 | If both roots are null, then the trees are the same! If one root is null and the other is not or their values are different, then the trees are different! -> otherwise, the roots are not null and their current values are the same so lets recursively check the left and right subtrees until we meet a base case!
| Tree      | Invert Tree                               |
| Tree      | Binary Tree Maximum Path Sum              |
| Tree      | Binary Tree Level Order Traversal         |
| Tree      | Serialize & Deserialize Binary Tree       |
| Tree      | Subtree of Another Tree                   | There is 1 or more nodes in the root and the subRoot, so we will recursively check sub-trees from the root until one matches or they all fail -> while the root is not null, if THIS root is equivalent to the subRoot we are looking for -> recursively process the left and right subtrees of THIS root check them against the GLOBAL subtree -> the method that checks whether a given root and subroot are the same has the following logic: if root and subroot are both null then the trees are the same, if one or the other is null or their values are different then the trees are different, otherwise the values are the same, so recursively check that the roots left subtree is equal to the subRoots left subtree and the roots right subtree is equal to the subRoots right subtree
| Tree      | Construct Tree from Preorder Inorder      |
| Tree      | Validate BST                              |
| Tree      | Kth Smallest Element in a BST             |
| Tree      | Lowest Common Ancestor of BST             |
| Tree      | Implement Trie                            |
| Tree      | Add and Search Word                       |
| Tree      | Word Search II                            |
| String    | Longest Substring w/o Repeating Char      | Sliding window (fast/slow)! Use a map to (k,v) = (char, freq) -> keep track of current substring length and maximum subtring length -> iterate over the FAST and increment the frequency of the current character, increment the current substring length as well -> while the frequency of the FAST char is greater than 0 (substring does not contain all uniques), first update the max, then decrement the freq of the char at the SLOW pointer, decrement the current substring length, and move the SLOW ptr to the right -> once this is all done, we have iterated over the entire string, return the maximum substring length (max of max and current)
| String    | Minimum Window Substring                  |
| String    | Valid Anagram                             | Strings that are not equal length are not anagrams -> the problem constrains us to lowercase english characters so initialize an int[26] to store the frequencies of character -> simutaneously iterate over both strings (s, t) and increment the frequency of char in s, decrement the frequency of char in t -> if the strings are anagrams, then all characters should have cancelled each other out and the frequency array should only contain zeroes.
| String    | Group Anagrams                            | We are going to hash the strings into their character frequencies -> "aab" becomes "#2#1#0#0#0..." -> We will keep these String hashes and a List<String> of their concrete implementations in a Map<String, List<String>> -> we iterate over the list of strings, we check if the map contains the hash of the current string, if it does not then we add the hash of the string and an empty List -> we then add the concrete string to the list that belongs to its hash in the map -> when we are done iterating over the list of strings we have a hashmap of hashes and the list of strings that match -> iterate over the map and add the values to a List<List<String>> result -> return result
| String    | Palindromic Substring                     |
| String    | Encode and Decode String                  |

## Tags
#interview #datastructures #algorithms

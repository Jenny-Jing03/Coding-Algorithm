# Graph

> deges + vertices

> directed /  undireted

> cyclic / acyclic (this only consider in directed graph)

> connected / disconnected

#### modeling
define and build the vertex and edge

*efficiently finding neighbors*

# Breath First Search BFS1

traversal with **level order**

use queue

# Best First Search BFS1

smallest k-conbination
deduplicated during expand
each elements has different priority

# Depth First Search DFS

use in finding **all solution** / **exist a solution**

*backtracking is a behavior of DFS*

**when return to parent node, restore to original status before when to another branch**

use recursion tree / case / number of level
> what store on each level
>
> how many different states in each level

TC = O(number of branch ^ number of level)

SC = O(height)

Combination

    do not have  order
    add / not add

permutaion

    have order   
    must add


# Topological Sort
**nodes have prerequests**

start from 0 as send node Queue

expansion
    adjust neighbors indegress

*if result size is **not equal to** the number of vertex, there must be a cycle in the directed graph*
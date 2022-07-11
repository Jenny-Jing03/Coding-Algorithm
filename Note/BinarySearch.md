# Binary Search
serch space reduce overtime

eliminate the impossible answer and leave the possible answer -> to find left / right = mid / mit + 1 / mid - 1

# Binary Tree
pre-order: root -> left -> right
in-order: left -> root -> right
post-order: left -> right -> root

balance 

    abs(leftHeight - rightHeight) < 1

complete binary tree

    except the last leve, nodes in each level have two children
    in the last level, all the nodes are stay in left

# Binary Search Tree
left value < root value < right value

depth: root is smallest (0 / 1)
height: root is largest, leaf is 1

## Path

straight up and down / herringbone

return straight up and down

uodate globalMax if necessary

must turn around

    leaf to leaf

might turn aroud

    any to any

must not turn around

    root to leaf / any leaf
    root to leaf (any to any)

### Serialization

tree -> other data structure

record the children reference before delete the children

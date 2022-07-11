# Lowest Common Ancestor

Give two node in a binary tree and find  their lowest common ancestor

#### Clarification
Two nodes might in different binary tree

Two nodes can be null

            a
        /       \
       b        c
     /   \     /  
    d    e    f

Target: b and c
result: a

input: root of binary tree, treenode a, treenode b

output: the lowest common ancestor

#### General Idea
We want to ge the lowest common ansestor from left and right subtree.

We want to return the lowest common ansestor in current level. 

In each level, we want to find the lowest common ansestor.

base case: if current node is null or is target

recursion rule: 

Get the lowest common ansestor of left and right subtree. 

If only one of the lowest common ansestor of the subtree is not null, return the lowest common ansestor of the not null subtree. 

If the lowest common ansestor of two subtrees are null, return null, which mean did not find the common ansestor in curren status. 

If both left and right subtree are not null, which means found one target in left and another in right. Return current node.



## Code

```java
public class Solution{
    class TreeNode{
        int key;
        TreeNode left; 
        TreeNode right;
        public TreeNode(int key){
            this.key = key;
        }
    }

    public TreeNode lca(TreeNode root, TreeNode a, TreeNode b){
        // base case
        if(root == null || root == a || root == b) return root;

        // find LCA in left and right subtree
        TreeNode left = lca(root.left, a, b);
        TreeNode right = lca(root.right, a, b);

        if(left == null) return right;
        if(right == null) return left; // left != null
        return root;// left != null && right != null
    }

}
```

TC = O(n)

SC = O(n)
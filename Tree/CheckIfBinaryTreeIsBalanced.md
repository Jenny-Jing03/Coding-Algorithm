# Check if Binary Tree is Balanced

Give a binary tree. Check whether this tree is balanced

## Clarification
    given tree can be null -> if null, the tree is balanced

## General Idea
In each level, get the hight of left and right subtree. If difference of left and right subtree hight is larger than 1, this tree is unbalanced. 

if previous level is not balance, we do not need to find the height of current level. 

input: TreeNode root
outbut: true if the tree is balanced; else, return false

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

    public boolean isBalanced(TreeNode root){
        // corner case
        if(root == null) return true;

        int height = getHeight(root);
        if(height == -1) return false;
        return true;
    }

    private int getHeight(TreeNode root){
        // base case
        if(root == null) return 0;

        int left = getHeight(root.left);
        if(left == -1){ // if left subtree is not balanced
            return -1;
        }

        int right = getHeight(root.right);
        if(right == -1){ // if right subtree is not balanced
            return -1;
        }

        // if in current status, both left and right subtree are balanced
        if(Math.abs(left - right) > 1){ // is not balanced in current level
            return -1;
        }
        return Math.max(left, right) + 1;
    }
}

```

TC = O(n)

SC = O(n)
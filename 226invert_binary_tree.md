# 226.Invert Binary Tree

**Problem：**

Invert a binary tree.

         4
       /   \
      2     7
     / \   / \
    1   3 6   9

to

         4
       /   \
      7     2
     / \   / \
    9   6 3   1


**My Solutions:**

Date: March 16, 2016

    class Solution {
    public:
        TreeNode* invertTree(TreeNode* root) {
            if(root == NULL) return NULL;
            TreeNode *temp = root->left;
            root->left = invertTree(root->right);
            root->right = invertTree(temp);
            return root;
        }
    };

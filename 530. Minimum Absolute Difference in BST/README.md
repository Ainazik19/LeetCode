#### 530. Minimum Absolute Difference in BST
````
Given the root of a Binary Search Tree (BST), return the minimum absolute difference between the values of any two different nodes in the tree.
````
#### Example 1:
````
Input: root = [4,2,6,1,3]
Output: 1
````
#### Example 2:
````
Input: root = [1,0,48,null,null,12,49]
Output: 1
````
#### Constraints:
````
The number of nodes in the tree is in the range [2, 104].
0 <= Node.val <= 105
````
#### Solution
````
class Solution {
public: 
    int mindiff=INT_MAX;
    TreeNode* p=NULL;
    
    int getMinimumDifference(TreeNode* root) {
       inOrder(root);
        return mindiff;
    }
    
    void inOrder(TreeNode*root){
        if(root==NULL)
            return ;
        inOrder(root->left);
        if(p!=NULL)
            if(root->val-p->val<mindiff)
                mindiff=root->val-p->val;
        p=root;
        inOrder(root->right);
    }
};
````

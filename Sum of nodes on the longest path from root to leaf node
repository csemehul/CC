class Solution {
private:
    int maxLength = 0;
    int maxSum = 0;

    void dfs(Node* node, int depth, int currentSum) {
        if (node == nullptr) return;
        
        currentSum += node->data;
        
        if (node->left == nullptr && node->right == nullptr) { 
            if (depth > maxLength) {
                maxLength = depth;
                maxSum = currentSum;
            } else if (depth == maxLength && currentSum > maxSum) {
                maxSum = currentSum;
            }
        }
        dfs(node->left, depth + 1, currentSum);
        dfs(node->right, depth + 1, currentSum);
    }

public:
    int sumOfLongRootToLeafPath(Node* root) {
        if (root == nullptr) return 0;
        
        dfs(root, 1, 0);
        
        return maxSum;
    }
};

# T
 Jul 20 — LC 515 — Find Largest Value in Each Tree Row
class Solution {
public:
     vector<int>ans;

    void bfs(TreeNode* root){

        if(!root){
            return;
        }
        
        queue<TreeNode*>q;
        q.push(root);
        

        while(!q.empty()){
            
            int largest = INT_MIN;
            int n = q.size();

            for(int i=0;i<n; i++){

                TreeNode* node = q.front();
                largest = max(node->val,largest);

                q.pop();


                if(node->left){
                    q.push(node->left);
                }
                if(node->right){
                    q.push(node->right);
                }
            }
            ans.push_back(largest);

        }
    }

    vector<int> largestValues(TreeNode* root) {
        bfs(root);
        return ans;
    }
};


    class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> v1;
        bool found = false;
        for(int i=0;i<(nums.size());i++){
            for(int j=0;j<(nums.size());j++){
                if(i==j){
                    continue;
                }
                if(nums[i] + nums[j] == target){
                    v1.push_back(i);
                    v1.push_back(j);
                    found=true;
                    break;
                }
            }
            if(found){
                break;
            }
        }
        return v1;
    }
};

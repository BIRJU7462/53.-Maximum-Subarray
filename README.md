# 53.-Maximum-Subarray


class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxi = INT_MIN;
        int size = nums.size();
        if(size == 1 && nums[0] == -1)
        {
            return -1;
        }
        else
        {
            int count = 0;
        for(int i = 0; i < size; i++)
        {
            if(nums[i] < 0)
            {
                count++;
            }
            maxi = max(maxi,nums[i]);
        }
        if(count == size)
        {
            return maxi;
        }

        }
        int current_sum = 0;
         
        for(int i = 0; i < size; i++)
        {
            current_sum = current_sum + nums[i];
            if(current_sum < 0)
            {
                current_sum = 0;
            }
            maxi = max(maxi, current_sum);
        }
        
        if(maxi < 0)
        {
            return -1;
        }
        return maxi;
    }
};

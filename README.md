# Best-Time-to-Buy-and-Sell-Stock

Best Time to Buy and Sell Stock

class Solution {
public:
    int maxProfit(vector<int>& prices) {
        if(prices.size()==0)
        {
            return 0;
        }
        int*arr=new int[prices.size()];
        arr[0]=prices[0];
        for(int i=1;i<prices.size();i++)
        {
            arr[i]= min(prices[i],arr[i-1]);
        }
        
        int ans=0;
        for(int i=0;i<prices.size();i++)
        {
            ans=max(ans,prices[i]-arr[i]);
        }
        return ans;
        
    }
};


 # 119. Pascal's Triangle II

Givenss an integer rowIndex, return the rowIndexth (0-indexed) row of the Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:

#### Example 1:

Input: rowIndex = 3
Output: [1,3,3,1]

#### Example 2:
Input: rowIndex = 0
Output: [1]

#### Example 3:
Input: rowIndex = 1
Output: [1,1]
 ````
Constraints:

0 <= rowIndex <= 33

#### Solution in C++

class Solution {
public:
    vector<int> getRow(int rowIndex) {
        vector<vector<int>> res;
        vector<int>v1,temp;
        v1.push_back(1);
        res.push_back(v1);
        if(rowIndex==0)
            return res[rowIndex];
        for(int i=1;i<=rowIndex;i++){
             temp.push_back(1);
            for(int j=v1.size()-1;j>=1;j--){
                int t=v1.back();
                v1.pop_back();
                temp.push_back(t+v1.back());
            }
             temp.push_back(1);
            res.push_back(temp);
            v1=temp;
            temp.clear();
        }
        return res[rowIndex];
    }  
};
````

# Problem Description
````
You are given an integer array score of size n, where score[i] is the score of the ith athlete in a competition. All the scores are guaranteed to be unique.

The athletes are placed based on their scores, where the 1st place athlete has the highest score, the 2nd place athlete has the 2nd highest score, and so on. The placement of each athlete determines their rank:

The 1st place athlete's rank is "Gold Medal".
The 2nd place athlete's rank is "Silver Medal".
The 3rd place athlete's rank is "Bronze Medal".
For the 4th place to the nth place athlete, their rank is their placement number (i.e., the xth place athlete's rank is "x").
Return an array answer of size n where answer[i] is the rank of the ith athlete.
````
 

#### Example 1:
````
Input: score = [5,4,3,2,1]
Output: ["Gold Medal","Silver Medal","Bronze Medal","4","5"]
Explanation: The placements are [1st, 2nd, 3rd, 4th, 5th].
````
#### Example 2:
````
Input: score = [10,3,8,9,4]
Output: ["Gold Medal","5","Bronze Medal","Silver Medal","4"]
Explanation: The placements are [1st, 5th, 3rd, 2nd, 4th].
````
 

#### Constraints:
````
n == score.length
1 <= n <= 104
0 <= score[i] <= 106
All the values in score are unique.
````
#### Solution 1
````
class Solution {
public:
    vector<string> findRelativeRanks(vector<int>& score) {
        map<int,int>m;
        vector<string>str;
        string c;
        int n=score.size();
        for(int i=0;i<score.size();i++)
            m[score[i]]=0;
        for(auto i=m.begin();i!=m.end();i++)
                i->second=n--;
        for(auto i=0;i<score.size();i++){
            if(m[score[i]]==1)
                c="Gold Medal";
            else if(m[score[i]]==2)
                c="Silver Medal";
            else if(m[score[i]]==3)
                c="Bronze Medal";
            else
                c=to_string(m[score[i]]);
            str.push_back(c);
        }
        
        return str;
    }
};
````
#### Solution 2
````
class Solution {
public:
    vector<string> findRelativeRanks(vector<int>& score) { 
        vector<string>answer;
        vector<int>p;
        vector<int>r;
        p=score;
        
        sort(p.begin(),p.end(),greater<int>());
        for(int i=0;i<score.size();i++){
            for(int j=0;j<p.size();j++){
                if(score[i]==p[j])
                    r.push_back(j+1);
            }
        }
        for(int i=0;i<r.size();i++){
            if(r[i]==1)
                answer.push_back("Gold Medal");
            else if(r[i]==2)
                answer.push_back("Silver Medal");
            else if(r[i]==3)
                answer.push_back("Bronze Medal");
            else{
                string str=to_string(r[i]);
                answer.push_back(str);
            }
        }
        
        return answer;
    }
};
````
      

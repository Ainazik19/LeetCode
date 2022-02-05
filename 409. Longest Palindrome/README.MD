#### problem Description 
````
Given a string s which consists of lowercase or uppercase letters, return the length of the longest palindrome that can be built with those letters.

Letters are case sensitive, for example, "Aa" is not considered a palindrome here.
````
Example 1:
````
Input: s = "abccccdd"
Output: 7
Explanation:
One longest palindrome that can be built is "dccaccd", whose length is 7.
````
Example 2:
````
Input: s = "a"
Output: 1
````
Example 3:
````
Input: s = "bb"
Output: 2
 ````
Constraints:
````
1 <= s.length <= 2000
s consists of lowercase and/or uppercase English letters only.
````
#### Solution
````
class Solution {
public:
    int longestPalindrome(string s) {
        unordered_map<char,int>mp;
        int count=0;
        for(int i=0;i<s.length();i++)
            mp[s[i]]++;
        
        for(auto i:mp){
            if(i.second % 2 != 0)
                count++;
        }
        if(count != 0)
            return s.length()-count+1;
        else
            return s.length();
    }
};

````

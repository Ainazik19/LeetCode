# 345. Reverse Vowels of a String
````
Given a string s, reverse only all the vowels in the string and return it.

The vowels are 'a', 'e', 'i', 'o', and 'u', and they can appear in both cases.

 ````

#### Example 1:

Input: s = "hello"
Output: "holle"

#### Example 2:

Input: s = "leetcode"
Output: "leotcede"
 

Constraints:

1 <= s.length <= 3 * 105
s consist of printable ASCII characters.
````
class Solution {
public:
    string reverseVowels(string s) {
        vector<char>v;
        char c;
        for(int i=0;i<s.size();i++){
            if (s[i]=='a'||s[i]=='o'||s[i]=='e'||s[i]=='i'||s[i]=='u'||s[i]=='A'||s[i]=='O'||s[i]=='I'||s[i]=='U'||s[i]=='E'){
                v.push_back(s[i]);
                
            }
        }
        for(int i=0;i<s.size();i++){
            if(s[i]=='a'|| s[i]=='i'||s[i]=='o'||s[i]=='e'||s[i]=='u'||s[i]=='A'||s[i]=='O'||s[i]=='U'||s[i]=='E'||s[i]=='I'){
                s[i]=v.back();
                v.pop_back();
            }
        }
        return s;
    }
};
````

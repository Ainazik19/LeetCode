# 557. Reverse Words in a String III

####  Given a string s, reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

 
#### Example 1:
````

Input: s = "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"
````
#### Example 2:
````
Input: s = "God Ding"
Output: "doG gniD"

````

````
Constraints:

1 <= s.length <= 5 * 104
s contains printable ASCII characters.
s does not contain any leading or trailing spaces.
There is at least one word in s.
All the words in s are separated by a single space.

````
#### Solution 
````
class Solution {
public:
    string reverseWords(string s) {
        int r=0;
        int i=0;
        while(i<s.length()){
            while(r<s.length() && s[r]!=' '){
                r++;
            }
            reverse(s.begin()+i,s.begin()+r);
            i=r+1;
            r=i;
        }
        return s;
    }
};
````

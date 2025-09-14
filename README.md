# Leetcode-383.-Ransom-Note
# Description
Given two strings ransomNote and magazine, return true if ransomNote can be constructed by using the letters from magazine and false otherwise.

Each letter in magazine can only be used once in ransomNote.
# Solution
In the given problem we have been given 2 strings ransomNote and magazine , we need to check whether the string in ransomNote can be constructed using the strings and letter in magazine . Also we can use only 1 letter from magazine to form ransomNote.

This can be done by counting the number of each letter in ransomNote as well as in magazine and checking whether each letter in in magazine has a frequency of words greater or equal to that of ransomNote.If it fails this condition then return False , else return True.

Example 1:

Input: ransomNote = "a", magazine = "b"

Output: false

Example 2:

Input: ransomNote = "aa", magazine = "ab"

Output: false

Example 3:

Input: ransomNote = "aa", magazine = "aab"

Output: true
# Algorithm
1. Count the number of letters in each string magazine and ransomNote , in python this operation can be done using the Counter function .
2. Now loop through each character and its corresponding frequency in ransomNote .
3. If the count in ransomNote for a letter is greater than that of the same letter in magazine return False
4. Else return True.
# Code
from collections import Counter
class Solution:

    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        ransomnote_count=Counter(ransomNote)
        magazine_count=Counter(magazine)
        for char,count in ransomnote_count.items():
            if magazine_count[char]<count:
                return False
            return True
# Complexity

Time Complexity: 

O(m + n) → counting characters in ransomNote (m) and magazine (n), plus checking characters.

Space Complexity: 

O(m + n) → storing counts in two hash maps.

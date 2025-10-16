# 2598-smallest-missing-non-negative-integer-after-operations
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int findSmallestInteger(vector<int>& nums, int value) {
        int n = nums.size();
        unordered_map<int, int> freq;

        for (int x : nums) {
            int r = ((x % value) + value) % value;
            freq[r]++;
        }

        int i = 0;
        while (true) {
            int r = i % value;
            if (freq[r] == 0) return i;
            freq[r]--;
            i++;
        }
    }
};

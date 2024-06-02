# LEETCODE-Strings-344
Sure, let's walk through a dry run of the `reverseString` method from the `Solution` class. This method reverses a string represented as a vector of characters in-place.

### Code Explanation

```cpp
class Solution {
 public:
  void reverseString(vector<char>& s) {
    int l = 0;  // Initialize left pointer
    int r = s.size() - 1;  // Initialize right pointer

    while (l < r)  // Continue until the two pointers meet
      swap(s[l++], s[r--]);  // Swap elements at the left and right pointers and then move the pointers towards each other
  }
};
```

### Dry Run

Let's consider an example where the input vector `s` is `['h', 'e', 'l', 'l', 'o']`.

1. **Initialization**:
   - `l = 0`
   - `r = 4` (since `s.size() - 1` is 4)

2. **First Iteration**:
   - Before swap: `s = ['h', 'e', 'l', 'l', 'o']`
   - Swap elements at indices `l` and `r`: swap(`s[0]`, `s[4]`)
     - After swap: `s = ['o', 'e', 'l', 'l', 'h']`
   - Increment `l` to 1 (`l++`)
   - Decrement `r` to 3 (`r--`)

3. **Second Iteration**:
   - Before swap: `s = ['o', 'e', 'l', 'l', 'h']`
   - Swap elements at indices `l` and `r`: swap(`s[1]`, `s[3]`)
     - After swap: `s = ['o', 'l', 'l', 'e', 'h']`
   - Increment `l` to 2 (`l++`)
   - Decrement `r` to 2 (`r--`)

4. **Termination Condition**:
   - Now `l` is equal to `r` (both are 2), so the `while` loop terminates.

The final reversed vector is `['o', 'l', 'l', 'e', 'h']`.

### Summary of Steps:
1. Swap `h` and `o` resulting in `['o', 'e', 'l', 'l', 'h']`.
2. Swap `e` and `l` resulting in `['o', 'l', 'l', 'e', 'h']`.
3. `l` meets `r`, so the process stops.

The function works by using two pointers, starting from the ends of the vector, and swaps elements until the pointers meet in the middle. This approach ensures that the string is reversed in-place with a time complexity of \(O(n)\) where \(n\) is the number of elements in the vector.

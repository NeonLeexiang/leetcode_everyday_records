# leetcode-everyday-records

准备每天没事刷刷 `leetcode` 并用这个 `markdown` 文档做个简单记录

[comment]: <> (-------------------------------------------------------------)
## easy

### 2021-06-03 Thursday

#### 1365. How Many Numbers Are Smaller Than the Current Number

`c++`:

```
class Solution {
public:
    vector<int> smallerNumbersThanCurrent(vector<int>& nums) {
        vector<int> res;
        for (int i = 0; i < nums.size(); i++)
            res.push_back(compare_nums(nums, nums[i]));
        return res;
    }
    
    int compare_nums(vector<int>& nums, int temp) {
        int res = 0;
        for (int i = 0; i < nums.size(); i++)
            if (nums[i] < temp)
                res++;
        return res;
    }
};
```

`python`:

```python
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:
        res = []
        for c in nums:
            res.append(len([1 for i in nums if i < c]))
        return res
```

#### 1342. Number of Steps to Reduce a Number to Zero

`python`:

```python
class Solution:
    def numberOfSteps(self, num: int) -> int:
        res = 0
        while num != 0:
            num = num // 2 if num % 2 == 0 else num - 1
            res += 1
        return res
```

`c++`:
```
class Solution {
public:
    int numberOfSteps(int num) {
        int res = 0;
        while (num != 0) {
            num = (num % 2 == 0)? (num / 2) :( num-1);
            res++;
        }
        return res;
    }
};
```
* special solvement:
  
        Count each 0 as 1.
        Count each 1 as 2 except the first 1.
        Time: O(bits of num)
        Space: O(bits of num)
        However num is bounded in 0 <= num <= 10^6, so time and space are both O(1) in this problem.

```python
class Solution:
    def numberOfSteps (self, num: int) -> int:
        digits = f'{num:b}'
        return digits.count('1') - 1 + len(digits)
```
`O(1) space`:
```python
class Solution:
    def numberOfSteps (self, num: int) -> int:
        steps = num == 0
        while num > 0:
            steps += 1 + (num & 1)
            num >>= 1
        return steps - 1
```


#### 1281. Subtract the Product and Sum of Digits of an Integer

`python`:
```python
class Solution:
    def subtractProductAndSum(self, n: int) -> int:
        str_n = str(n)
        product = 1
        sums = 0
        for c in str_n:
            product *= int(c)
            sums += int(c)
        return product - sums
```

[comment]: <> (-------------------------------------------------------------)
## medium


[comment]: <> (-------------------------------------------------------------)
## hard

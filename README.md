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



[comment]: <> (-------------------------------------------------------------)
## medium


[comment]: <> (-------------------------------------------------------------)
## hard

### 思路
遍历数组元素nums[i]，如果哈希表中不存在target - nums[i]，则将当前元素插入哈希表，直到匹配到才返回。
### 代码
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> hashtable = new HashMap<>();
        for(int i = 0; i < nums.length; i++){
            if (hashtable.containsKey(target - nums[i])){
                return new int[]{i, hashtable.get(target - nums[i])};
            }
            hashtable.put(nums[i], i);
        }
        return new int [0];
    }
}
```
**复杂度分析**
- 时间复杂度：O(n)，遍历一次数组。
- 空间复杂度：O(n)，哈希表的开销。

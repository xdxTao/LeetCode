## 题目位置

[https://leetcode-cn.com/problems/he-wei-sde-liang-ge-shu-zi-lcof/](https://leetcode-cn.com/problems/he-wei-sde-liang-ge-shu-zi-lcof/)

<br/>

## 题解

```java

    /**
     * 使用set
     *
     * @author 小道仙
     * @date 2020/9/4
     */
    public int[] twoSum(int[] nums, int target) {
        int[] arr = new int[2];
        Set<Integer> set = new HashSet<>();
        for (int i = 0;i < nums.length; i++){
            set.add(nums[i]);
        }
        for (int i = 0;i < nums.length; i++){
            if (set.contains(target - nums[i])){
                arr[0] = nums[i];
                arr[1] = target - nums[i];
                break;
            }
        }
        return arr;
    }

```
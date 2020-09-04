## 题目位置

[https://leetcode-cn.com/problems/shu-zu-zhong-chu-xian-ci-shu-chao-guo-yi-ban-de-shu-zi-lcof/](https://leetcode-cn.com/problems/shu-zu-zhong-chu-xian-ci-shu-chao-guo-yi-ban-de-shu-zi-lcof/)

<br/>

## 题解


```java

    /**
     * 思路一：
     *  1、使用 map 存储每一个数字出现的次数，然后找到最大的
     *
     *
     * @author 小道仙
     * @date 2020/9/4
     */
    public int majorityElement(int[] nums) {
        int max = 0;
        int key = -1;
        Map<Integer,Integer> map = new HashMap<>();
        for (int i = 0;i < nums.length; i++){
            if (map.containsKey(nums[i])){
                map.put(nums[i], map.get(nums[i]) + 1);
            }else {
                map.put(nums[i], 1);
            }
            if (map.get(nums[i]) > max){
                max = map.get(nums[i]);
                key = nums[i];
            }
        }
        return key;
    }

    /**
     * 思路二：
     *  1、数组中有一个数字出现的次数超过数组长度的一半   说明在这个数字在中间
     */
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        return nums[nums.length / 2];
    }


```
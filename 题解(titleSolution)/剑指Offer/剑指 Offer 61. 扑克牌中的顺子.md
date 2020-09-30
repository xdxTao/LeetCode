## 题目位置

[https://leetcode-cn.com/problems/bu-ke-pai-zhong-de-shun-zi-lcof/](https://leetcode-cn.com/problems/bu-ke-pai-zhong-de-shun-zi-lcof/)

<br/>

## 题解


```java

    /**
     * 思路
     *  1、判断0的个数和相邻两个数组之间的差值
     *  2、需要注意的是，如果数组中存在相同的数，就直接返回false（0除外）
     *
     * @author 小道仙
     * @date 2020年9月30日
     */
    public boolean isStraight(int[] nums) {
        int zeroCount = 0;
        int length = 0;
        Arrays.sort(nums);
        List<Integer> list = new ArrayList<>();
        for (int i = 0;i < nums.length; i++){
            if (nums[i] == 0){
                zeroCount ++;
            }else {
                list.add(nums[i]);
            }
        }
        for (int i = 1;i < list.size(); i++){
            if (list.get(i) - list.get(i-1) > 1){
                length += list.get(i) - list.get(i-1) - 1;
            }
            if (list.get(i) - list.get(i-1) == 0){
                return false;
            }
        }
        return length > zeroCount ? false : true;
    }

```
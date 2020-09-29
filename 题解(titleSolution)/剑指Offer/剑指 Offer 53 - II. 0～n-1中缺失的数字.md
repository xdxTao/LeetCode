## 题目位置

[https://leetcode-cn.com/problems/que-shi-de-shu-zi-lcof/](https://leetcode-cn.com/problems/que-shi-de-shu-zi-lcof/)

<br/>

## 题解

```java

    /**
     * 思路：双指针法 0ms执行
     *  1、分别从前后开始判断
     *
     * @author 小道仙
     * @date 2020年9月29日
     */
    public int missingNumber(int[] nums) {
        if (nums.length == 0){
            return 0;
        }
        int i = 0,j = nums.length-1;
        while (i <= j){
            if (nums[i] != i){
                return i;
            }
            if (nums[j] != j+1){
                return j+1;
            }
            i ++;
            j --;
        }
        return i;
    }

```
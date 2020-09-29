## 题目位置

[https://leetcode-cn.com/problems/hua-dong-chuang-kou-de-zui-da-zhi-lcof/](https://leetcode-cn.com/problems/hua-dong-chuang-kou-de-zui-da-zhi-lcof/)

<br/>

## 题解

```java

    /**
     * 思路
     *  1、先找到，我们最后一共有【nums.length-k+1】个元素，可以把结果数组new出来
     *  2、然后一个个移动，找到每一个子数组的最大值
     *
     * @author 小道仙
     * @date 2020年9月29日
     */
    public int[] maxSlidingWindow(int[] nums, int k) {
        if (nums.length == 0){
            return nums;
        }
        int[] result = new int[nums.length-k+1];
        int cur = 0;
        for (int i = 0;i+k <= nums.length; i++){
            result[cur++] = fun(nums,i,i+k);
        }
        return result;
    }

    private int fun(int[] arr, int start,int end){
        int max = Integer.MIN_VALUE;
        for (int i = start; i < end; i++){
            if (arr[i] > max){
                max = arr[i];
            }
        }
        return max;
    }

```
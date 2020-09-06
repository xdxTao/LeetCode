## 题目位置

[https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/](https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/)

<br/>

B站视频地址：[https://www.bilibili.com/video/BV1rT4y1w7vs](https://www.bilibili.com/video/BV1rT4y1w7vs)

## 题解


```java

    /**
     * 思路
     *  双指针法，前后同时进行
     *
     * @author 小道仙
     * @date 2002/9/5
     */
    public int[] exchange(int[] nums) {
        int start = 0;
        int end = nums.length-1;
        int tmp;
        while (start < end){
            if (nums[start] % 2 == 0){
                tmp = nums[start];
                nums[start] = nums[end];
                nums[end] = tmp;
                end --;
            }else {
                start ++;
            }

            if (nums[end] % 2 != 0){
                tmp = nums[end];
                nums[end] = nums[start];
                nums[start] = tmp;
                start ++;
            }else {
                end --;
            }
        }
        return nums;
    }

```
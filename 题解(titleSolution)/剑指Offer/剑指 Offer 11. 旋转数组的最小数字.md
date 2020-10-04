## 题目位置

[https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/](https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/)

<br/>

## 题解


```java

    /**
     * 思路
     *  1、找到数组中元素最小的元素
     *  2、因为数组是递增的，所以 numbers[i] > numbers[i+1] i+1 就是最小的
     *
     * @author 小道仙
     * @date 2020年10月4日
     */
    public int minArray(int[] numbers) {
        for(int i = 0;i < numbers.length-1; i++){
            if (numbers[i] > numbers[i+1]){
                return numbers[i+1];
            }
        }
        return numbers[0];
    }

```
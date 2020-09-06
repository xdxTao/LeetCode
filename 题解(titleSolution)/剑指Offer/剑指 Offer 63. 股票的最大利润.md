## 题目位置

[https://leetcode-cn.com/problems/gu-piao-de-zui-da-li-run-lcof/](https://leetcode-cn.com/problems/gu-piao-de-zui-da-li-run-lcof/)

<br/>

## 题解

```java

    /**
     * 思路
     *   1、计算每一天收入的最大值，然后返回这个最大值
     *   2、每天的最大值计算 = 今天的 - 之前的最小值
     *
     * @author 小道仙
     * @date 2020/9/6
     */

    public int maxProfit(int[] prices) {
        if (prices.length == 0){
            return 0;
        }
        int min = prices[0];
        int maxMoney = 0;
        for (int i = 1;i < prices.length; i++){
            if (prices[i] - min > maxMoney){
                maxMoney = prices[i] - min;
            }
            if (prices[i] < min){
                min = prices[i];
            }
        }
        return maxMoney;
    }


```
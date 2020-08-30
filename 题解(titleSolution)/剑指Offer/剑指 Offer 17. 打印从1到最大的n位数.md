## 题目位置

[https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/](https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/)

<br/>

## 题解


```java

    /**
     * 思路：
     *
     * @author 小道仙
     * @date 2020/8/30
     */
    public int[] printNumbers(int n) {
        if(n <= 0){
            return new int[0];
        }
        StringBuilder tmp = new StringBuilder();
        for (int i = 1; i <= n; i++){
            tmp.append(9);
        }
        int max = Integer.parseInt(tmp.toString());
        int[] arr = new int[max];
        for (int i = 0;i < max; i++){
            arr[i] = i+1;
        }
        return arr;
    }

```
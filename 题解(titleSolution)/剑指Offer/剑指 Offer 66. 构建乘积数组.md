## 题目位置

[https://leetcode-cn.com/problems/gou-jian-cheng-ji-shu-zu-lcof/](https://leetcode-cn.com/problems/gou-jian-cheng-ji-shu-zu-lcof/)

<br/>

## 题解

```java

    /**
     * 思路
     *  1、判断0出现的次数
     */
    public int[] constructArr(int[] a) {
        int count = 0;
        int[] b = new int[a.length];
        long max = 1;
        for (int i = 0; i < a.length; i++){
            if (a[i] != 0){
                max *= a[i];
            }else{
                count ++;
            }
        }
        if (count > 1){
            for (int i = 0;i < a.length; i++){
                b[i] = 0;
            }
        }else if (count == 1){
            for (int i = 0;i < a.length; i++){
                if (a[i] != 0){
                    b[i] = 0;
                }else {
                    b[i] = (int) max;
                }
            }
        }else{
            for (int i = 0;i < a.length; i++){
                b[i] = (int) max / a[i];
            }
        }
        return b;
    }

```
## 题目位置

[https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/](https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/)

<br/>

## 题解

```java

    /**
     * 思路
     *  1、前后左右走起来
     *
     * @author 小道仙
     * @date 2020年9月30日
     */
    public int[] spiralOrder(int[][] matrix) {
        if (matrix.length == 0 || matrix[0].length == 0){
            return new int[0];
        }
        int[] result = new int[matrix.length*matrix[0].length];
        int cur = 0;
        char direction = '→';
        int i = 0,j = 0;
        int rowLength = matrix[0].length;
        int cloumLength = matrix.length;
        while (true){
            result[cur++] = matrix[i][j];
            matrix[i][j] = Integer.MIN_VALUE;
            if (direction == '→'){
                if (j+1 < rowLength && matrix[i][j+1] != Integer.MIN_VALUE){
                    j ++;
                }else {
                    direction = '↓';
                    i ++;
                }
            } else if (direction == '↓'){
                if (i+1 < cloumLength && matrix[i+1][j] != Integer.MIN_VALUE){
                    i ++;
                }else{
                    direction = '←';
                    j --;
                }
            } else if (direction == '←'){
                if (j - 1 >= 0 && matrix[i][j-1] != Integer.MIN_VALUE){
                    j --;
                }else {
                    direction = '↑';
                    i --;
                }
            } else if (direction == '↑'){
                if (i - 1 >= 0 && matrix[i-1][j] != Integer.MIN_VALUE){
                    i --;
                }else {
                    direction = '→';
                    j++;
                }
            }
            if (cur == result.length){
                break;
            }
        }
        return result;
    }


```
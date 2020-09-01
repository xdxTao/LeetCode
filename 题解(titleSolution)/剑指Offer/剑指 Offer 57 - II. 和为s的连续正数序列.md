## 题目位置

[https://leetcode-cn.com/problems/he-wei-sde-lian-xu-zheng-shu-xu-lie-lcof/](https://leetcode-cn.com/problems/he-wei-sde-lian-xu-zheng-shu-xu-lie-lcof/)

<br/>

## 题解

```java
    /**
     * 暴力解法
     * 
     * 
     * @return
     */
    public int[][] findContinuousSequence(int target) {
        List<int[]> tmp = new ArrayList<>();
 
        for (int i = 1;i <= target / 2; i++){
            int[] fun = fun(i, target);
            if (fun != null){
                tmp.add(fun);
               
            }
        }
        int[][] arr = new int[tmp.size()][];
        for (int i = 0;i < tmp.size(); i++){
            arr[i] = tmp.get(i);
        }
        return arr;
    }

    public int[] fun(int start,int end){
        List<Integer> result = new ArrayList<>();
        int sum = 0;
        for (int i = start;i < end; i++){
            result.add(i);
            sum += i;
            if (sum == end){
                int[] arr = new int[result.size()];
                for (int j = 0;j < result.size();j++){
                    arr[j] = result.get(j);
                }
                return arr;
            }
            if (sum > end){
                return null;
            }
        }
        return null;
    }
```
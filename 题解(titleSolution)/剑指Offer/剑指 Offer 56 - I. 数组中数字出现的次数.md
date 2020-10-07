## 题目位置

[https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-lcof/](https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-lcof/)

<br/>

## 题解


```java

    /**
     * 思路：
     *  1、使用集合进行遍历
     *  
     * @author 小道仙
     * @date 2020年10月7日
     */
    public int[] singleNumbers(int[] nums) {
        List<Integer> set = new ArrayList<>();

        for (int i = 0;i < nums.length; i++){
            if (set.contains(nums[i])){
                set.remove((Object)nums[i]);
            }else {
                set.add(nums[i]);
            }
        }
        int[] arr = new int[2];
        int cur = 0;
        for (Integer item : set){
            arr[cur ++] = item;
        }
        return arr;
    }


```
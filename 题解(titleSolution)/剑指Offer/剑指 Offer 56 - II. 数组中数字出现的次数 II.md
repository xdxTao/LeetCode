## 题目位置

[https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-ii-lcof/](https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-ii-lcof/)

<br/>

## 题解

```java

    /**
     * 存入set，然后....最起码代码好像少点不是吗？
     *
     * @author 小道仙
     * @date 2020/9/2
     */
    public int singleNumber(int[] nums) {
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> set2 = new HashSet<>();
        for (int i = 0;i < nums.length; i++){
            if (!set1.contains(nums[i])){
                set1.add(nums[i]);
            }else {
                set2.add(nums[i]);
            }
        }
        set1.removeAll(set2);
        return (int)set1.toArray()[0];
    }

```
## 题目位置

[https://leetcode-cn.com/problems/zai-pai-xu-shu-zu-zhong-cha-zhao-shu-zi-lcof/](https://leetcode-cn.com/problems/zai-pai-xu-shu-zu-zhong-cha-zhao-shu-zi-lcof/)

<br/>

## 题解


```java

    public int search(int[] nums, int target) {
        int count = 0;
        for (int i = 0;i < nums.length; i++){
            if (target < nums[i]){
                break;
            }
            if (target == nums[i]){
                count ++;
            }
        }
        return count;
    }

```
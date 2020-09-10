## 题目位置

[https://leetcode-cn.com/problems/yuan-quan-zhong-zui-hou-sheng-xia-de-shu-zi-lcof/](https://leetcode-cn.com/problems/yuan-quan-zhong-zui-hou-sheng-xia-de-shu-zi-lcof/)

<br/>

## 题解

```java

    /**
     * 思路：
     *  1、先把数字全部装进List里面去
     *  2、while循环删除List里面的数据，直到只有一个为止
     *  3、每次删除cur位置的元素，注意删除完之后要-1，因为删除之后后面的元素向前移动了一位
     *
     * @author 小道仙
     * @date 2020/9/10
     */
    public int lastRemaining(int n, int m) {
        List<Integer> list = new ArrayList<>();
        for (int i = 0;i < n; i++){
            list.add(i);
        }
        int cur = -1;
        while (list.size() > 1){
            cur += m;
            if (cur >= list.size()){
                cur = cur % list.size();
            }
            list.remove(cur);
            cur --;
        }
        return list.get(0);
    }

```
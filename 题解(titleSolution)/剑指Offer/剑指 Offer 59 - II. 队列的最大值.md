## 题目位置

[https://leetcode-cn.com/problems/dui-lie-de-zui-da-zhi-lcof/](https://leetcode-cn.com/problems/dui-lie-de-zui-da-zhi-lcof/)

<br/>

## 题解


```java

    /**
     * 思路
     *
     * @author 小道仙
     * @date 2020年10月13日
     */
    private List<Integer> list;
    int max = Integer.MIN_VALUE;

    public MaxQueue() {
        list = new ArrayList<>();
    }
    public int max_value() {
        if (list.isEmpty()){
            return -1;
        }
        return max == Integer.MIN_VALUE ? null : max;
    }

    public void push_back(int value) {
        if (value > max){
            max = value;
        }
        list.add(value);
    }

    public int pop_front() {
        if (list.isEmpty()){
            return -1;
        }
        Integer remove = list.remove(0);
        if (remove == max){
            max = Integer.MIN_VALUE;
            for (Integer item : list){
                if (item > max){
                    max = item;
                }
            }
        }
        return remove;
    }


```
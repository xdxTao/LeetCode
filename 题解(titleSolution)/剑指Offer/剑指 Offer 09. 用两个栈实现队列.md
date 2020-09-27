## 题目位置

[https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/](https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/)

<br/>

## 题解


```java

    /**
     * 题解
     * 
     * @author 小道仙
     * @date 2020年9月27日
     */
    private List<Integer> list;
    public CQueue() {
        list = new ArrayList<>();
    }

    public void appendTail(int value) {
        list.add(0,value);
    }

    public int deleteHead() {
        if (list.size() > 0){
            return list.remove(list.size()-1);
        }else{
            return -1;
        }
    }

```
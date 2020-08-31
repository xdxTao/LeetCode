## 题目位置

[https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/](https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/)

<br/>

## 题解


```java

    public int[] reversePrint(ListNode head) {
        List<Integer> tmp = new ArrayList<>();
        while (head != null){
            tmp.add(head.val);
            head = head.next;
        }
        
        int[] arr = new int[tmp.size()];
        int j = 0;
        for (int i = tmp.size() - 1;i >= 0; i--){
            arr[j ++] = tmp.get(i);
        }
        return arr;
    }

```
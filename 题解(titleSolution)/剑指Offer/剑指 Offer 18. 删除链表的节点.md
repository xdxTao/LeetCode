## 题目位置

[https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/](https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/)

<br/>

## 题解


```java

    /**
     * 思路
     *  1、注意删除是第一个元素，最后一个的处理
     *
     * @author 小道仙
     * @date 2020/9/12
     */
    public ListNode deleteNode(ListNode head, int val) {
        ListNode tmpHead = new ListNode(-1);
        tmpHead.next = head;
        ListNode tmp = tmpHead;
        while (head != null){
            if (head.val == val){
                if (head.next == null){
                    tmp.next = null;
                }else{
                    tmp.next = head.next;
                }
                break;
            }
            tmp = head;
            head = head.next;
        }
        return tmpHead.next;
    }

```
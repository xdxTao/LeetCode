## 题目位置

[https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/](https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/)

<br/>


## 题解


```java

    /**
     * 思路：
     *  1、先同时输出链表中的每一个节点
     *  2、在输出剩下的链表节点
     *
     * 注意：
     *  1、要保存好链表头
     *
     * @author 小道仙
     * @date 2020/9/1
     */
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {

        ListNode preHead = new ListNode(-1);
        ListNode head = new ListNode(-1);
        preHead.next = head;

        while (l1 != null && l2 != null){
            if (l1.val < l2.val){
                head.next = new ListNode(l1.val);
                head = head.next;
                l1 = l1.next;
            }else {
                head.next = new ListNode(l2.val);
                head = head.next;
                l2 = l2.next;
            }
        }
        while (l1 != null){
            head.next = new ListNode(l1.val);
            head = head.next;
            l1 = l1.next;
        }

        while (l2 != null){
            head.next = new ListNode(l2.val);
            head = head.next;
            l2 = l2.next;
        }
        return preHead.next.next;
    }

```
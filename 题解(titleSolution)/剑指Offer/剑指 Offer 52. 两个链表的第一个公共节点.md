## 题目位置

[https://leetcode-cn.com/problems/liang-ge-lian-biao-de-di-yi-ge-gong-gong-jie-dian-lcof/](https://leetcode-cn.com/problems/liang-ge-lian-biao-de-di-yi-ge-gong-gong-jie-dian-lcof/)

<br/>

## 题解


```java

    /**
     * 思路
     *  1、双层循环每次去对比一下当前节点是否等于链表B中的节点
     *
     * @author 小道仙
     * @date 2020/9/6
     */
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        ListNode tmp;
        while (headA != null){
            tmp = headB;
            while (tmp != null){
                if (headA == tmp){
                    return headA;
                }
                tmp = tmp.next;
            }
            headA = headA.next;
        }
        return null;
    }

```
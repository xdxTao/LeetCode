## 题目位置

[https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/](https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/)

<br/>

B站视频：[https://www.bilibili.com/video/bv1mT4y1L7Zz](https://www.bilibili.com/video/bv1mT4y1L7Zz)


## 题解


```java
    
    /**
     * 思路：
     *    1、如果head只有0或者1个节点就直接返回
     *    2、我们把链表分成左右两部分
     *    3、现在我们需要三个节点
     *          - left 左边部分的结尾
     *          - right 右边部分的开始
     *          - tmp 当前操作的节点
     *    4、所以我们只需要让  （tmp -> left, left = tmp, tmp = right） 就好了
     *
     * @author 小道仙
     * @date 2020/8/31
     */
    public ListNode reverseList(ListNode head) {
        if (head == null || head.next == null){
            return head;
        }
        ListNode left = head;
        ListNode right = head.next;
        ListNode tmp;
        left.next = null;
        while (right != null){
             tmp = right;
             right = right.next;
             tmp.next = left;
             left = tmp;
        }
        return left;
    }


```
## 题目位置

[https://leetcode-cn.com/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/)

<br/>

## 题解

```java

    /**
     * 思路：
     *  1、我们使用一个中序遍历，把链表回收到集合里面去
     *  2、我们对集合的节点，进行前后指向
     *
     * @author 小道仙
     * @date 2020年9月17日
     */
    List<Node> list = new ArrayList<>();
    public Node treeToDoublyList(Node root) {
        if (root == null){
            return root;
        }
        fun(root);
        Node frontHead = new Node(-1,null,null);
        frontHead.left = list.get(0);
        Node tmp = list.get(0);
        for (int i = 1;i < list.size(); i++){
            Node item = list.get(i);
            tmp.right = item;
            item.left = tmp;
            tmp = list.get(i);
        }
        Node first = list.get(0);
        Node last = list.get(list.size() - 1);
        first.left = last;
        last.right = first;
        return frontHead.left;
    }

    public void fun(Node root) {
        if (root == null){
            return;
        }
        if (root.left != null) fun(root.left);
        list.add(root);
        if (root.right != null) fun(root.right);
    }

```
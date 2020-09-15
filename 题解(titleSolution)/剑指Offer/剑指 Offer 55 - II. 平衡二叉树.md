## 题目位置

[https://leetcode-cn.com/problems/ping-heng-er-cha-shu-lcof/](https://leetcode-cn.com/problems/ping-heng-er-cha-shu-lcof/)

<br/>

## 题解

```java

    /**
     * 本以为这是一个很烂的题解，没想到执行性能打败百分之99的人
     *
     * 思路：
     *  1、递归遍历每一个节点，然后再去递归遍历每一个节点，找到它左右子树的长度，然后进行比较
     *
     * @author 小道仙
     * @date 2020年9月15日
     */
    int flag = 0;
    public boolean isBalanced(TreeNode root) {
        fun(root);
        return flag == 0 ? true : false;
    }

    public void fun(TreeNode root){
        if (root == null || flag == 1){
            return;
        }
        int left,right;
        if (root.left != null){
            fun1(root.left, 1);
            left = max;
        }else{
            left = 0;
        }
        max = 0;
        if (root.right != null){
            fun1(root.right, 1);
            right = max;
        }else{
            right = 0;
        }
        max = 0;
        if (Math.abs(left - right) > 1){
            flag = 1;
        }
        if (root.left != null) fun(root.left);
        if (root.right != null) fun(root.right);

    }
    int max = 0;
    public void fun1(TreeNode root,int count){
        if (count > max){
            max = count;
        }
        if (root == null){
            return;
        }
        if (root.left != null) fun1(root.left,count + 1);
        if (root.right != null) fun1(root.right, count + 1);
    }

```
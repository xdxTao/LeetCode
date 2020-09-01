## 题目位置

[https://leetcode-cn.com/problems/er-cha-shu-de-zui-jin-gong-gong-zu-xian-lcof/](https://leetcode-cn.com/problems/er-cha-shu-de-zui-jin-gong-gong-zu-xian-lcof/)

<br/>

## 题解

```java

    /**
     * 以每一个节点为根节点进行便利，看看能否找到 p、q，返回最后一个条件成立的可能
     *
     * @author 小道仙
     * @date 2020/9/1
     */
    TreeNode result;
    int count = 0;
    int tmp1,tmp2;
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        tmp1 = p.val;
        tmp2 = q.val;
        fun(root);
        return result;
    }

    public void fun(TreeNode root){
        if (root == null){
            return;
        }
        fun2(root);
        if (count == 2){
            count = 0;
            result = root;
        }else {
            count = 0;
            return;
        }

        if (root.left != null) fun(root.left);
        if (root.right != null) fun(root.right);
    }


    public void fun2(TreeNode root){
        if (root == null){
            return;
        }
        if (root.val == tmp1 || root.val == tmp2){
            count += 1;
        }
        if (root.left != null) fun2(root.left);
        if (root.right != null) fun2(root.right);
    }

```
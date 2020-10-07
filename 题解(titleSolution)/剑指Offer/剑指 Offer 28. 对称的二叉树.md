## 题目位置

[https://leetcode-cn.com/problems/dui-cheng-de-er-cha-shu-lcof/](https://leetcode-cn.com/problems/dui-cheng-de-er-cha-shu-lcof/)

<br/>

## 题解

B站视频讲解 [https://www.bilibili.com/video/BV1qD4y1R7Uk](https://www.bilibili.com/video/BV1qD4y1R7Uk)


```java

    /**
     * 思路
     *  1、对左边的节点进行  【根左右】遍历
     *  2、对右边的节点进行  【根左右】遍历
     *  3、然后对比遍历的结果是否一直
     *
     * 注：
     *  1、对于【非叶子】节点，需要对他补全。（也就是左节点没有，就存入null，右节点同理）
     *
     * @author 小道仙
     * @date 2020年10月6日
     */
    public boolean isSymmetric(TreeNode root) {
        StringBuilder left = new StringBuilder();
        StringBuilder right = new StringBuilder();
        if (root != null){
            fun(root.left,left);
            fun2(root.right, right);
        }
        return left.toString().equals(right.toString());
    }

    public void fun(TreeNode root,StringBuilder sb){
        if (root == null){
            return;
        }

        sb.append(root.val);

        if (root.left!=null) fun(root.left,sb);
        if (root.left == null && root.right != null){
            sb.append("null");
        }
        if (root.right!=null) fun(root.right,sb);
        if (root.right == null && root.left != null){
            sb.append("null");
        }
    }

    public void fun2(TreeNode root,StringBuilder sb){
        if (root == null){
            return;
        }
        sb.append(root.val);
        if (root.right!=null) fun2(root.right,sb);
        if (root.right == null && root.left != null){
            sb.append("null");
        }
        if (root.left!=null) fun2(root.left,sb);
        if (root.left == null && root.right != null){
            sb.append("null");
        }
    }

```
## 题目位置

[https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)

<br/>

## 题解


B站视频讲解 [https://www.bilibili.com/video/BV1P54y1v7AE](https://www.bilibili.com/video/BV1P54y1v7AE)

```java

    /**
     * 理解：除了叶子节点，每个节点左右互换
     * 
     * @author 小道仙
     * @date 2020/8/29
     */
    TreeNode tmp = new TreeNode(-1);
    public TreeNode mirrorTree(TreeNode root) {
        if (root == null){
            return root;
        }
        TreeNode head = new TreeNode(-1);
        head.left = root;
        change(root);
        return head.left;
    }

    private void change(TreeNode root){
        if (root == null){
            return;
        }
        if (root.left == null && root.right == null){
            return;
        }
        tmp = root.left;
        root.left = root.right;
        root.right = tmp;

        if (root.left != null) change(root.left);
        if (root.right != null) change(root.right);
    }

```
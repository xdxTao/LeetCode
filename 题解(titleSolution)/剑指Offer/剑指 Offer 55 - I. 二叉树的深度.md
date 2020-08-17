## 题目位置

[https://leetcode-cn.com/problems/er-cha-shu-de-shen-du-lcof/](https://leetcode-cn.com/problems/er-cha-shu-de-shen-du-lcof/)

<br/>

## 题解

```java

    /**
     * 思路：
     *  1、便利二叉树的每一个节点，计算每一个节点高度
     *  2、用一个变量（max）记录最大的高度
     *  3、每次便利到根节点就判断当前高度和max那个大，最大值
     *  4、最后返回max即可
     *
     * @author 小道仙
     * @date 2020年8月17日
     */
    int max = -1;
    public int maxDepth(TreeNode root) {
        if (root == null){
            return 0;
        }
        fun(root,1);
        return max;
    }

    public void fun(TreeNode root,int cur){
        if (cur > max){
            max = cur;
        }
        if (root.left != null){
            fun(root.left,cur + 1);
        }
        if (root.right != null){
            fun(root.right,cur + 1);
        }
    }

```
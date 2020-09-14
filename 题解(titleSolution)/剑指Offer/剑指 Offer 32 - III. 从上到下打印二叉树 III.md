## 题目位置

[https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-iii-lcof/](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-iii-lcof/)

<br/>

## 题解

```java

    /**
     * 思路
     *  1、递归输出每一个节点，然后弄一个 level 等级标记节点
     *  2、如果等级是偶数就从尾部添加，如果等级是奇数就从头部添加
     *
     * @author 小道仙
     * @date 2020/9/14
     */
    private List<List<Integer>> lists = new ArrayList<>();
    public List<List<Integer>> levelOrder(TreeNode root) {
        fun(root, 0);
        return lists;
    }
    private void fun(TreeNode root,int level){
        if (root == null){
            return;
        }
        if (lists.isEmpty() || lists.size() <= level){
            List<Integer> list = new ArrayList<>();
            lists.add(list);
        }
        if (level % 2 == 0){
            lists.get(level).add(root.val);
        }else{
            lists.get(level).add(0,root.val);
        }
        if (root.left != null) fun(root.left, level+1);
        if (root.right != null) fun(root.right, level+1);
    }

```
## 题目位置

[https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-di-kda-jie-dian-lcof/](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-di-kda-jie-dian-lcof/)

<br/>

## 题解


```java
    /**
     * 思路：
     *  1、把二叉树里面的数据放到集合里面，然后对集合进行排序
     *  
     * @author 小道仙
     * @date 2020/9/1
     */
    List<Integer> list = new ArrayList<>();
    public int kthLargest(TreeNode root, int k) {
        fun(root);
        Collections.sort(list);
        return list.get(list.size() - k);
    }

    public void fun (TreeNode root){
        if (root == null){
            return;
        }
        list.add(root.val);
        if (root.left != null) fun(root.left);
        if (root.right != null) fun(root.right);
    }

```
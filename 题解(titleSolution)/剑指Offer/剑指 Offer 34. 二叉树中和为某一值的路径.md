## 题目位置

[https://leetcode-cn.com/problems/er-cha-shu-zhong-he-wei-mou-yi-zhi-de-lu-jing-lcof/](https://leetcode-cn.com/problems/er-cha-shu-zhong-he-wei-mou-yi-zhi-de-lu-jing-lcof/)

<br/>

## 题解

```java

    /**
     * 思路
     *  1、循环便利每一个从根到叶子的线路
     *  2、需要注意，值传递和地址值传递的问题
     *
     * @author 小道仙
     * @date 2020年9月16日
    */
    int sum;
    List<List<Integer>> lists = new ArrayList<>();
    public List<List<Integer>> pathSum(TreeNode root, int sum) {
        if (root != null){
            this.sum = sum;
            ArrayList<Integer> list = new ArrayList<>();
            list.add(root.val);
            fun(root,list,root.val);
        }
        return lists;
    }

    public void fun(TreeNode root,ArrayList list,int curSum){
        if (root == null){
            return;
        }
        if (root.left == null && root.right == null){
            if (curSum == sum){
                lists.add(list);
            }
        }
        if (root.left != null) {
            ArrayList arrayList = new ArrayList<>(list);
            arrayList.add(root.left.val);
            fun(root.left,arrayList ,curSum + root.left.val);
        }
        if (root.right != null) {
            ArrayList arrayList = new ArrayList<>(list);
            arrayList.add(root.right.val);
            fun(root.right, arrayList,curSum + root.right.val);
        }
    }

```
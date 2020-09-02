## 题目位置

[https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-ii-lcof/](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-ii-lcof/)

<br/>

## 题解


```java

    /**
     * 思路
     *  1、在遍历的时候传一个当前层级的参数 level
     *  2、然后每个当前值，都添加到当前层就好了
     *
     * @author 小道仙
     * @date 2020/9/2
     */
    List<List<Integer>> result = new ArrayList<>();
    public List<List<Integer>> levelOrder(TreeNode root) {
        fun(root,0);
        return result;
    }
    public void fun(TreeNode root,int level){
        if (root == null){
            return;
        }
        if (result.isEmpty() || level >= result.size()){
            List<Integer> tmp = new ArrayList<>();
            tmp.add(root.val);
            result.add(tmp);
        }else{
            result.get(level).add(root.val);
        }
        if (root.left != null) fun(root.left,level + 1);
        if (root.right != null) fun(root.right,level + 1);
    }

```
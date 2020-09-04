## 题目位置

[https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/)

<br/>

## 题解


B站视频讲解 [https://www.bilibili.com/video/BV1P54y1v7AE](https://www.bilibili.com/video/BV1P54y1v7AE)

```java

    /**
     * 二叉树的层序遍历
     *
     * @author 小道仙
     * @date 2020/9/4
     */
    List<List<Integer>> result = new ArrayList<>();
    int count = 0;
    public int[] levelOrder(TreeNode root) {
        fun(root,0);
        int[] arr = new int[count];
        int cur = 0;
        for (List<Integer> item : result){
            for (Integer iten : item){
                arr[cur ++] = iten;
            }
        }
        return arr;
    }

    public void fun(TreeNode root,int level){
        if (root == null){
            return;
        }
        count += 1;
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
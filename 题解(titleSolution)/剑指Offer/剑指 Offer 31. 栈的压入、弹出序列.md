## 题目位置

[https://leetcode-cn.com/problems/zhan-de-ya-ru-dan-chu-xu-lie-lcof/](https://leetcode-cn.com/problems/zhan-de-ya-ru-dan-chu-xu-lie-lcof/)

<br/>

## 题解

```java

    /**
     * 1、使用出站的第一个元素，进行左右分组
     * 2、判断出站的每一个元素（除去第一个元素），是否在分组的【左边末尾】或者是否在分组的【右边开头】
     * 3、判断当前元素是否在【左边分组】如果是就返回fasle
     * 4、如果把右边的元素从0直到当前元素全部转移到左边
     *
     * @author 小道仙
     * @date 2020年10月7日
     */
    public boolean validateStackSequences(int[] pushed, int[] popped) {
        if (pushed.length == 0 || popped.length == 0){
            return true;
        }
        List<Integer> left = new ArrayList<>();
        List<Integer> right = new ArrayList<>();
        init(pushed, left,right,popped[0]);
        for (int i = 1;i < popped.length; i++){
            if (!left.isEmpty() && left.get(left.size()-1) == popped[i]){
                left.remove(left.size()-1);
                continue;
            }
            if (!right.isEmpty() && right.get(0)  == popped[i]){
                right.remove(0);
                continue;
            }
            if (left.contains(popped[i])){
                return false;
            }

            fun(left,right,popped[i]);

        }
        return true;
    }

    private void init(int[] pushed,List<Integer> left,List<Integer> right, int cur){
        String flag = "left";
        for (int i = 0;i < pushed.length; i++){
            if (pushed[i] == cur){
                flag = "right";
            }else{

                if ("left".equals(flag)){
                    left.add(pushed[i]);
                }else {
                    right.add(pushed[i]);
                }
            }
        }
    }

    // 如果把右边的元素从0直到当前元素全部转移到左边
    private void fun(List<Integer> left,List<Integer> right, int cur){
        while (true){
            if (right.isEmpty() || right.get(0) == cur){
                right.remove(0);
                break;
            }
            left.add(right.remove(0));
        }
    }


```
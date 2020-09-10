## 题目位置

[https://leetcode-cn.com/problems/di-yi-ge-zhi-chu-xian-yi-ci-de-zi-fu-lcof/](https://leetcode-cn.com/problems/di-yi-ge-zhi-chu-xian-yi-ci-de-zi-fu-lcof/)

<br/>

## 题解


```java

    /**
     * 思路
     *  1、把每一个字符的数量都存入map里面去
     *  2、把每个不重复的字符存入list里面去
     * @author 小道仙
     * @date 2020/9/10
     */
    public char firstUniqChar(String s) {
        List<Character> list = new ArrayList<>();
        Map<Character,Integer> map = new HashMap<>();
        char[] chars = s.toCharArray();
        for (Character c : chars){
            if (!list.contains(c)){
                list.add(c);
            }
            if (map.containsKey(c)){
                map.put(c,map.get(c) + 1);
            }else{
                map.put(c,1);
            }
        }
        for (Character c : list){
            if (map.get(c) == 1){
                return c;
            }
        }
        return ' ';
    }

```
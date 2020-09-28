## 题目位置

[https://leetcode-cn.com/problems/fan-zhuan-dan-ci-shun-xu-lcof/](https://leetcode-cn.com/problems/fan-zhuan-dan-ci-shun-xu-lcof/)

<br/>

## 题解

```java

    /**
     * 思路：
     *  1、字符串按照【空格】切割
     *  2、然后倒叙对每个字符串去掉空格，判断是否为空字符串，如果不是就加进去
     *
     * @author 小道仙
     * @date 2020年9月28日
     */
    public String reverseWords(String s) {
        String[] s1 = s.split(" ");
        StringBuilder sb = new StringBuilder();
        for (int i = s1.length - 1;i >= 0; i--){
            sb.append(fun(s1[i]));
        }
        if ("".equals(sb.toString())){
            return "";
        }
        return sb.toString().substring(0, sb.toString().length()-1);
    }

    private String fun(String str){
        str = str.replace(" ","");
        if (str.length() > 0){
            return str+" ";
        }
        return "";
    }

```
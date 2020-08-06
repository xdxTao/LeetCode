## 题目位置

[https://leetcode-cn.com/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/](https://leetcode-cn.com/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/)

<br/>

## 题解

```java

    /**
     * 思路：
     *  1、这个题很简单，直接把前 n 个字符拿出来变成数组，然后一个个拼接到后面即可
     *  2、因为是使用到Java，需要反复的操作字符串，并且没有线程安全的问题，所以我们首选 StringBuilder
     *  
     * 其它：
     *  1、其中仔细思考一下，下面的代码是不是
     *  
     *  return s.substring(n,s.length()) + s.substring(0,n);
     */
    public String reverseLeftWords(String s, int n) {
        char[] chars = s.substring(0,n).toCharArray();
        StringBuilder result = new StringBuilder(s.substring(n,s.length()));
        for (int i = 0;i < chars.length; i++){
            result.append(chars[i]);
        }
        return result.toString();
    }

```
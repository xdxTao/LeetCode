## 题目位置

[https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/](https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/)

<br/>

## 题解


```java

/**
    * 这个题没什么难度，但是有趣的是 return s.replaceAll(" ","%20"); 这个答案很差劲
    * 然后我尝试了一下 return s.replace(" ","%20");
    * replace 要比 replaceAll 好很多，百度后发现 replaceAll 是支持正则匹配的，可能这个原因所以会慢一些
    *
    *
    * @author 小道仙
    * @date 2020/8/30
    */
public String replaceSpace(String s) {
    StringBuilder str = new StringBuilder();
    char[] chars = s.toCharArray();
    for (int i = 0;i < chars.length; i++){
        if (chars[i] == ' '){
            str.append("%20");
        }else {
            str.append(chars[i]);
        }
    }
    return str.toString();
}

```
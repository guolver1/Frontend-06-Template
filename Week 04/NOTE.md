学习笔记
##字典树
- 用Object或者Map来存储字典树
- 随机生成一个字母的方法：

`String.fromCharCode(Math.random()*26+"a".charCodeAt(0));`

fromCharCode：Unicode->字符
charCodeAt（n）: 字符-> Unicode，返回第n个字符的Unicode

##KMP字符串模式匹配算法
- 待查的串和pattern串
- 关注字符串的自重复行为，分别从前面开始截短
# 正则表达式
* 正则表达式是计算机科学的一个概念。正则表达式使用单个字符串来描述、匹配一系列符合某个句法规则的字符串在很多文本编辑器里，正则表达式通常被用来检索、替换那些符合某个模式的文本。  
## 创建
* JavaScript通过内置对象RegExp支持正则表达式，有两种方式穿件正则表达式对象，如果我们想匹配字符串中<%xxx%>两个百分号分隔的字符串可以这么写。  
1. 构造函数
  var reg = new RegExp('<%[^%]+%>','g');  
2. 字面量
  var reg = /<%[^%]%>g;
最后的g代表全全局，还有几个修饰符。
1. g:global,全文搜索，不添加的话搜索到第一个结果停止搜索
2. i:ingore case，忽略大小写，默认大小写敏感。
3. m:multiple lines,多行搜索。。

### 元字符
在正则表达式中具有特殊意义的专用字符，可以用来规定其前导字符。
([ { \ ^ $ | ) ? * +

* 一般情况下正则表达式一个字符（转义字符算一个）对应字符串一个字符

### 预定义类
![](https://github.com/zzxx9426/myPicture/blob/master/RegExp%20%E9%A2%84%E5%AE%9A%E4%B9%89%E7%B1%BB.png?raw=true)  
### 边界

![](https://github.com/zzxx9426/myPicture/blob/master/RegExp%E8%BE%B9%E7%95%8C.png?raw=true)  
### 量词

![](https://github.com/zzxx9426/myPicture/blob/master/RegExp%E9%87%8F%E8%AF%8D.png?raw=true)  
### 贪婪模式与非贪婪模式


### 分组

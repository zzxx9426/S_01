# Date
### 事件的表示方式
GMT / UTC /CST
### JavaScript中的Date
### new Date()
* 使用Date构造函数创建一个Date实例

![](https://github.com/zzxx9426/myPicture/blob/master/new%20Date().png?raw=true)  
### set
![](https://github.com/zzxx9426/myPicture/blob/master/setDate().png?raw=true)  

* Date.prototype.toString()  
toString方法返回一个完整的时间字符串
* Date.prototype.toDateString()，Date.prototype.toTimeString()  
toDateString方法返回日期的字符串形式，toTimeString方法返回时间的字符串形式。
* toLocalDateString, toLocalTimeString
toLocalDateString方法返回一个字符串，代表日期的当地写法
toLocalTimeString方法返回一个字符串，代表时间的当地写法  
* Date.now()
返回当前距离1970年1月1日00:00:00的毫秒数。

* Date.parse()
parse方法用来解析日期字符串，返回距离1970年1月1日00:00:00的毫秒数。

### 在新建日期对象时，如果不设置时间，则认为创建的是utc的0点，也就是北京时间8点。如果设置时间，则是北京时间当前时间。

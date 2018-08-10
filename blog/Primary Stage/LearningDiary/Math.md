# Math
* Math对象是JavaScript的内置对象，提供一系列数学常数和数学方法。Math对象只提供了静态的属性和方法，所以使用时不用**实例化**。
### 属性
* Math对象提供一下一些只读的数学常数。  
![](https://github.com/zzxx9426/myPicture/blob/master/Math%E5%B1%9E%E6%80%A7.png?raw=true)  
### 方法
**round**
* round方法用于四舍五入
> Math.round(0.1) //0
> Math.round(0.5) //1
* 它对于负值的运算结果与正值略有不同，主要体现在对.5的处理。
> Math.round(-1.1)  // -1
> Math.round(-1.5)  // -1

### abs, max, min
* abs方法返回参数值的绝对值  

* max方法返回最大的参数，min方法返回最小的参数。

### floor, ceil
* floor方法返回小于参数值的最大整数
* ceil方法返回大于参数值的最小整数

### pow，sqrt
* pow方法返回以第一个参数为底数、第二个参数为幂的指数值。
Math.pow(2, 3) //8
* sqrt方法返回参数值的平方根。如果参数是一个负值，则返回NaN。
Math.sqrt(4) //2
Math.sqrt(-4) //NaN

### log,exp
* log方法返回以e为底的自然对数值。
Math.log(Math.E) //
Math.log(10) //

# 常数e代表什么？
```
数学家把这个数就成为e，它的含义是单位时间内，持续的翻倍增长所能达到的极限值。
这个值是自然增长的极限，因此以e为底的对数，就叫做自然对数。
```
### random
* 该方法返回0到1之间的一个伪随机数，可能等于0，但是一定小于1。
![](https://github.com/zzxx9426/myPicture/blob/master/Math.random.png?raw=true)  

### 三角函数

sin方法返回参数的正弦，cos方法返回参数的余弦，tan方法返回参数的正切。  
Math.sin(0)  //0  
Math.cos(0)  //1  
Math.tan(0)  //0  

* asin方法返回参数的反正弦，acos方法返回参数的反余弦，atan方法返回参数的反正切。这三个方法的返回值都是弧度值。
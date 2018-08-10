### 数组
基本使用  
![数组](https://github.com/zzxx9426/myPicture/blob/master/%E6%95%B0%E7%BB%84.png?raw=true)

### 创建数组
在JavaScript多种方式创建数组

### 构造函数
在使用构造函数创建数组时如果传入一个*数字*参数，则会创建一个长度为参数的数组，如果传入多个，则创建一个数组，参数作为初始化数据加到数组中。  
![](https://github.com/zzxx9426/myPicture/blob/master/%E6%95%B0%E5%AD%97%E5%8F%82%E6%95%B0.png?raw=true)

### 字面量
使用字面量方式，无论传入几个参数，都会把参数当做初始化内容。
在使用初始化参数的方式创建数组的时候，最好最后不要带多余的“，”，在不同的浏览器下对此处理方式不一样。    
![](https://github.com/zzxx9426/myPicture/blob/master/%E5%AD%97%E9%9D%A2%E9%87%8F%E5%9C%A8%E4%B8%8D%E5%90%8C%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%8B%E6%98%BE%E7%A4%BA%E7%9A%84%E6%95%B0%E7%BB%84%E9%95%BF%E5%BA%A6%E4%B8%8D%E5%90%8C.png?raw=true)

**在现代浏览器上运行结果，长度为3.但是在低版本IE下长度为4，最后一条数据为undefined.**

### 数组的索引与长度

1. 数组的值可以通过自然数索引访问进行读写操作，下标也可以是一个得出非负整数的变量或表达式。
2. 数组也是对象，我们可以使用索引的奥秘在于，数组会把索引值转换为对应字符串（1=>"1"）作为对象属性名
3. 可以看出所有的索引都是属性名，但只有自然数（有最大值）才是索引，一般我们在使用数组的时候不会出现数组越界错误也正是因为此，数组的索引可以不是连续的，访问index不存在的元素的时候返回undefined
4. 数组length属性等于数组中最大的index+1，数组的length属性是个可写的属性，当强制把数组的length属性值设置为小于等于最大index值时，数组会自动删除index大于等于length的数据，如果把length设置为大于最大index+1的值的时候，数组也会自动扩张，但是不会为数组添加新元素，只是在尾部追加空空间。
> var a = new Arry(1, 2, 3);  
 > a.length = 5;  
  > console.log(a);  //[1, 2, 3, empty × 2]

### 元素添加/删除

* 基本方法

数组也是对象，索引只是特殊属性，所以我们可以使用删除对象属性的方法，使用delete删除数组元素

* 栈方法  
pop push 先入后出  
![](https://github.com/zzxx9426/myPicture/blob/master/%E6%A0%88%E6%96%B9%E6%B3%95.png?raw=true)

* 队列方法

先入先出 shift unshift  
shift方法可以删除数组index最小元素，并使用后面元素index都减一，le

2. 删除元素的位移
3. 插入的新元素，当然可以写多个  

splice方法返回一个由删除元素组成的新数组，没有删除则返回空数组。

### 删除
![](https://github.com/zzxx9426/myPicture/blob/master/%E5%88%A0%E9%99%A4.png?raw=true)  
![](https://github.com/zzxx9426/myPicture/blob/master/%E4%B8%8D%E6%98%AF%E4%BB%8E0%E5%BC%80%E5%A7%8B%E7%9A%84%E5%88%A0%E9%99%A4.png?raw=true)

splice的第一个参数是绝对索引值，而不是相对于数组索引，第二个参数并不是删除元素的个数，而是删除动作执行多少次，并不是按数组实际索引移动，而是连续移动。同时调整后面元素索引，前面索引不理会。

### 插入与替换
只要方法第二个参数，也就是删除动作执行的次数设为0，第三个参数及以后填写要插入内容就splice就能执行插入操作，而如果第二个参数不为0则变成了现在该位置删除再插入，也就是替换效果。

### 常用操作

* join（char）  
这个方法在C#等语言中也有，作用是把数组元素（对象调用其toStrin（）方法）使用参数作为连接符连成一字符串，不会修改原数组内容。

### slice(start,enf)

> * slice方法对array中的一段做浅复制。首先赋值array[start],一直复制到array[end]为止。end参数是可选的，默认值是该数组的长度array.length。如果两个参数中的任何一个是负数，array.length会和它们相加，试图让它们成为非负数，如果start大于等于array.length，得到的结果将是一个新的空数组。千万别把slice和splice弄混了，字符串也有一个同名的方法。 ( _JS语言精粹_ ) 
> * 不要和splice方法混淆，slice方法用于返回数组中一个片段或子数组，如果只写一个参数到数组结束部分，如果参数出现负数，则从数组尾部技术（-3意思是数组倒数第三个，一般人不会这么干，但是在不知道数组长度，想舍弃后n个的时候有些用，不过数组长度很好知道），如果start大于end返回空数组，值得注意的一点是slice不会改变原数组，而是返回一个新的数组。

### sort
sort方法用于对数组进行排序，当没有参数的时候按字母表升序排序，如果含有undefined会被排到最后面，对象元素则会调用其toString方法，如果想按照自己定义当时排序，可以传一个排序方法进去，很典型的策略模式，同样sort会改变原数组。  
![](https://github.com/zzxx9426/myPicture/blob/master/%E5%AD%97%E6%AF%8D%E6%8E%92%E5%BA%8F.png?raw=true)  
**因为字母表排序，7就比10打，这时候我们需要传入自定义排序函数**
如果想按照数值排序  
![](https://github.com/zzxx9426/myPicture/blob/master/%E6%8C%89%E6%95%B0%E5%80%BC%E6%8E%92%E5%BA%8F.png?raw=true)  

## ES5
ES5为Array对象做了大幅扩展

Array.isArray(obj)
这是Array对象的一个静态函数，用来判断一个对象是不是数组。

.indexOf(element)/.lastIndexOf(element)

这两个方法用于查找数组内指定元素位置，查找到第一个后返回其索引，没有查找到返回-1，indexOf从头到尾搜索，lastIndexOf反向搜索。  
![](https://github.com/zzxx9426/myPicture/blob/master/indexOf%E3%80%81lastIndexOf.png?raw=true)  

### .forEach(element,index,array)
遍历数组，参数为一个回调函数，回调函数有三个参数：

1. 当前元素
2. 当前元素索引值
3. 整个数组

.every(function(element,index,array))/
.some(function(element,index,array))

这两个函数类似于离散数学中的逻辑判定，回调函数返回一个**布尔值**
1. every是所有函数的每个回调函数都返回true的时候才会返回true，当遇到false的时候终止执行，返回false。
2. some函数是"存在"有一个回调函数返回true的时候终止执行并返回true，否则返回false。
在空数组上调用every返回true，some返回false。
> ![](https://github.com/zzxx9426/myPicture/blob/master/forEach.png?raw=true)  

> ![](https://github.com/zzxx9426/myPicture/blob/master/every%E3%80%81some.png?raw=true)  

### .map(funciton(element))
与forEach类似，遍历数组，回调函数返回值组成一个新数组返回，新数组索引结构和原数组一致，原数组不变。  
![](https://github.com/zzxx9426/myPicture/blob/master/map%E9%81%8D%E5%8E%86.png?raw=true)  

### .filter(function(element))

返回数组的一个自己，回调函数用于逻辑判断是否返回，返回true则把当前元素加入到返回数组中，false则不加。  

新数组只包含返回true的值，索引缺失的不包括，原数组保持不变。

### .reduce(function(v1,v2),value)/.reduceRight(function(v1,v2),value)

遍历数组，调用回调函数，将数组元素组合成一个值，reduce从所用最小值开始，reduceRight反向，方法有两个参数

1. 回调函数：把两个值合为一个，返回结果
2. value， 一个初始值，可选。

> 练习 (*yilianmengb*)  
实现一个reduce函数，作用和原生的reduce类似。  
![](https://github.com/zzxx9426/myPicture/blob/master/reduce%E5%87%BD%E6%95%B0.png?raw=true)
实现一个flatten函数，将一个嵌套多层的数组array（数组）（嵌套可以使任何层数）转换为只有一层的数组，数组中元素仅基本类型的元素或数组，不存在循环引用的情况。    
![](https://github.com/zzxx9426/myPicture/blob/master/flatten%E5%87%BD%E6%95%B0.png?raw=true)
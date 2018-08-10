### DOM

* 文档对象模型（DOM)是HTML和XML文档的编程接口。它给文档（结构树）提供了一个结构化的表述并且定义了一种方式——程序可以对结构树进行访问，以改变文档的结构，样式和内容。

DOm提供了一种表述形式将文档作为一个结构化的节点以及包含属性和方法的对象。从本质上说，它将web页面和脚本或编程语言连接起来。
![](https://github.com/zzxx9426/myPicture/blob/master/DOM%E6%A0%91.png?raw=true)  
要改变页面的某个东西，JavaScript就需要获得会HTML文档中所有元素进行访问的入口。这个入口，连同对HTML元素进行添加、移动、改变或移除的方法和属性，都是通过DOM来获取的。  

### document对象

每个载入浏览器的HTML文档都会成为document对象。document对象包含了文档的基本信息，我们可以通过JavaScript对HTML页面中的所有元素进行访问、修改。

### document对象常用属性

> document.doctype  
> document.title  
> document.characterSet  
> document.head  
> document.body  
> document.images  

> document.readyState  
  >> readyState 属性返回当前文档的状态，共有三种可能的值。
  >> 1. loading:加载HTML代码阶段，尚未完全解析
  >> 2. interactive：加载外部资源阶段
  >> 3. complete： 全部加载完成

> document.compat
>> compatMode 属性返回浏览器处理文档的模式，可能的值为
>> 1. BackCompat:向后兼容模式，也就是没有添加DOCTYPE
>> 2. CSS1Compat:严格模式，添加DOCTYPE

### document.location
> document.location === location //true
> document.location === window.location //true

location属性返回一个只读对象，提供了当前你文档的URL信息
![](https://github.com/zzxx9426/myPicture/blob/master/document.location.png?raw=true)  
虽然location属性但会的对象是只读的，但是可以将URL赋值给这个属性，网页就会自动跳转到指定网址。  
document.location = ''http://wwww.example.com';  
// 等价于  
document.location.herf = 'http://wwww.example.com';  
### document.location.open()、document.close()

document.open方法用于新建一个文档，供write放写入内容。它实际上等于清楚当前文档，重新写入内容。  
document.close方法用于关闭open方法所新建的文档。一旦关闭，write方法就无法写入内容了。  

### document.write()
document.write方法用于向当前文档写入内容。只要当前文档还没有用close方法关闭，它所写入的内容就会追加在已有内容的后面。  
document.open();  
document.write("hello");  
document.write("world");  
document.close();  
> 1. 如果页面已经渲染完成再调用write方法，它会先调用open方法，擦除当前文档所有内容，然后再写入。
> 2. 如果在页面渲染过程中调用write方法，并不会调用open方法。

* 需要注意的是，虽然调用close方法之后，无法再用write方法写入内容，但这是当前页面的其他DOM节点还是会继续加载。  
* 除了某些特殊情况，应该尽量避免使用document.write这个写法。

### Element
除了document对象，再DOM中最常用的就是Element对象，Element对象表示HTML元素。

Element对象可以拥有类型为元素节点、文本节点、注释节点的子节点，DOM提供了一系列的方法可以进行元素的增、删、改、查操作。  

Element有几个重要属性  
> 1. nodeName:元素标签名，还有个类似的tagName
> 2. nodeType:元素类型
> 3. className:类名
> 4. id： 元素id
> 5. children： 子元素列表（HTMLCollection）
> 6. childNodes：子元素列表（NodeList）
> 7. firstChild ：第一个子元素
> 8. lastChild： 最后一个子元素
> 9. nextSibling：下一个兄弟元素
> 10. prevousSibling:上一个兄弟元素
> 11. parentNode、parentElement: 父元素

## 查询元素
### getElementById()
getElementByid方法返回匹配指定ID属性的元素节点。如果没有发现匹配的节点，则返回null。这也是获取一个元素最快的方法。
var elem = document.getElementById("test");  
### getElementsByClassName()
    HTMLCollection接口表示一个包含了元素（元素顺序为文档流中的顺序）的通用集合（generic collection），还提供了用来从该集合中选择元素的方法和属性。
getElementsByClassName方法返回一个类似数组的对象（HTMLCollection类型对象），包括了所有class名字符合指定条件的元素（搜索范围包括本身），元素的变化实时反映在返回结果中。这个方法不仅可以在document对象上调用，也可以在任何元素节点上调用。  
var elements = document.getElementsByClassName('tab');
getElementsByClassName方法的参数，可以是多个空格分隔的class名字，返回同时具有这些节点的元素。  
document.getElementsByClassName('red test');
### getElementsByTagName()
getElementsTagName方法返回所有指定标签的元素（搜索范围包括本身）。返回值是一个HTMLCollection对象，也就是说，搜索结果是一个动态集合，任何元素的变化都会实时反映在返回的集合中。这个方法不仅可以在document对象上调用，也可以在任何元素节点上调用。  
var paras = document.getElementsByTagName("p");  
代码返回当前文档的所有p元素节点。注意，getElementByTagName方法会将参数转为小写后，在进行搜索。
### getElementsByName()
getElementsByName方法用于选择拥有name属性的HTML元素，比如form、img、frame、embed和object，返回一个NodeList格式的对象，不会实时反映元素的变化。   
    //假定有一个表单是<form name="x"></form>
    var forms = document.getElementsByName("x");
    forms[0].tagName  // "FORM"  
    注意，在IE浏览器使用这个方法，会将没有name属性、但有同名id属性的元素也返回，所以name和id属性最好设为不一样的值。

### querySelectoer()
querySelector方法返回匹配指定的CSS选择器的元素节点。如果有多个节点满足匹配条件，则返回第一个匹配的节点。如果没有发现匹配的节点，则返回null。  
querySelector方法无法选中CSS伪元素。

### querySelectorAll（）
querySelectorAll方法返回匹配指定的CSS选择器的所有节点，返回的是NodeList类型的对象。NodeList对象不是动态集合，所以元素节点的变化无法实时反映在返回结果中。  
elementList = document.querySelectorAll(selectors);  
querySelectorAll方法的参数，可以是逗号分隔的多个CSS选择器，返回所有匹配其中一个选择器的元素。  
> var matches = document.querySelectorAll("div.note, div.alert");
上面代码返回class属性是note或alert的div元素。

### 创建元素

### createElement()

createElement方法用来生成HTML元素节点。
> var newDiv = document.creataElement("div");  
createElement方法的参数为元素的标签名，即元素节点的tagName属性。如果传入大写的标签名，会被转为小写。如果参数带有尖括号（即<和>）或者是null，会报错。

#### createTextNode()
> createTextNode方法用来生成文本节点，参数为所要生成的文本节点的内容。
>> var newDiv = document.createElement("div");  
>> var newContent = document.createTextNode("hello");  
上面代码新建一个div节点和一个文本节点

### createDocumentFragment()

createDocumentFragment方法生成一个DocumentFragment。
> var docFragment = document.createFragment();  
DocumentFragment对象是一个存在于内存的DOM片段，但是不属于当前文档，常常用来生成较复杂的DOM结构，然后插入当前文档。这样做的好处在于，因为DocumentFragment不属于当前文档，对它的任何改动，都不会引发网页的重新渲染，比直接修改当前文档的DOM有更好的性能表现。  

## 修改元素
### appendChild()  
在元素末尾添加元素
> var newDiv = document.createElement("div");  
> var newContent = document.createTextNode("hello");
> newDiv.appendChild(newContent)

### insertBefore()

在某个元素之前插入元素
> var newDiv = document.createElement("div");
> var newContent = document.createTextNode("hello");
> newDiv.insertBefore(newContent, newDiv.fitstChild);

### replaceChild()
replaceChild()接受两个参数：要插入的元素和要替换的元素。
> newDiv.replaceChild(newElement, oldElement);

## 删除元素
删除元素使用removeChild()方法即可
> parentNode.removeChild(childNode);

## clone元素
cloneNode()方法用于克隆元素，方法有个布尔值参数，传入true的时候会深复制，也就是会赋值元素机器子元素（IE还会复制其事件），false的时候只复制元素本身。
> node.clonneNode(true);

### 属性操作

### getAttribute()
getAttribute()用于获取元素的attribute值
> node.getAttribute('id');

### createAttribute()
createAttribute()方法生成一个新的属性对象节点，并返回它。
> attribute = document.createAttribute(name);  
createAttribute方法的参数name，是属性的名称。

### setAttribute()
setAttribute()方法用于设置元素属性

> var node = document.getElementById("id");  
> node.setAttribute("my_attrib","newVal");  

### removeAttribute()
removeAttribute()用于删除元素属性
> node.removeAttribute('id');

### element..attributes
当然上面的方法做的事情也可以是通过类操作数组属性element.attributes来实现。

### innerText 
innerText是一个可写属性，返回元素内包含的文本内容，在多层次的时候会按照元素由浅到深的顺序拼接其内容

 ```
 <div>  
    <p>
        123
        <span>456</span>
    </p>
</div> 
```

外层div的innerText返回内容是“123456”

### innerHTML
innerHTML属性作用和innerText类似，但是不是返回元素的文本内容，而是返回元素的HTML结构，在写入的时候也会自动构建DOM。
 ```
 <div>  
    <p>
        123
        <span>456</span>
    </p>
</div> 
```
外层div的innerHTML返回内容是
```
“<p> 123<span>456</span></p>”  
```
### 常见使用方式

### 修改样式
可修改元素的style属性，修改结果直接反应到页面元素。
> document.querySelector('p').style.color = 'red'
> document.querySelector('.box').style.backgroundColor = '#ccc'

### 获取样式 getComputedStyle
使用getComoutedStyle获取元素计算后的样式，不要通过*node.style.属性*获取

> var node = document.querySelector('p')
> var color = window.getComputedStyle(node).color
> console.log(color)

### class操作 
> var nodeBox = document.querySelector('.box')  
> console.log(nodeBox.classList)  
> nodeBox.classList.add('active')  // 新增class
> nodeBox.classList.remove('active')  //删除class
> nodeBox.classList.toggle('active')  //  新增/删除切换
> node.classList.contains('active)  // 判断是否拥有class

样式的改变尽量使用class的新增删除来实现

### 页面宽高
> element.clientHeight
> element.offsetHeight

* element.scrollHeight 元素滚动内容的总长度。如果元素没出现滚动条，scrollHeight等于clientHeight
* element.scrollTop滚动的高度
* window.innerHeight 窗口的高度
* element.getBoundingClientRect()获取元素在视窗中的位置

### HTMLCollection和NodeList

节点都是单个对象，有事会需要一种数据结构，能够容纳多个节点。DOM提供两种集合对象，用于实现这种节点的集合：NodeList和HTMLCollection.  

NodeList对象代表一个有顺序的节点列表，HTMLCollection是一个接口，表示HTML元素的集合，它提供了可以遍历列表的方法和属性。  

获取的为HTMLCollection对象
> document.images   // 所有img元素
> document.links   // 所有带href属性的a元素和area元素
> document.forms  // 所有form元素
> document.scripts // 所有script元素
> document.body.children
> document.getElementByClassName("class1")

获取的为NodeList对象
> document.getElementsByName("name1")
> document.getElementsByTagName("a")
> document.querySelectorAll("a")
> document.body.childNodes

* HTMLCollection与NodeList基本相似
相同点：都是类数组对象，节点的变化都会实时反映在集合中。
不同点：少部分方法不一样，比如NodeList有forEach方法，而HTMLCollection没有。































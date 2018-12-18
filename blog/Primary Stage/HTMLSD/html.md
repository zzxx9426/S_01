## HTML:超文本标记语言。是一种用于穿件网页的标准标记语言。HTML是一种基础技术，常与CSS、JavaScript一起被众多网站用于设计网页、网页应用程序以及移动应用程序的用户界面。网页浏览器可以读取HTML文件，并将其渲染成可视化网页。  

发展年份  
> 1997.1 HTML 3.2   
> 1997.12 HTML 4.0  
> 1999.12. HTML 4.01  
> 2014.10 HTML 5    

## HTMLvsXMLvsXHTML
* HTML,超文本标记语言，是语法较为松散的、不严格的Web语言；
* XML，可扩展标记语言，主要用于储存数据和结构；
* XHTML，可扩展超文本标记语言，基于XML，作用与HTML类似，但语法更严格。

## 表现（内容）、样式、行为分离  
* 写HTML的时候先不管样式，重点放在HTML的结构和语义化上，让HTML能体现页面结构或者内容。之后再去写样式。  
* 写JS的时候，尽量不要用JS去直接操作样式，而是通过给元素添加删除class来控制样式变化。
* HTML内部不允许出现属性样式，尽量不要出现行为样式。  

 ## 语义化HTML  
 语义化HTML是一种编写HTML的方式 
 选择合适的标签、使用合理的代码结构，便于开发者阅读，同时让浏览器的爬虫和及其很好地解析。  


 ## HTML、XML、XHTML有什么区别？
1.  XML
  XML是The Extensible Markup Language（可扩展表示语言）的简写。目前推荐遵循的是W3C于2000年10月6日发布的XML1.0。XML最初设计的目的是弥补HTML的不足，以强大的扩展性满足网络信息发布的需要，后来用于**网络数据**的转换和描述。
2.  XHTML
  XHTML是The Extensible Markup Language 可扩展标识语言的缩写。目前推荐遵循的是W3C于2000年1月26日推荐XML1.0。XML虽然数据转换能力强大，完全可以替代HTML，但面对成千上万已有的站点，直接采用XML还为时过早。因此，我们在HTML4.0的基础上，用XML的规则对其进行扩展，得到了XHTML。简单的说，建立XHTML的目的是实现HTML向XML的国度。
3.  HTML
  HTML是网络的通用语言，一直简单、通用的全置标记语言。它允许**网页制作**人建立文本与图片相结合的复杂页面，这些页面可以被网上任何其他人浏览到，无论使用的是什么类型的电脑或浏览器。事实上你不需要任何专门的软件来建立HTML页面;你所需要的只是一个文字处理器如（McrosoftWord\记事本\写字板等等）以及HTML的工作常识。其实你很快就会发现，基础的**HTML语言**非常简单。
HTML只不过是组合一个文本文件的一系列标签。
HTML标签通常是英文词汇的全称（如块引用：blockquote）或缩略语（如“P”代表Paragragh），但它们的与一般文本有区别，因为它们放在单书名号里。故Paragragh标签是 < p > ,块引用标签是< blockquote>。有些标签说明页面如何被格式化（例如，< p >开始一个新段落），其他则说明这些词如何显示（< b >使文字变粗）还有一些其他标签提供在页面上不显示的信息-----例如标题。
关于标签，需要记住的是，它们是成双出现的。每当使用一个标签-----如< blockquote >,则必须以另一个标签 < / blockquote >将它关闭。
基本HTML页面以< html >标签开始，以< /html >结束。在它们之间，整个页面有两部分-----标题和正文。
标题词 -----夹在< head >和</ head >标签之间－－这个词语在打开页面时出现在屏幕底部最小化的窗口。正文则夹在< body>和< /body>之间------即所有页面的内容所在。页面上显示的任何东西都包含在这两个标签之中。
* * *
* * *
## 什么是HTML语义化？
1.  什么是HTML语义化？
 *基本上都是围绕着几个主要的标签，像标题（H1~H6）、列表（li）、强调（strong em）等等*
根据内容的结构化（内容语义化），选择合适的标签（代码语义化）便于**开发者阅读和写出更优雅的代码**的同时**让浏览器的爬虫和机器很好地解析。**
2.  为什么要语义化？
 *   为了在没有CSS的情况下，页面也能呈现出很好地内容结构、代码结构:为了裸奔时好看；
 *  **用户体验**：例如title、alt用于解释名词或解释图片信息、label标签的活用；
 *  有利于[SEO](http://baike.baidu.com/item/seo):和搜索引擎建立良好沟通，有助于爬虫抓取更多的有效信息：[爬虫](http://baike.baidu.com/item/%E7%88%AC%E8%99%AB)依赖于标签来确定上下文和各个关键字的权重；
 *  方便其他设备解析（如屏幕阅读器、盲人阅读器、移动设备）以意义的方式来渲染网页；
 *  便于团队开发和维护，语义化更具可读性，是下一步网页的重要动向，遵循W3C标准的团队都遵循这个标准，可以减少差异化。
3.  写HTML代码时应注意什么？
 *  尽可能少的使用无语义的标签div和span；
 *  在语义不明显时，既可以使用div或者p时，尽量用p，因为p在默认情况下有上下间距，对兼容特殊终端有利；
  *  不要使用纯样式标签，如：b、font、u等，改用css设置。
 *  需要强调的文本，可以包含在strong或者em标签中（浏览器预设样式，能用CSS指定就不用他们），strong默认样式是加粗（不要用b），em是斜体（不用i）；
 *  使用表格时，标题要用caption，表头用thead，主体部分用tbody包围，尾部用tfoot包围。表头和一般单元格要区分开，表头用th，单元格用td；
 * **表单域要用fieldset标签包起来，并用legend标签说明表单的用途；**    
 *         每个input标签对应的说明文本都需要使用label标签，并且通过为input设置id属性，在lable标签中设置for=someld来让说明文本和相对应的input关联起来。    
  *   ~~[HTML5](http://www.html5jscss.com/html5-semantics-section.html)语义标签* 暂留*~~
* * *
* * *
  ###  怎样理解内容与样式分离的原则

* HTML是用标签说明内容，CSS负责渲染，JavaScript是用来处理相关动作。
* * *
### Doctype作用
* < !DOCTYPE>声明叫做文件类型定义（DTD），声明的作用为了告诉浏览器该文件的类型。让浏览器解析器知道应该用哪个规范来解析文档。< !DOCTYPE>声明必须在 HTML 文档的第一行，但这并不是一个 HTML 标签。
*  严格模式：又称标准模式，是指浏览器按照 W3C 标准解析代码。

     混杂模式：又称怪异模式，是指浏览器用自己的方式解析代码。

   如何区分：浏览器解析时到底使用严格模式还是混杂模式，与网页中的 DTD 直接相关。  

  1.  如果文档包含严格的 DOCTYPE ，那么它一般以严格模式呈现。（严格 DTD ——严格模式）   
  2.  包含过渡 DTD 和 URI 的 DOCTYPE ，也以严格模式呈现，但有过渡 DTD 而没有 URI （统一资源标识符，就是声明最后的地址）会导致页面以混杂模式呈现。（有 URI 的过渡 DTD ——严格模式；没有 URI 的过渡 DTD ——混杂模式）   
   3.  DOCTYPE 不存在或形式不正确会导致文档以混杂模式呈现。（DTD不存在或者格式不正确——混杂模式）   
   4.  HTML5 没有 DTD ，因此也就没有严格模式与混杂模式的区别，HTML5 有相对宽松的语法，实现时，已经尽可能大的实现了向后兼容。（ HTML5 没有严格和混杂之分）  

    意义：严格模式与混杂模式存在的意义与其来源密切相关，如果说只存在严格模式，那么许多旧网站必然受到影响，如果只存在混杂模式，那么会回到当时浏览器大战时的混乱，每个浏览器都有自己的解析模式。 混杂模式服务于旧式规则，严格模式服务于标准规则。   

### DTD的具体声明  
> *1*、HTML5（一种）：< !DOCTYPE html>  
> *2*、HTML 4.01（三种）：严格模式包含所有 HTML 元素和属性，但不包括展示性的和弃用的元素（比如 font），不允许框架集（Framesets）；过渡模式包含所有 HTML 元素和属性，包括展示性的和弃用的元素（比如 font），不允许框架集（Framesets）；框架模式等同于过渡模式，但允许框架集内容。   
> HTML 4.01 Strict ：< !DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">  
> HTML 4.01 Transitional ：< !DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"  "http://www.w3.org/TR/html4/loose.dtd">  
> HTML 4.01 Frameset ：< ！DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN"  "http://www.w3.org/TR/html4/frameset.dtd">  
> *3*、XHTML 1.0（四种）：前三种模式同上，XHML 必须以格式正确的 XML 来编写标记。   
> XHTML 1.0 Strict ：< !DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">   
> XHTML 1.0 Transitional ：< !DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" " http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">   
> XHTML 1.0 Frameset： < !DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN"  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">   
> XHTML 1.1 该 DTD 等同于 XHTML 1.0 Strict，但允许添加模型。< !DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">  

### <!doctype html>的作用
是html5的头声明，其实是一种回归，回归简单声明方式。
* * *
* * *

### 有哪些常见的meta标签
#### meta
1. Keywords (关键字)
说明：告诉搜索引擎你网页的关键字是什么。
用法：< meta name="keywords" content="SEO优化,SEO优化教程,网站优化,搜索引擎优化教程">
2. Description (网页描述)
说明：Description用来告诉搜索引擎你的网页主要内容。
用法：< meta name="description" content="学习研究搜索引擎优化网提供专业的SEO优化教程，收集整理SEO优化文章、SEO优化工具，为网络营销贡献出自己的一份力量。" />
3. Robots (机器人向导)
说明：Robots用来告诉搜索机器人哪些页面需要索引，哪些页面不需要索引。Content的参数有all、none、index、noindex、follow、nofollow。默认是all。
用法：< meta name="robots" content="All|None|Index|Noindex|Follow|Nofollow">
all：文件将被检索，且页面上的链接可以被查询；
none：文件将不被检索，且页面上的链接不可以被查询；(和 "noindex, no follow" 起相同作用)
index：文件将被检索；（让robot/spider登录）
follow：页面上的链接可以被查询；
noindex：文件将不被检索，但页面上的链接可以被查询；(不让robot/spider登录)
nofollow：文件将不被检索，页面上的链接可以被查询。(不让robot/spider顺着此页的连接往下探找) 

4. Author (作者)
说明：标注网页的作者或制作组
用法：< meta name="author" content="mycodewind，mycodewind@qq.com">
注意：Content可以是：你或你的制作组的名字,或Email
5. Copyright (版权)说明：标注版权用法：< meta name="copyright" content="本网站版权归CSDN所有">
6. Generator (编辑器)说明：编辑器的说明用法：< meta name="generator" content="PCDATA|FrontPage|">注意：Content="你所用编辑器"
7. Revisit-after (重访)说明：通知搜索引擎多少天访问一次用法：< meta name="revisit-after" content="7 days" >从IE9开始引入了固定网站功能，对用户来说这是一种只需在任务栏上单击图标即可直接访问网站的简单方式。固定网站还易于实现，仅需要非常少的代码。以下的元数据标签只在IE9+生效。如Windows Vista,Windows 7系统上。官方文档地址http://msdn.microsoft.com/zh-cn/library/ie/gg491732%28v=vs.85%29.aspx 。所有元素都是可选的。
8.移动端viewport标签含义如下：width控制 viewport 的大小，可以指定的一个值或者特殊的值，如 device-width 为设备的宽度（单位为缩放为 100% 时的 CSS 的像素）。
height和 width 相对应，指定视窗的高度。
target-densitydpi一个屏幕像素密度是由屏幕分辨率决定的，通常定义为每英寸点的数量（dpi）。Android支持三种屏幕像素密度：低像素密度，中像素密度，高像素密度。一个低像素密度的屏幕每英寸上的像素点更少，而一个高像素密度的屏幕每英寸上的像素点更多。Android Browser和WebView默认屏幕为中像素密度。下面是 target-densitydpi 属性的 取值范围device-dpi –使用设备原本的 dpi 作为目标 dp。 不会发生默认缩放。high-dpi – 使用hdpi 作为目标 dpi。 中等像素密度和低像素密度设备相应缩小。medium-dpi – 使用mdpi作为目标 dpi。 高像素密度设备相应放大， 像素密度设备相应缩小。 这是默认的target density.low-dpi -使用mdpi作为目标 dpi。中等像素密度和高像素密度设备相应放大。<value> – 指定一个具体的dpi 值作为target dpi. 这个值的范围必须在70–400之间。为了防止Android Browser和WebView 根据不同屏幕的像素密度对你的页面进行缩放，你可以将viewport的target-densitydpi 设置为 device-dpi。当你这么做了，页面将不会缩放。相反，页面会根据当前屏幕的像素密度进行展示。在这种情形下，你还需要将viewport的width定义为与设备的width匹配，这样你的页面就可以和屏幕相适应。
initial-scale初始缩放。即页面初始缩放程度。这是一个浮点值，是页面大小的一个乘数。例如，如果你设置初始缩放为“1.0”，那么，web页面在展现的时候就会以target density分辨率的1:1来展现。如果你设置为“2.0”，那么这个页面就会放大为2倍。
maximum-scale最大缩放。即允许的最大缩放程度。这也是一个浮点值，用以指出页面大小与屏幕大小相比的最大乘数。例如，如果你将这个值设置为“2.0”，那么这个页面与target size相比，最多能放大2倍。
user-scalable用户调整缩放。即用户是否能改变页面缩放程度。如果设置为yes则是允许用户对其进行改变，反之为no。默认值是yes。如果你将其设置为no，那么minimum-scale 和 
maximum-scale都将被忽略，因为根本不可能缩放。所有的缩放值都必须在0.01–10的范围之内。例：(设置屏幕宽度为设备宽度，禁止用户手动调整缩放) < meta name="viewport" content="width=device-width,user-scalable=no" />(设置屏幕密度为高频，中频，低频自动缩放，禁止用户手动调整缩放)< meta name="viewport" content="width=device-width,target-densitydpi=high-dpi,initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no"/>另外，[iOS](http://lib.csdn.net/base/ios) 7.1的Safari为meta标签新增minimal-ui属性，在网页加载时默认隐藏地址栏与导航栏。

###浏览器乱码的原因是什么？如何解决
你的网页没有设置meta charset编码造成的，导致浏览器不能识别你网页默认编码类型。   解决方法：在浏览器中找到转换编码的菜单。
1.  IE9浏览器出现网页乱码，在需要转码的网页空白处右键鼠标，即可选择编码，
2.  谷歌浏览器中浏览需要转码的网页时，点击工具-->编码即可。
###常见的浏览器有哪些，什么内核
常见的 内核基本是一下4种：

#### Trident：

这是微软开发的一种排版引擎。该内核程序在1997年的IE4中首次被采用，是微软在Mosaic代码的基础之上修改而来的，并沿用到目前的 IE7。Trident实际上是一款开放的内核，其接口内核设计的相当成熟，因此才有许多采用IE内核而非IE的浏览器涌现（如 Maxthon、The World 、TT、GreenBrowser、AvantBrowser等）。此外，为了方便也有很多人直接简称其为IE内核（当然也不排除有部分人是因为不知道内 核名称而只好如此说，至少老N就是如此。。。）。自从发布后，Trident不断地被更新和完善：

Trident II（IE5）——增进对CSS1.0的支持及对CSS2重大的变更；

Trident III（IE5.5）——修正部分CSS的排版控制；

Trident IV（IE6）——修正了一部分box-model的错误以及增加了“兼容模式（Quirks Mode）”切换功能，以增加对文件类型描述（Document Type Definition，DTD）的支持；

Trident V（IE7）——修正许多CSS排版处理上的错误以及增加对PNG格式alpha通道（半透明）的支持。（这就是IE6经常被诟病的对png图片支持不良的之处！）

####Geckos：

Gecko是套开放源代码的、以C++编写的网页排版引擎。这软件原本是由网景通讯公司开发的，Netcape6开始采用该内核。后来的 Mozilla FireFox也采用了该内核，Geckos的特点是代码完全公开，因此，其可开发程度很高，全世界的程序员都可以为其编写代码，增加功能。Geckos 现在由Mozilla基金会维护。

####Presto：

Presto是一个由Opera Software开发的浏览器排版引擎，该内核在2003年的Opera7中首次被使用，该款引擎的特点就是渲染速度的优化达到了极致，也是目前公认网页浏览速度最快的浏览器内核。

####Webkit：

苹果公司自己的内核，也是苹果的Safari浏览器使用的内核。 Webkit引擎包含WebCore排版引擎及JavaScriptCore解析引擎，均是从KDE的KHTML及KJS引擎衍生而来，它们都是自由软 件，在GPL条约下授权，同时支持BSD系统的开发。所以Webkit也是自由软件，同时开发源代码。在安全方面不受IE、Firefox的制约，所以 Safari浏览器在国内还是很安全的。

简单的总结一下：

使用Trident内核的浏览器：IE、Maxthon、TT、The World等；

使用Gecko内核的浏览器：Netcape6及以上版本、FireFox、MozillaSuite/SeaMonkey；

使用Presto内核的浏览器：Opera7及以上版本；

使用Webkit内核的浏览器：Safari、Chrome。

###常见的标签及应用场景

* < a> 用于超链接。< a href="">some text< /a>
* <article> 用于一篇文章。<article>a self-contained article</article>
* <aside> 用于页面的侧边栏。<aside>some content</aside>
* < blockquote> 用于大段的引用内容。< blockquote>some big texts</blockquote>
* <body> 页面上显示的所有内容都被包含在<body></body>里
* < br> 用于显示一个换行
* < button> 用于显示一个按钮
* < code> 用于一包裹一段代码内容
* < dd> 用于一个dl列表的某个dt名词的描述
* < del > 用于删除一些不需要的文字
* < div> 用于包裹住一些其他的标签，制造一个容器
* < dl> 用于制作一个名词和对应解释的列表
* < dt> 用于一个dl列表的某个dt名词
* < em> 用于强调一些文本内容
* < figcaption> 用于一张图表的说明文字
* < figure> 用于一张图表
* < footer> 用于包裹页面的底部内容
* < form> 用于制作一个表单
* < h1 > - < h6 > 用于标记标题，从h1到h6重要性依次递减
* < head> 用于包裹页面的元数据，如< meta>, < link>, < title>等
* < header> 用于包裹页面的头部内容
* < hr> 用于制造出一条分隔线
* < html> 整个 HTML 文档的根元素，包裹住其他所有的元素
* < iframe> 用于嵌入另一个小页面到一个页面中
* < img> 用于显示一张图片
* < input> 用于显示一个表格输入控件
* < label> 用于给一个表格输入控件打上一个标签，说明输入控件的作用
* < li > 用于< ul >和< ol >标签，代表一个列表项
* < link> 用于链接外部CSS文件
* < mark> 用于高亮显示某些文本
* < meta> 用于下达一些元数据指令，或者对页面进行说明
* <  nav> 用于包裹住一个导航条的内容
* < ol> 用于制作一个有序列表
* < p> 用于显示一个段落
* < q> 用于一小段引用文字
* < script> 用于一段JavaScript脚本代码，或者引入一个外部JavaScript脚本文件
* < section> 用于包裹一部分有逻辑关第的页面内容
* < select> 用于制作一个下拉列表选框
* < span> 用于包裹住一小段文字，作为一个容器
* < strong> 用于着重强调重要的文本内容
* < style> 用于给页面元素加上样式
* < sub> 用于下标文本
* < sup> 用于上标文本
* < table> 用于制作一个表格
* < tbody> 用于表格里的主体部分
* < td> 用于表格里的某一个单元格
* < textarea> 用于制作一大块文本输入框
* < tfoot> 用于表格里的底部
* < th> 用于表格里的表头的单元格
* < thead> 用于表格里的表头
* < time> 用于页面内容中的时间
* < title> 用于显示整个页面的标题（显示在浏览器的tab上）
* < tr> 用于标记表格里的一行
* < ul> 用于制作一个无序列表
    
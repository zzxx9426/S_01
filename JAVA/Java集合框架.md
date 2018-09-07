集合框架被设计成要满足以下几个目标。  
* 该框架必须是高性能的。基本集合（动态数组，链表，树，哈希表）的实现也必须是高效的。
* 该框架允许不同类型的集合，以类似的方式工作，具有高度的互操作性。
* 对一个集合的扩展和适应必须是简单的。  
为此，整个集合框架就围绕一组标准接口而设计。  
Java集合框架主要包括两种类型的容器，一种是集合（Collection），储存一个元素集合，另一种是图（Map），存储键/值对映射。Collection接口又有3种子类型，List、Set和Queue，再下面是一些抽象类，最后是具体实现类，常用的有ArrayList、LinkedList、HashSet、LinkedHashSet、Hashmap、LinkedHashMap等等。  
集合框架是一个用来带边和操纵集合的同一框架。所有的集合框架都包含如下：  
* 接口： 是代表集合的抽象数据类型。例如Collection、List、Set、Map等。之所以定义多个接口，是为了以不同的方式操作集合对象。
* 实现（类）：是集合接口的具体实现。从本质上讲，它们是可重复使用的数据结构，例如：ArrayList、LinkedList、HashSet、HashMap。  
* 算法：是实现集合接口的对象里的方法执行的一些有用的计算，例如：搜索和排序。这些算法被称为多态，那是因为相同的方法可以在相似的接口上有着不同的实现。    
除了集合，该框架也定义了集合Map接口和类。Map里储存的是键/值对。尽管Map不是集合，但是他们完全整合在集合中。
![](https://github.com/zzxx9426/S_01/blob/master/myPicture/JAVA/%E9%9B%86%E5%90%88%E6%A1%86%E6%9E%B6%E4%BD%93%E7%B3%BB.png?raw=true)  
Java集合提供了一套性能优良，使用方便的接口和类，java集合框架位于java.util包中，所以使用集合框架的时候需要进行导包。  
## 集合接口 
集合框架定义了一些接口。  
```
1. Collection接口 
  COllection是最基本的集合接口，一个Collection代表一组Object，即Collection的元素，Java不提供直接继承自Collection的类，只提供继  承于的子接口（List和set）。  
  Collection接口储存一组不唯一，无序的对象。  
2. List接口 
   List接口是一个有序的Collection，使用此接口能够精确的控制每个元素插入的位置，能够通过索引（元素在List中的位置，类似于数组的下表）来访问List中的元素，第一个元素的索引为0，而且允许有相同的元素。  
   List接口储存一组不唯一，有序（插入顺序）的对象。  
3. Set  
   Set具有与Collection完全一样的接口，只是行为上不同，Set不保存重复的元素。  
   Set接口储存一组唯一，无序的对象。  
4. SortedSet  
   继承于Set保存有序的集合。  
5. Map  
   Map接口储存一组键值对象，提供key（键）到value（值）的映射。  
6. Map.Entry  
   描述在一个Map中的一个元素（键/值对）。是一个Map的内部类。

7. SortedMap  
继承于Map，使 Key 保持在升序排列。  
8. Enumeration  
这是一个传统的接口和定义的方法，通过它可以枚举（一次获得一个）对象集合中的元素。这个传统接口已被迭代器取代。  

```

###Set和List的区别
* 1. Set接口实例储存的是无序的，不重复的数据。List接口实例储存的是有序的，可以重复的元素。  
* 2. Set检索效率低下，删除和插入效率高，插入和删除不会引起元素位置改变<实现类有HashSet，TreeSet>。  
* 3. List和数组类似，可以动态增长，根据实际储存的数据的长度自动增长List的长度。查找元素效率高，插入删除效率低，因为会引起其他元素位置改变<实现类有ArrayList，LinkedList,Vector>. 

### 集合实现类（集合类）  
Java提供了一套实现Collection接口的标准集合类。其中一些事具体类，这些类可以直接拿来使用，而另外一些是抽象类，提供了接口的部分实现。  
标准集合类汇总：  
![](https://github.com/zzxx9426/S_01/blob/master/myPicture/JAVA/%E6%A0%87%E5%87%86%E9%9B%86%E5%90%88%E6%B1%87%E6%80%BB.png?raw=true)  
java.util类  
![]()
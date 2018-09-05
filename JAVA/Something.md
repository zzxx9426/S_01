Java Character 用于对单个字符进行操作。  
Character类在对象中包装一个基本类型char的值。
// 字符数组 
char[] charArray = {'a','b','c'};  
Character类提供了一系列方法来操作字符。可以使用Character类对象：  
> Character ch = new Character('a');  
将一个char类型的参数传递给需要一个Character类型参数的方法时，那么编译器自动地将char类型参数转换为Character对象，这种特征称为装箱，反过来称为拆箱。  
Character ch = 'a'; // 原始字符‘a’ 装箱到Character 对象ch 中  
char c = test('x');
// 原始字符‘x’ 用test方法装箱  
// 返回拆箱的值到'c' 

Java StringBuffer和StringBuilder类 
当对字符串进行修改的时候，需要使用StringBuffer和StringBuilder类。  
和String类不同的，StringBuffer和StringBuilder类的西乡能够被多次的修改，并且不产生新的未使用对象。  
StringBuilder类在Java 5中被提出，它和StringBuffer之间的最大不同在于StringBuilder的方法不是线程安全的（不能同步访问）。  
由于StringBuilder相较于StringBuffer有速度优势，所以多数情况下建议使用StringBuilder类。然而在应用程序要求线程安全的情况下，则必须使用StringBuffer类。

### Java equals()  

## Java/类与对象 
Java是一门面向对象的变成语言，除了基本数据类型以外，Java要求每个数据类型必须都是一个类。  
面向对象的变成思想力图使在计算机语言中对事物的描述与现实世界中该事物的本来面目尽可能地一致，类（class）和对象（object）就是面向对象方法的核心概念。  

## Java封装

在面向对象程式设计方法中，封装是指一种将抽象性函式接口的实现细节部分包装、隐藏起来的方法。  
封装可以被认为是一个保护屏障，防止该类的代码和数据被外部类定义的代码随机访问。  
要访问该类的代码和数据，必须通过严格的接口控制。  
封装最主要的功能在于我们能修改自己的实现代码，而不用修改那么调用我们代码的程序片段。  
适当的封装可以让程式码更容易理解与维护，也加强了程式码的安全性。  
利用抽象数据类型将数据和基于数据的操作封装在一起，
## 封装的优点
* 1. 良好的封装能够减少耦合。
* 2. 类内部的结构可以自由修改。
* 3. 可以对成员变量进行更精确的控制。
* 4. 隐藏信息，实现细节。
###  修饰符 
在面向对象的过程中，我们通过权限控制对封装好的类加上权限，来限制外来者对类的操纵，借以达到保障类中数据和方法的安全的目的。  
Java中修饰符分别为public、protected、default、private。（我们要尽量让权限降到最低，从而让安全性提高。）  
如果没有在属性前面添加任何修饰符，默认是default权限，我们通过创建对象就可以直接对属性值进行修改，没有体现封装的特性。这在程序设计中是不安全的，所以我需要利用封装。  

## 实现Java封装的步骤
1. 修改属性的可见性类限制对属性的访问（一般限制为private）。  
public class Person {  
    private String name;  
    private int age;
}  
2. 对每个值属性提供对外的公共方法访问，也就是创建一对赋取值方法，用于对私有属性的访问。  
public class Preson{  
    private String name;  
    private int age;

    public int getAge(){  
        return age;  
    }

    public String getName(){  
        return name;  
    }  

    public void setAge(int age){  
        this.age = age;  
    }  

    public void setName(String name){  
        this.name = name;  
    }  
}  
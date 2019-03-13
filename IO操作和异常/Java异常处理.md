### 异常  
Java提供了丰富的异常处理机制，与C语言相同，Java的异常处理也就是包含在try，catch，finally三个块中的，常见的异常处理方式：  
 try{  
       //可能产生异常的代码  
 }catch(IOException e){  
  //IOExceptioin为输出输入异常，当产生的异常被捕捉后，该处代码将被执行  
 }finally{  
   //无论异常产生与否，该处代码始终将被执行  
 }  

 如果在**程序**中需要抛出异常，应使用throw关键字：  
 if(!file.exists()){  
     throw new FileNotFoundException ("file not found");
 }  
 **方法**里抛出异常，应使用关键字throws：  
 public void get() throws Exception{  

 }  

### 异常类  
Java提供了专门的异常类，所有的异常类均应是java.lang.Throwble的子类。其中，主要分为两大子类：  
1. java.lang.Error:其子类表示了Java虚拟机的异常  
2. java.lang.Exception：其子类表示了程序运行中的异常  

Exception的子类还可分为两类：  
1. java.lang.RuntimeException：其子类表示了运行中的异常，该异常可以不被catch，编译器也能通过。该子类表示的异常，均应该在源代码中避免，比如数组范围的超出等等。  
2. 非RuntimeException：其子类表示了程序中不可避免的异常，如文件不存在的FileNotFoundException异常，该异常必须被catch掉或者是在函数头处声明。  

### Assert
从1.4版本开始，java支持了assert关键字对异常的处理。一般形式如下：  
assert布尔表达式；  
assert布尔表达式：字符串或表达式；  
该语句表示，如果布尔表达式的值为假，则抛出AssertionError异常，如果采取第二种形式，则以后面的字符串或表达式的返回值作为构造器的输入参数。该语句表达了，程序断言此处布尔表达式为真，否则将会出错。但在一般情况下，assert语句将被程序忽略掉，除非在java运行时指定。  
形式如下：  
java-ea MainApp  
这个命令行参数-ea打开了assert断言机制，而默认的情况是关闭的。  
不同普通的Exception异常，assert断言一般是作为调试信息用的。比如，作为java包的设计者，对于包中private或包访问限制的函数中所进行的判断，就可以使用assert断言作为额外的调试信息。而对于public和protected访问限制的函数，其中的判断就应该用Exception异常，因为这些函数是面向用户的。

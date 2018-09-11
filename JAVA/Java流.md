## Java流（ Stream）、文件（File）和IO  
Java.io包几乎包含了所有操作输入、输出需要的类。所有这些流类代表了输入源和输出目标。  
Java.io包中的流支持很多种格式，比如：基本类型、对象、本地化字符集等。  
一个流可以理解为一个数据的序列。输入流表示从一个源读取数据，输出流表示向一个目标写数据。  
Java为I/O提供了强大的而灵活的支持，使其更广泛地应用到文件传输和网络编程中。  

## 读取控制台输入 
Java的控制台输入由System.in完成。  
为了获得一个绑定到控制台的字符流，你可以把System.in包装在一个BufferedReader对象中来创建一个字符流。  
创建BufferedReader的基本语法：  
BufferedReader br = new BufferedReader(  
    InputStreamReader(System.in));  
BufferedReader对象创建后，我们便可以使用read()方法从控制台读取一个字符，或者用readLine()方法读取一个字符串。  

## 从控制台读取多字符输入  
从BufferReader对象读取一个字符要使用read()方法，语法如下：  
int read() throws IOException   
每次调用read()方法，它从输入流读取一个字符，或者用readLine()方法读取一个字符串。  
## 从控制台读取多字符输入 
从BufferedReader对象读取一个字符要使用read()方法：   
> int read() throws IOException  
每次调用read()方法，它从输入流读取一个字符并把该字符作为整数值返回。当流结束的时候返回-1.该刚发抛出IOException。  

##  从控制台读取字符串  
从标准输入读取一个字符串需要使用BufferedReader 的 readLine()方法。  
> String readLine() throws IOException  


## 控制台输出 
控制台的输出由print()和println()完成。这些方法都由类PrintSteam定义，System.out是该类对象的一个引用。  
PrintStream继承了OutputStream类，并且实现了方法write().这样，write()也可以用来往控制台写操作。  
PrintStream定义write()的最简单格式：  
void write(int byteval) //该方法将byteval的低 八位字节写到流中。  

## FileInputStream  
该流用于从文件读取数据，它的对象可以用关键字new来创建。  
有多种构造方法可以用来创建对象。  
可以使用字符串类型的文件名来创建一个输入流对象来读取文件：  
InputStream f = new FileInputStream("c:/java/hello");  
也可以使用一个文件对象来创建一个输入流对象来读取文件。我们首先得使用File()方法来创建一个文件对象：  
File f = new File("c:/java/hello");  
InputStream out = new FileInputStream(f);  


public void close() throws IOException{}  
关闭此文件输入流并释放与此流有关的所有系统资源。抛出IOException异常。  
protected void finalize() throws IOException{}  
这个方法清除与该文件的链接。确保在不再引用文件输入流时调用其close方法。抛出IOException异常。  
public int read(int r) throws IOException{}  
这个方法从输入流读取r.length长度的字节。返回读取的字节数。如果是文件结尾则返回-1.  
public int available() throws IOException{}  
返回下一次对此输入流调用的方法可以不受阻塞地从此输入流读取的字节数。返回一个整数值。  

## FileOutputStream  
该类用来创建一个文件并向文件中写数据。  
如果该流在打开文件进行输出前，目标文件不存在，那么该流会创建该文件。  
有两个构造方法可以用来创建FileOutputStream对象。  
使用字符串类型的文件名来创建一个输出流对象：  
OutoutStream f = new FileOutoutStream("C:/java/hello")  
也可以使用一个文件对象来创建一个输出流来写文件。我们首先得使用File()方法来创建一个文件对象：  
File f = new File("C:/java/hello");  
OutoutStream f = new FileOutoutStream(f);  

## 文件和I/O  


## Java中的目录 
### 创建目录： 
File类中有两个方法可以用来创建文件夹：  
* mkdir()方法创建一个文件夹，成功则返回true，失败则返回false。失败表明File对象制定的路径已经存在，或者由于整个路径还不存在该文件夹不能被创建。  
* mkdirs()方法创建一个文件夹和它的所有父文件夹。  

## 读取目录 
一个目录其实就是一个File对象，它包含其他文件和文件夹。  
如果创建一个File对象并且它是一个目录，那么调用isDirectory()方法会返回true。  
可以通过调用该对象上的list()方法，来提取它包含的文件和文件夹的列表。  

## 删除目录和文件  
删除文件可以使用java.io.File.delete()方法。  

# java-study
java进阶知识点总结
###JDK 和 JRE 的区别
JRE：java运行时环境，包含了java虚拟机，java基础类库。是使用java语言编写的程序运行所需要的软件环境。  
JDK：java开发工具包，是编写java程序所需的开发工具。JDK包含了JRE，同时还包含了编译器javac，调试和分析工具，JavaDoc。

###自动装箱与拆箱 autoboxing and unboxing
自动装箱是 Java 编译器在基本数据类型和对应的对象包装类型之间做的一个转化。
比如：把 int 转化成 Integer，double 转化成 Double等,反之就是自动拆箱。  
[Java中的自动装箱与拆箱](http://droidyue.com/blog/2015/04/07/autoboxing-and-autounboxing-in-java/index.html)
###Java 创建对象的几种方式
(1) 用 new 语句创建对象，这是最常见的创建对象的方法  
(2) 运用反射手段,调用 java.lang.Class 或者 java.lang.reflect.Constructor 类的 newInstance() 实例方法  
(3) 调用对象的 clone() 方法  
(4) 运用反序列化手段，调用 java.io.ObjectInputStream 对象的 readObject() 方法

(1)和(2)都会明确的显式的调用构造函数；(3)是在内存上对已有对象的影印，所以不会调用构造函数 (4)是从文件中还原类的对象，也不会调用构造函数。

###序列化与反序列化
对象序列化(Serializable)是指将对象转换为字节序列的过程，而反序列化则是根据字节序列恢复对象的过程。    
序列化一般用于以下场景：   
1.永久性保存对象，保存对象的字节序列到本地文件中；   
2.通过序列化对象在网络中传递对象；    
3.通过序列化在进程间传递对象。   

只有实现了Serializable和Externalizable接口的类的对象才能被序列化，   
java.io.ObjectOutputStream代表对象输出流，它的writeObject(Objectobj)方法可对参数指定的obj对象进行序列化，把得到的字节序列写到一个目标输出流中。
java.io.ObjectInputStream代表对象输入流，它的readObject()方法从一个源输入流中读取字节序列，再把它们反序列化为一个对象，并将其返回。

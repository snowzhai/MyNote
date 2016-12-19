

## 1." "和null 的区别

    ""指分配了内存但还没有写入值
    null指还没有分配内存空间
## 2.如何判断是否为奇数

    正常判断  
    public boolean oddOrNot(int num) {
        return num % 2 == 1;
    }
    解决上面无法判断负数的问题 并进行了计算数据的优化  
    public boolean oddOrNot(int num) {
        return (num & 1) != 0;//用& 的方法 转换成2进制 只有相同位上都为1才为1 这样只有末尾是1 才返回true 不论是正数还是负数
    }
    
## 3.位运算符

    位运算符主要针对二进制，它包括了：“与”、“非”、“或”、“异或”。从表面上看似乎有点像逻辑运算符，但逻辑运算符是针对两个关系运算符来进行逻辑运算，而位运算符主要针对两个二进制数的位进行逻辑运算。下面详细介绍每个位运算符。
    1．与运算符
    与运算符用符号“&”表示，其使用规律如下：
    两个操作数中位都为1，结果才为1，否则结果为0，例如下面的程序段。
    public class data13
    {
    public static void main(String[] args)
    {
    int a=129;
    int b=128;
    System.out.println("a 和b 与的结果是："+(a&b));
    }
    }
    运行结果
    a 和b 与的结果是：128
    下面分析这个程序：
    “a”的值是129，转换成二进制就是10000001，而“b”的值是128，转换成二进制就是10000000。根据与运算符的运算规律，只有两个位都是1，结果才是1，可以知道结果就是10000000，即128。
     
    2．或运算符
    或运算符用符号“|”表示，其运算规律如下：
    两个位只要有一个为1，那么结果就是1，否则就为0，下面看一个简单的例子。
    public class data14
    {
    public static void main(String[] args)
    {
    int a=129;
    int b=128;
    System.out.println("a 和b 或的结果是："+(a|b));
    }
    }
    运行结果
    a 和b 或的结果是：129
    下面分析这个程序段：
    a 的值是129，转换成二进制就是10000001，而b 的值是128，转换成二进制就是10000000，根据或运算符的运算规律，只有两个位有一个是1，结果才是1，可以知道结果就是10000001，即129。
     
    3．非运算符
    非运算符用符号“~”表示，其运算规律如下：
    如果位为0，结果是1，如果位为1，结果是0，下面看一个简单例子。
    public class data15
    {
    public static void main(String[] args)
    {
    int a=2;
    System.out.println("a 非的结果是："+(~a));
    }
    }
     
    4．异或运算符
    异或运算符是用符号“^”表示的，其运算规律是：
    两个操作数的位中，相同则结果为0，不同则结果为1。下面看一个简单的例子。
    public class data16
    {
    public static void main(String[] args)
    {
    int a=15;
    int b=2;
    System.out.println("a 与 b 异或的结果是："+(a^b));
    }
    }
    运行结果
    a 与 b 异或的结果是：13
    分析上面的程序段：a 的值是15，转换成二进制为1111，而b 的值是2，转换成二进制为0010，根据异或的运算规律，可以得出其结果为1101 即13。
## 4.列出目录下的文件    

    你可以用下面的代码来列出目录下的文件。这个程序会遍历某个目录下的所有子目录及文件，并存储到一个数组里，然后通过遍历数组来列出所有文件。
    public class ListContents {
        public static void main(String[] args) {
            File file = new File("//home//user//Documents/");
            String[] files = file.list();
            System.out.println("Listing contents of " + file.getPath());
            for(int i=0 ; i < files.length ; i++)
            {
                System.out.println(files[i]);
            }
        }
    }
## 5.static 关键字

    被static修饰的成员,可以理解为这些成员是与类相关的,通过 类名.成员 的形式调用 
    没有被static修饰的成员,可以理解为这些成员是与对象相关的,通过 对象名.成员 的形式调用
     
    注意：在被static修饰的方法中不能调用没有static修饰的方法和属性
## 6.instanceof关键字

    instanceof属于Java中的二元操作符  和==  > 等操作符类似
    a instanceof b 当a是b指定的类型或者是子类型的时候返回true 否则返回false
## 7.int 和 Integer什么区别

    int是基本的数据类型     为方便Java保留 int(Integer),short(Short),long(Long),byte(Byte),float(Float),double(Double),char(Character),boolean(Boolean)等8个基本类型
    基本类型不具备面向对象的基本特征，没有方法和属性。 封装类型属于引用类型，具有方法和属性 利用封装类型可以完成基本类型不能完成的工作 例如：将数值转换成字符串
    float a=3.4f;
    float a=(float)3.4;
## 8.x=x+y 和 x+=y 的区别

    short s=3;
    s+=1;//通过
    s=s+1;//不同过
    x+=y 想当与 x=x+y 和强制转两个操作
## 9.toString().trim().toUpperCase();

    trim   获得对象的字段的值，然后转成string类型，并且去掉前后空白~~
    toUpperCase     是把字符串中的字母转换成大写
    String s=str.replaceAll(" ",""); 替换中间的空格
## 10.Java中的序列化和反序列化
[孤傲沧浪博客的介绍][1]

    对象的序列化主要有两种用途：
    1.把对象的字节序列永久地保存到硬盘上，通常存放在一个文件中
    2.在网络上传送对象的字节序列
## 11.Java中的反斜杠

    String s="1";
    String s="\"1" 通过反斜杠来实现可能引起歧义字符的转义  
    对于 ， 等也要用到 否则会使字符串打断格式
## 12.String 型转为Int型

    String s="100";
    Integer a=Integer.parseInt(s);
    //String 的分割
    String s="java,c,php,c++";
    String ssString[]=s.split(",");
    for (String string : ssString) {
        System.err.println(string);
    }
## 13.内部类和外部类

    //外部类访问内部类的函数
    public class testString {
        String out="他是谁!";
    	public static void main(String[] args) {
    		testString t=new testString();
    	    String string=t.new Test().testgetstring("who are you?");
    	    System.err.println(string);
	    }
	    public class Test{
		    String	testgetstring(String s){
		        return s+"你是谁"+out;//内部类默认拥有外部类的访问权限
		    }
	    }
    }

## 14.instanceof

    content instanceof Activity  
    instanceof是Java中的二元运算符，判断左边的对象会否是右边的实例，如果是的话，返回true，不是的话，返回false。
    上面说的是判断content是否来源于Activity（也可能来源于application或者是service）。

## 15.hashmap的使用

[网址][2]

## 16.关于for循环

	continue为跳出本次循环，执行后面的循环
    break 为终止循环
    对于两层 循环 break 只是跳出当层循环，不会跳出双层循环

## 17. string 中split的用法

	String[] split (String regex, int limit)
	The string "boo:and:foo", for example, yields the following results with these parameters:

    Regex	Limit	Result
    :	2	{ "boo", "and:foo" }
    :	5	{ "boo", "and", "foo" }
    :	-2	{ "boo", "and", "foo" }
    o	5	{ "b", "", ":and:f", "", "" }
    o	-2	{ "b", "", ":and:f", "", "" }
    o	0	{ "b", "", ":and:f" }







  [1]: http://www.cnblogs.com/xdp-gacl/p/3777987.html
  [2]: http://blog.csdn.net/kaituozhe345/article/details/6843130
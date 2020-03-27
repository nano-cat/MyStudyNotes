# Java核心技术

## 1.1 类基础知识

* 一个java文件只能有一个公共类public class, 且类名必须与文件名相同
* 一个文件可以有多个类class, 但是只有一个是公共的public

### 1.1.1 class 类

* **类是java中最基础的逻辑单位** (java项目就是由一个个类组成的)
  * java中所有的内容都需要放在类的范围中
  * 内容不允许游离在类以外
* 类的构成 (**类包括成员变量和成员方法**)
  * 成员变量/属性 member variables
  * 成员方法/函数 member functions
* 类的基本结构:
  * 属性: 对象数据的描述
  * 构造方法: 用于实例化对象
  * 方法: 对象的行为
  * 内部类: 在类中声明的类(inner class)
  * 块: 静态块和实例块

### 1.1.2 main函数

* 一个class最多只能有一个main函数. 类可以没有main函数(不会主动执行, 但可以被调用执行)
* 程序的入口都是main函数, **main函数是一个java程序的总入口(起点)**
* main函数写法固定 public static void main(String[] args){}
* java要求所有程序都必须放在类对象中, 即所有代码都要放在class管辖范围内
* 严格来说, main函数并不属于这个类所拥有的函数, 只是因为要求所有内容都必须放在class内, main是"寄居"
* main函数的形参args是外界提供给mian函数的参数, 可以在main函数中使用

### 1.1.3 基本类型

* java总共提供了8种基本类型
  - boolean   布尔
    - 只有 true 和 false 两种值, 默认是 false  (不能赋值0和1)
  - byte          字节
    - 储存有符号的整数 -128~127默认0, 占用空间只有int的四分之一
  - short / int / long   短整数 / 整数 / 长整数
  - float /  double       浮点数
    - float类型赋值需要加f,不加默认为double, 整数可以直接转为float不需要加f
  - char          字符
    - 占用2个字节

### 1.1.4 运算符

* `+` , `-` , `*` , `/` , `%`
  * b=i++ (先赋值后++)    b=++i  (先++后赋值)
* 逻辑运算符与或非 `&&` ,  `||` , `!` 
* 比较运算符 `!=` , `>` , `>=` , `<` , `<=` , `==`
* 移位运算符`<<`,  `>>` 
  * 左移和右移n位相当于 × 和 ÷ 2^n , 位移运算可以代替这样的乘除操作, 但是不代表这两者是一样的, 

### 1.1.5 选择结构和循环结构

* 选择结构 if(表达式) { } else if(表达式) { } else { }

* 多重选择结构 switch(表达式){case 条件: 语句; break; default : 语句;}

* 循环结构 

  * while(表达式) { }
  * do { } while(表达式)
    * break;跳出当前循环(离break最近的循环)
    * continue;结束当前循环,继续下一次循环

  * for (初始条件; 循环检测条件; 循环后更新计数器) { }
  * **递归: 重复调用自身**
  * 迭代: 循环的结果作为初始值继续参与循环

### 1.1.6 自定义函数

* 函数必须放在类的范围内
* 必须有 修饰词(public 或者static) 返回值(int 或者void), 函数名(形参列表){函数体}
* **重载overload: 函数重载是函数名相同, 形参列表必须有所不同**
* 调用: 
  * 非静态函数需要声明一个类实例, 通过实例调用
  * 静态函数可以直接调用(不会浪费内存), 也可以通过实例调用
  * 

## 1.2 面向对象

### 1.2.1 对象

* 每个对象有自己的特有属性, 也有自己专有的方法
* 对象 = 属性 + 方法
* 对象的规范 = 属性定义 + 方法定义
* **类是规范**, 定义, 类规定了对象应有的属性内容和方法
* **对象是根据规范产生的实例**, 是类的一个实现, 根据类的定义构造出来
* A obj = new A();
  * obj可以看作是内存中一个对象(包含若干个数据)的句柄
  * 在C/C++中, obj称为指针, 在java中称为Reference
  * **对象赋值是Reference赋值, 而基本类型是直接拷贝**
* **函数类的局部变量**, 编译器不会给默认值, **需要初始化**后才可使用
* **类的成员变量**, 编译器会给**默认值**, 可直接使用

### 1.2.2 构造函数/构造方法

* java构造函数的名称必须和类名一样, 且**没有返回值**
* 每个变量都是有生命周期的, 它只能储存在离他最近的一对 {} 中
* 当变量被创建时, 变量将占据内存; 当变量消亡时, 系统将回收内存

* **每个java类都必须有构造函数**
  * 如果没有显式定义构造函数, java编译器自动为该类产生一个空的无形参构造器
  * 每个子类的构造函数的第一句话, 都默认调用父类的无参数构造函数super(), 除非子类的构造函数第一句话是super, 而且放在第一条
* **一个类可以有多个构造函数,** 只要形参列表不相同即可
* 构造函数是一个对象初始化的过程

### 1.2.3 信息隐藏和this指针

* 面向对象有一个法则: 信息隐藏
  * 类的成员属性, 是私有的private
  * 类的方法是公有的public, 通过方法修改成员属性的值
* this负责指向本类中的成员变量和成员方法
  * this.add(5); //调用本类的add方法, this可忽略
* this可以当作构造函数使用
  * this(m, n); //



## 1.3 继承 接口 和抽象类

### 1.3.1 继承 extends

* 子类继承父类门所有的东西(但是不能直接访问private成员)

* 本类方法会比父类优先级高
* java单根继承原则: 每个类都只能继承一个类
* 如果不写extends, **java类都默认继承java.lang.Object类**
* java所有类从java.lang.Object开始, 构建出一个类型继承树
* **子类构造函数默认第一句话都会去调用父类的无参构造函数** ( 编译器会默认在子类的每个构造函数里添加super(); ), 除非显示使用super

### 1.3.2 抽象类 abstract

* 类可以没有方法, 但是一个完整(健康)的类: 所有的方法都有实现(方法体)
* 一个完整的类才可以被实例化, 被new出来
* 如果一个类暂时有方法未实现, 需要被定义为抽象类
* 抽象类: 若方法只有方法名字, 形参列表, 没有方法体, 那所在的类就被定义为抽象类
* abstract类无法被实例化(被new出来)
* 抽象类也是类, 一个类继承于抽象类, 就不能继承与其他的类和抽象类
* 子类可以继承于抽象类, 但是**一定要实现父类们所有的abstract的方法**, 如果不能完全实现, 那么子类也必须被定义为抽象类

### 1.3.3 接口 interface

* 如果类的所有方法都没有实现, 那么这个类就算是接口interface
* 类只可以继承(extends)一个类, 但是可以**实现(implements)**多个接口, 继承和实现可以同时
* **类实现接口必须实现所有未实现的方法**, 如果没有全部实现, 那么只能成为一个抽象类
* 接口不算类, 或者说是 "特殊" 的类
* **接口可以继承(多个)接口**, 没有实现的方法将会叠加
* 接口可以定义变量, 但是一般是常量
* 继承多个接口, 相当一将多个接口中未实现的方法都"继承"过来

### 1.3.4 抽象类和接口

* 抽象类和接口的相同点: 都不能被实例化, 不能new操作
* 不同点:
  * 抽象类可以有部分方法实现, 接口的所有方法都不能有实现
  * 一个类 只能继承一个抽象类, 但是可以实现多个接口
  * 抽象类有构造函数, 接口没有构造函数
  * 抽象类可以有main函数, 可以独立运行, 接口不可以有main函数
  * 抽象类方法可以有private/protected, 接口方法都是public

### 1.3.5 转型 多态和契约设计

#### 1.3.5.1 类转型

* 变量支持互相转化, 比如int a = (int) 3.5
* 类型可以相互转型, 但是只限制于有继承关系的类
  * **子类可以转换为父类(向上转型), 而父类不可以转为子类(向下转型)**
  * 父类强制转换为子类会 抛出 ClassCastException 异常

#### 1.3.5.2 多态

* 多态是同一个行为具有多个不同表现形式或形态的能力.(同一个事件发生在不同的对象上会产生不同的结果)

* 子类继承父类的所有方法, 但子类可以重新定义一个名字参数和父类一样的方法, 这种行为就是重写(覆写,覆盖, overwrite/override)

* 子类的方法的优先级高于父类

* 多态的作用

  * 以统一的接口来操纵某一类中不同的对象的动态行为
  * 对象之间的解耦

#### 1.3.5.3 契约设计

  * 契约: 规定规范了对象应该包含的行为方法
  * 接口定义了方法的名称 参数和返回值, 规范了派生类的行为
  * 基于接口, 利用转型和多态, 不影响真正方法的调用, 成功将调用类和被调用类解耦(decoupling)

### 1.3.6 我遇到的问题和理解

#### ① 隐式调用造成的报错问题

```java
	//为什么下面的程序会报错 ?  
class A {	
    A(int n){ /*语句*/ }		
}
class B extends A {		
    B(int n){/*语句*/}	
    PSVM{A a = new B(5)} //PSVM缩写代指public static void main(String[] args)
}	/*因为 创建对象时会调用构造函数B(int n), 又因为子类B继承于父类A, 
    该构造函数会隐式调用父类A的无参构造函数A(), 而因为已经定义过有参构造函数A(int n)
    所以编译器不会自动生成A(), 导致缺少A()报错 */
```
#### ② 隐藏的构造函数造成的程序执行顺序的理解问题

```java
	//下面程序输出是什么?  
class C {
    C(){ Sys.o.p("C") } //缩写
}
class D extends C {
    //D(){super();} 
    PSVM{new D(); new C();}
}	/*输出是 C C  ; 把编译器会补全的代码注释出来就能看懂为什么了
	*/
```

#### ③ 子类强转父类时子类方法被隐藏造成的问题

```java
	//为什么有错?  
class E {
    public void func1(){ }
    public void func2(){ }	}
class F extends E{
    public void func1(){ }  //a.func1();调用的是子类方法!
    public void func3(){ }	}
class G {
    PSVM{ E a = new F()
        a.func1(); a.func2(); a.func3();}	}
	/*因为 子类F继承于父类E 而E a = new F()将子类向上转型为父类, 
	子类里的func3()相当于被隐藏了, 所以func3()对于类型E来说未定义*/
```

#### ④ 子类和父类转换时, 对象指针问题

```java
class Father { }
public class Child extends Father { }
child a = new Child();
Father b = (Father)a;
Child c = (Child)b;
sys.o.p( a == b );	//true	子类转换为父类, 其指针值一般不会变
sys.o.p( a == c );	//true
```

#### ⑤ 同一父类的两个子类之间是否能够转换

* 不能 , 直接提示 cannot cast from a to b.



## 1.4 static ,  final和常量设计

### 1.4.1 静态的 static

* 可以用在
  * 变量 / 方法 / 类 / 匿名方法
* 静态变量 
  * **静态变量是 类共有成员**
  * static变量只依赖于类存在, 不需要实例对象即可访问
  * 所有的对象实例 static变量的值都**共享储存在一个共同的空间(栈)中**
* 静态方法 Static Method
  * 静态方法无需通过对象来引用, 而通过类名可以直接引用
    * 不能用类名访问非静态方法
  * 在**静态方法**中, 只能使用静态变量,**不能使用非静态变量**
  * 静态方法禁止引用非静态方法 (非静态方法可以调用静态方法)
* 静态代码块
  * 只在类第一次被加载时调用 (换句话说就是在程序运行期间这段代码只运行一次
  * **执行顺序:** static块 > 匿名块 > 构造函数

### 1.4.2 单例模式

* 单例模式, 又名单态模式, 属于创建型模式

  * 限定某一个类在整个程序运行的过程中, 只能保留一个实例对象在内存空间
  * 保证一个类有且只有一个对象
    * 采用static来共享对象实例
    * 采用private使构造函数私有化, 防止外界new操作

* ```java
  public class A {
      private static A a = new A(); //共享同一个对象
      private int x;
      private A(){ this.x = 1} //确保只能在类内部调用构造函数
      public static A getInstance(){
          return obj;
      }
      PSVM{ A obj1 = A.getInstance();}	//无法new A
  }
  ```

### 1.4.3 final

* 可以用来修饰
  * 类 / 方法 / 字段
* final的类, 不能被继承
* 父类中如果有final的方法, 子类中不能改写此方法
* final的变量, 不能再次赋值
  * 如果是基本型别的变量, 不能修改其值
  * 如果是对象实例, 那么不能修改其指针(地址)

### 1.4.4 常量设计

* ```java
  public static final double PI_NUMBER = 3.14; //常量建议全大写,以连字符相连
  ```

* 接口内定义的变量默认是常量 (默认会补全缺省public static final)

* Java为很多基本类型的包装类/字符串都监理常量池(相同的值只存储一份,节省内存,共享访问

  * 基本类型的包装类
    * Boolean : true, false
    * Byte, Character : \u0000 - \u007f ( 0 - 127)
    * Short, Integer, Long : -128 ~ 127
    * Float, Double : 没有缓存(常量池)
  * **自动装箱:** 基本数据类型, 直接变成对象
  * **自动拆箱:** 对象中的数据变回基本数据类型
  * 自动装箱拆箱的好处: 基本类型和引用类型能够直接进行运算

### 1.4.5 不可变对象和字符串

* 不可变对象Immutable Object (八个基本类型的包装类 / String, BigInteger和BigDecimal等)
  * 一旦创建, 这个对象(状态/值)不能被更改
  * 其内在的成员变量的值也不能更改了
  * **不可变对象提高 读效率**
* 字符串是java使用最多的类, 是一种典型的不可变对象
  * 字符串内容比较: equals方法
  * 是否指向同一个对象: 指针比较 ==

### 1.4.6 我遇到的问题和解释

#### ① 静态代码块, 匿名代码块, main函数, 类构造函数 他们的执行顺序

```java
class A { // [6]. 但因为 static块 > 匿名块 > 构造函数, 所以先执行匿名块
    static {	sys.o.p("a");	}	// [2]. 在同一类中static代码块优先于main执行(只会执行一次)
   	{	sys.o.p("b");	} // [7]. 执行匿名块, 然后执行隐藏的无参构造函数, 再回到子类
    PSVM{  // [1]. 执行main函数时 首先会加载class A 
        A a = new B();	// [4]. 实例化对象B
        A b = new A();	} // [8].实例化对象A 执行匿名块
}
class B extends A{	// [5]. 隐式调用父类无参构造函数
    static {	sys.o.p("c");	}	// [3]. 子类静态代码块依然优先于main执行....(没想到啊!)
}  /*所以结果是 a c b b ; ps:在多个类中,main函数优先于静态代码块执行*/
```
#### **② 堆和栈**的简单理解

* **通俗来说, 堆主要是用来存放对象的, 栈主要是用来执行程序的**

* 在函数中定义的一些基本类型变量和对象的引用变量都在函数的栈内存中分配
* 堆内存用来存放有new创建的对象和数组

#### ③ 三种 字符串加法操作的时间比较

```java
public static void main(String[] args) {
		int n = 50000;
		Calendar t1 = Calendar.getInstance();
		String a = new String();	//非常慢,结果3740ms, 因为每次相加操作都会产生新的对象, 效率很差
		for(int i = 0; i<n ; i++) {
			a = a + i + ",";
		}
		System.out.println(Calendar.getInstance().getTimeInMillis() - t1.getTimeInMillis());
		
		Calendar t2 = Calendar.getInstance();
		StringBuffer b = new StringBuffer("");	//修改快速, 结果5ms, 同步 线程安全
		for (int i =0; i<n ; i++) {
			b.append(i);
			b.append(",");
		}
		System.out.println(Calendar.getInstance().getTimeInMillis() - t2.getTimeInMillis());
		//StringBuffer初始分配空间16个字节, 当字符长度超过分配长度时分配空间会加一并翻倍, 如果添加的字符串很长超过了(加一翻倍的)空间, 则会以最新的长度更换
		Calendar t3 = Calendar.getInstance();
		StringBuilder c = new StringBuilder(""); //修改最快, 结果2ms, 不同步 线程不安全
		for (int i =0; i<n ; i++) {
			c.append(i);
			c.append(",");
		}
		System.out.println(Calendar.getInstance().getTimeInMillis() - t3.getTimeInMillis());
	}
```

#### ④ 变量默认值和初始化问题

* 类变量(实例变量) 有默认值, 可以不初始化
  * boolean **(false)** 
  * char **(\u0000)** 
  * byte,short,int,long **(0)** ; float,double **(0.0)** 
  * String **(null)**
* 局部变量(定义在方法/块中的变量) 没有默认值, 必须初始化, 才能使用
  * The local variable i may not have been initialized

## 1.5 package, import和classpath 以及权限访问

- Java程序分布式放置和调用问题

### 1.5.1 package

* 放在同一个目录下的java类无需显示声明调用
* package机制是为了防止命名冲突, 访问控制, 提供搜索和定位类 接口等

### 1.5.2 import

* 用import来引入类, 可以有多条
* import必须全部放在package后面, 类定义的前面

### 1.5.3 classpath

* ```cmd
  X> javac -classpath ".;c:\m1;c:\m2" c:\m3\com\example\a.java	//编译
  X> java -classpath ".;c:\m1;c:\m2;c:\m3" com.example.a			//运行
  ```

### 1.5.4 jar文件的导入和导出

* 导出方法 : 
  * 在编写好的java包上 右键 -> export -> 选择 JAR file ->Browse导出位置
* 导入方法: 
  * 右键项目 -> New - Folder新建文件夹 lib -> 将jar包拖入lib ->
  * 再次右键项目 -> Properties ->  Java Build Path -> Libraries -> Add External JARs...

### 1.5.5 java访问权限

* java访问权限有4种:
  * private : 私有的, 只能本类访问
  * default(忽略不写) : 同一个包内访问(同一个package)
  * protected : 同一个包, 子类均可访问
  * public : 公开的, 所有的类都可以访问

* 四种都可以用来修饰成员变量, 成员方法, 构造函数

* default 和 public 可以修饰类

* |           | 同一个类 | 同一个包 | 不同包的子类 | 不同包的非子类 |
  | --------- | -------- | -------- | ------------ | -------------- |
  | private   | √        |          |              |                |
  | default   | √        | √        |              |                |
  | protected | √        | √        | √            |                |
  | public    | √        | √        | √            | √              |



## 1.6 Java 常用类

### 1.6.1 java类库

* 包名以java开始的包是Java核心包

* 包名以javax开始的包是Java扩展包

#### 常用包

| 软件包        | 描述                                                         |
| ------------- | ------------------------------------------------------------ |
| java.applet   | Applet 是一种 Java 程序。它一般运行在支持 Java 的 Web 浏览器内。因为它有完整的 Java API支持,所以Applet 是一个全功能的 Java 应用程序。 |
| java.awt      | 包含用于创建用户界面和绘制图形和图像的所有类。               |
| java.beans    | 使用Javabeans的好处是解决代码重复编写，功能区分明确，提高了代码的可维护性, 通常在jsp页面中使用 |
| java.io       | 通过数据流, 对象序列以及文件系统实现的系统输入输出(同步)     |
| java.lang     | 提供java编程语言设计至关重要的类                             |
| java.math     | 提供任意精度整数和十进制运算的类                             |
| java.net      | 提供实现网络通讯应用的类                                     |
| java.nio      | 面向缓冲区操作, 用来提升效率(异步)                           |
| java.rmi      | 提供与远程方法调用相关的类                                   |
| Java.security | 提供设计网络安全方案需要的类                                 |
| java.sql      | 访问和处理储存在数据源(通常是关系型数据库)中的数据的API      |
| java.text     | 提供用于以独立于自然语言的方式处理文本，日期，数字和消息的类和接口 |
| java.time     | 日期，时间，瞬间和持续时间的主要API                          |
| java.util     | 包括集合类, 时间处理模式, 日期时间工具等各类常用的工具包     |

* 说实话API文档看得头都大了, 我做了个思维导图, 用来记录和方便回忆自己用过的API吧

* JAVA API [思维导图链接](https://www.processon.com/mindmap/5e7c6017e4b092510f7828c4)

### 1.6.2 数字相关类

#### java数字类

##### BigInteger (大整数类)

* ```java
  //import java.math.BigInteger;
  BigInteger b1 = new BigInteger("123456789");	//声明BigInteger对象
  BigInteger b2 = new BigInteger("987654321");
  sys.o.p( b2.add(b1) );			//加法操作
  sys.o.p( b2.subtract(b1) );		//减法操作
  sys.o.p( b2.multiply(b1) );		//乘法操作
  sys.o.p( b2.divide(b1) );		//除法操作
  sys.o.p( b2.max(b1) );			//求最大值
  sys.o.p( b2.min(b1) );			//求最小值
  BigInteger result[] = b2.divideAndRemainder(b1);//求商和余数,并赋值数组初始元素和最后一个元素 (即[0]和[1])
  sys.o.p( b1.equals(b2) );		//等价性判断
  int flag = b1.compareTo(b2);	//比较判断 b1<b2则值为-1 =则为0 >则为1
  ```

##### BigDecimal (大小数类)

* ```java
  //在同一个package下, 方法类似
  BigDecimal b1 = new BigDecimal("1234.4321");
  //赋值为了精准 尽量采用字符串赋值 (传入floatdouble不精确)
  sys.o.p( b2.divide(b1, 10, BigDecimal.ROUND_HALF_UP) );
  //除法操作需要定位, 防止无限循环 指定位数10位,舍入模式 四舍五入
  ```

### 1.6.3 字符串相关类

#### String类

* java中使用频率最高的类

* ```java
  String a = "123;456;789;123 ";
  System.out.println(a.charAt(0));//返回第一个元素 : 1
  System.out.println(a.indexOf(";"));//返回第一个;的位置 : 3
  System.out.println(a.concat(";000"));//连接一个新字符并返回,a不变 : 123;456;789;123 ;000
  System.out.println(a.contains("000"));//判断a是否包含000 : false
  System.out.println(a.endsWith("000"));//判断a是否以000结尾 : false
  System.out.println(a.equals("000"));//判断是否等于000	: false
  System.out.println(a.equalsIgnoreCase("000"));//判断在忽略大小写情况下是否等于000 : false
  System.out.println(a.length());//返回a的长度 : 16
  System.out.println(a.trim());//返回a去除前后空格的字符串,a不变 : 123;456;789;123
  String[] b = a.split(";");//将a字符串按照 ; 分割成数组
  for (int i = 0; i < b.length; i++) {
  	System.out.print(b[i] + " ");
  } //123 456 789 123
  System.out.println(a.substring(2, 5));//截取a的第二个到第五个字符 a不变 : 3;4
  System.out.println(a.replace("1", "a"));// a23;456;789;a23
  System.out.println(a.replaceAll("a", "1"));//第一个参数是正则表达式
  ```



## 1.6 Java 异常和异常处理

### 1.6.1 异常

* 程序不正常的行为或者状态
* 异常分为
  * Error : 系统内部错误或者资源耗尽
  * Exception : 程序有关的异常
    * RuntimeException : 程序自身的错误
      * Unchecked Exception : 编译器不会辅助检查的, 需要程序员自己预防处理
    * 非RuntimeException : 外界相关的错误
      * Checked Exception : 编译器会辅助检查

### 1.6.2 异常处理

* 让程序返回到安全的状态

* 抓住异常, 分析异常内容

#### try - catch - finally 捕获异常

  * try必须有, catch和finally至少要有一个)

  * try : 正常业务逻辑代码
    
    * try的内部也可以写一个完整的try-catch/finally结构(不能try里只有try没catch/finally)
    
  * catch : 当try发生异常, 将执行catch代码, 若无异常, 则不执行
    * catch块可以有多个, 每个有不同的入口形参, 如果发生的异常与某一个catch块形参类型一致, 那么将执行该catch块, 如果都不匹配则不会触发catch,最后进入finally块
    * 进入catch块后, 并不会再返回到try发生的异常的位置, 也不会执行后续的catch块, 一个异常只能进入一个catch块
    * 异常的匹配是从上到下, 一般小异常写在前面, 大(宽泛)的异常写在后面
    
  * finally : 当try或catch执行结束后, finally块肯定会被执行

  * ```java
    try { 		try-catch-finally }
    catch { 	try-catch-finally }
    finally {	try-catch-finally }
    ```

  * 捕获多种异常

      * 如果某些异常的处理逻辑相同, 但是异常本身不存在继承关系, 我们可以把它两用`|`合并到一起

      * ```java
        catch (IOException | NumberFormatException e) {}
        ```

#### throws 抛出异常

* 方法存在可能异常的语句, 但不处理, 那么可以使用throws来声明异常
* 调用带有throws异常 (checked exception)的方法, 要么处理异常, 或者再次向外 throws, 直到main函数为止
* 一个方法被覆盖, 覆盖它的方法必须抛出相同的异常, 或者异常的子类
* 如果父类的方法抛出多个异常, 那么重写子类方法必须抛出那些异常的子集, 也就是不能抛出新的异常

### 1.6.3 自定义异常

* Exception类是所有异常的父类 , 继承自java.lang.Throwable

* Java标准库定义的常用异常

* ```ascii
  Exception
  │
  ├─ RuntimeException
  │  │
  │  ├─ NullPointerException
  │  │
  │  ├─ IndexOutOfBoundsException
  │  │
  │  ├─ SecurityException
  │  │
  │  └─ IllegalArgumentException
  │     │
  │     └─ NumberFormatException
  │
  ├─ IOException
  │  │
  │  ├─ UnsupportedCharsetException
  │  │
  │  ├─ FileNotFoundException
  │  │
  │  └─ SocketException
  │
  ├─ ParseException
  │
  ├─ GeneralSecurityException
  │
  ├─ SQLException
  │
  └─ TimeoutException
  ```

* 可以自定义新的异常类型，但是，保持一个合理的异常继承体系是非常重要的

* 一个常见的做法是自定义一个`BaseException`作为“根异常”，然后，派生出各种业务类型的异常。`BaseException`需要从一个适合的`Exception`派生，通常建议从`RuntimeException`派生：

* ```java
  public class BaseException extends RuntimeException {}
  public class UserNotFoundException extends BaseException {}
  public class LoginFailedException extends BaseException {}
  ```

* 自定义的`BaseException`应该提供多个构造方法

* ```java
  public class BaseException extends RuntimeException {
      public BaseException() {	super();	}
      public BaseException(String message, Throwable cause) {
      						    super(message, cause);	}
      public BaseException(String message) {	super(message);	}
      public BaseException(Throwable cause) {	super(cause);	}
  }
  ```

## 1.7 Java数据结构类

### 1.7.1 数组

* 数组是一个存放多个数据的容器

  * 数据是同一种类型, 线性规则排列
  * 可通过索引快速定位访问数据, 需明确容器长度

* 数组不能越界访问, 否则会报ArrayIndexOutOfBoundsException异常

* 数组的遍历: 两种方法

* ```java
  int[] d = new int[]{0,2,4};
  for (int i=0 ; i<d.length ; i++) {}
  for (int e : d ) {}
  ```

### 1.7.2 JCF 集合框架(容器类)

* 容器: 能够存放数据的空间结构
* 容易框架: 为表示和操作容器而规定的一种标准体系结构
  * 对外的接口: 容器中能够存放的抽象数据类型
  * 接口的实现: 可复用的数据结构
  * 算法: 对数据的查找和排序
* 容器框架的优点: 提高数据存取效率, 避免重复劳动

### 1.7.3 List 列表

* ArrayList (非同步, 以可变数组形式实现的列表)
  * 利用索引位置可以快速定位访问 (主要用于经常查询的数据)
  * 不适合指定位置的插入删除操作
* LinkedList (非同步, 以双向链表形式实现的列表)
  * 顺序访问/插入删除操作高效, 随机访问性能较差
  * 适用于经常变化的数据
* Vector (同步, 和ArrayList类似)
  * 适合多线程下使用, 否则优先使用ArrayList

### 1.7.3 集合接口 Set

* 确定性: 对任意对象都能判定其是否属于某一个集合
* 互异性: 集合内每个元素都是不相同的, 注意是内容互异
* 无序性: 集合内的顺序无关
* Java中的集合接口Set:
  * HashSet (基于散列函数的集合, 无序, 不支持同步)
  * TreeSet (基于树结构的集合, 可排序的, 不支持同步)
  * LinkedHashSet (基于散列函数和双向链表的集合, 可排序的, 不支持同步)
* 判断重复元素
  * HashSet和LinkedSet: 先判定两个元素的hashCode, 在判定equals方法, 两个都位true时判定相同
  * TreeSet: 需要元素继承自Comparable接口, 比较两个元素的compareTo方法

### 1.7.4 映射Map

* Map映射:
  * 数学定义: 两个集合之间的元素对应关系
  * 一个输入对应到一个输出
  * {Key, Value}键值对
* Java中的Map
  * Hashtable (同步, 慢, 数据量小)
  * HashMap (不支持同步, 快, 数据量大)
  * Properties (同步, 数据量小, 可以将K-V对保存在文件中)
  * LikedHashMap (基于双向链表的维持插入顺序的HashMap)
  * TreeMap (基于红黑树的Map, 可以根据key的自然排序或者compareTo方法进行排序输出)

## 1.8 Java文件的读写

### 1.8.1文件基本操作

* java.io.File 类 (File类不涉及文件里面的内容)
  * createNewFile 创建一个新文件
  * delete 删除文件
  * exists 判断文件是否存在
  * mkdirs 创建多级目录
  * isDirectory / isFile 判断是否是目录 / 文件
  * getName 获取文件名
  * getParent / getPath 获取上级目录 / 全路径
  * lastModified 返回文件最后一次修改时间(毫秒)
  * listFiles 获取目录下所有的子文件(不包括子目录下的)

* java.nio.file.Path 
  * 1
* java.nio.file.FileSystems.getDefault() 用来得到当前系统的FileSystem

### 遇到的问题

#### ① 如何理解链式调用

* 在学习io包的时候遇到了很多链式调用, 比如

* ```java
  Path path = FileSystems.getDefault().getPath("c:/temp", "abc.txt");
  ```

  这是之前学习中没有接触的, 刚开始很费解为什么要这样写, 这是如何实现的

* 原来, 一般而言, 初学的时候我们接触到的方法返回值都是一个基本类型或者干脆是void, 而链式调用的关键就是这个返回值的不同

* 代码的返回值又是一个必要的步骤, 直接返回void好像很浪费, 所以我们见到的很多方法的返回值都是自身( return this; ), 这就是链式调用实现的关键

* 这个逻辑就很明了了: 对象调用自身的方法, 调用完返回的是当前对象本身, 上个方法返回的对象又是下一个调用方法的执行对象, 就这样依次调用就形成了链式调用...



***

### 未完待更

***

<table class="reference">
<tbody><tr>
<th>类别</th>
<th>关键字</th>
<th>说明</th>
</tr>
<tr>
<td rowspan="3" align="center">访问控制</td>
<td>private</td>
<td>私有的</td>
</tr>
<tr>
<td>protected</td>
<td>受保护的</td>
</tr>
<tr>
<td>public</td>
<td>公共的</td>
</tr>
<tr>
<td rowspan="13" align="center">类、方法和变量修饰符</td>
<td>abstract</td>
<td>声明抽象</td>
</tr>
<tr>
<td>class</td>
<td>类</td>
</tr>
<tr>
<td>extends</td>
<td>扩充,继承</td>
</tr>
<tr>
<td>final</td>
<td>最终值,不可改变的</td>
</tr>
<tr>
<td>implements</td>
<td>实现（接口）</td>
</tr>
<tr>
<td>interface</td>
<td>接口</td>
</tr>
<tr>
<td>native</td>
<td>本地，原生方法（非 Java 实现）</td>
</tr>
<tr>
<td>new</td>
<td>新,创建</td>
</tr>
<tr>
<td>static</td>
<td>静态</td>
</tr>
<tr>
<td>strictfp</td>
<td>严格,精准</td>
</tr>
<tr>
<td>synchronized</td>
<td>线程,同步</td>
</tr>
<tr>
<td>transient</td>
<td>短暂</td>
</tr>
<tr>
<td>volatile</td>
<td>易失</td>
</tr>
<tr>
<td rowspan="12" align="center">程序控制语句</td>
<td>break</td>
<td>跳出循环</td>
</tr>
<tr>
<td>case</td>
<td>定义一个值以供 switch 选择</td>
</tr>
<tr>
<td>continue</td>
<td>继续</td>
</tr>
<tr>
<td>default</td>
<td>默认</td>
</tr>
<tr>
<td>do</td>
<td>运行</td>
</tr>
<tr>
<td>else</td>
<td>否则</td>
</tr>
<tr>
<td>for</td>
<td>循环</td>
</tr>
<tr>
<td>if</td>
<td>如果</td>
</tr>
<tr>
<td>instanceof</td>
<td>实例</td>
</tr>
<tr>
<td>return</td>
<td>返回</td>
</tr>
<tr>
<td>switch</td>
<td>根据值选择执行</td>
</tr>
<tr>
<td>while</td>
<td>循环</td>
</tr>
<tr>
<td rowspan="6" align="center">错误处理</td>
<td>assert</td>
<td>断言表达式是否为真</td>
</tr>
<tr>
<td>catch</td>
<td>捕捉异常</td>
</tr>
<tr>
<td>finally</td>
<td>有没有异常都执行</td>
</tr>
<tr>
<td>throw</td>
<td>抛出一个异常对象</td>
</tr>
<tr>
<td>throws</td>
<td>声明一个异常可能被抛出</td>
</tr>
<tr>
<td>try</td>
<td>捕获异常</td>
</tr>
<tr>
<td rowspan="2" align="center">包相关</td>
<td>import</td>
<td>引入</td>
</tr>
<tr>
<td>package</td>
<td>包</td>
</tr>
<tr>
<td rowspan="8" align="center">基本类型</td>
<td>boolean</td>
<td>布尔型</td>
</tr>
<tr>
<td>byte</td>
<td>字节型</td>
</tr>
<tr>
<td>char</td>
<td>字符型</td>
</tr>
<tr>
<td>double</td>
<td>双精度浮点</td>
</tr>
<tr>
<td>float</td>
<td>单精度浮点</td>
</tr>
<tr>
<td>int</td>
<td>整型</td>
</tr>
<tr>
<td>long</td>
<td>长整型</td>
</tr>
<tr>
<td>short</td>
<td>短整型</td>
</tr>
<tr>
<td rowspan="3" align="center">变量引用</td>
<td>super</td>
<td>父类,超类</td>
</tr>
<tr>
<td>this</td>
<td>本类</td>
</tr>
<tr>
<td>void</td>
<td>无返回值</td>
</tr>
<tr>
<td rowspan="3" align="center">保留关键字</td>
<td>goto</td>
<td>是关键字，但不能使用</td>
</tr>
<tr>
<td>const</td>
<td>是关键字，但不能使用</td>
</tr>
<tr>
<td>null</td>
<td>空</td>
</tr>
</tbody></table>




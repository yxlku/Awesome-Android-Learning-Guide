#1.你创建一个类的时候，什么时候选择类、内部类、静态内部类、匿名内部类？设计框架时该如何选择？
  - 内部类允许把一些逻辑相关的类组织到一起,并控制位于内部的类的可见性.内部类隐式持有外部类的引用,可以直接访问外部类成员(内部类之所以能够获取外部类成员还是因为他能够获取到外部类的引用),外部类成员访问内部类成员,必须创建对象.创建内部类必须通过其外部类对象去创建.**内部类常用来隐藏一些不想向外提供的细节操作,即内部类具有封装性,使用内部类可以使代码更加优雅清晰)**
  - 静态内部类是声明为static的内部类,不再持有外部类的引用.创建静态内部类不再需要通过其外部类对象,而静态内部类不再可以直接访问外部类的费静态成员变量.
  - 匿名内部类是内部类的简化写写法,但是匿名内部类的前提是存在一个相应的类或者接口,其本质是继承了该类或者实现了改接口的子类的匿名对象.**在实际开发中常作为参数传递.**
  - **内部类与接口结合起来,解决了Java不能多继承的问题.**

#2.你什么时候会创建一个抽象类，为什么不用接口？设计框架时该如何选择？
  - 当需要强制子类总写某个方法时,需要创建抽象类.
  - 接口和内部类为我们提供了一种将接口与实现分离更加结构化的方法.
  - 抽象类被继承体现的是"is a"的关系,抽象类中定义的是该继承体系的共性功能.
  - 接口被实现体现的是"like a"的关系,接口中定义的是该继承体系的扩展功能.

#3.类的成员变量修饰符有哪些？ public protected private 怎么选，什么时候用 final 修饰，什么时候会用 static 的？
  - private,protect,public属于权限修饰符
  - final,static属于状态修饰符
  - private,protect,public允许外部访问的的范围一致递增.private修饰的成员变量只能在本类中访问,默认权限修饰符的成员变量只能在同一包下访问,protect可以允许不同包下子类访问,public修饰的成员变量范围最广,不同包下无关类也可以使用.
  - final修饰成员变量,只能赋值一次.
  - static修饰的成员变量称为静态变量,存储于方法区,可以直接通过`类名.变量名`调用.

#4.什么时候会发生自动装箱拆箱？有什么需要注意的吗？
  - 装箱:把基本数据类型转换为对象(`Integer a = new Integer(10)`)
    拆箱:把对象转为基本数据类型(`int b = a.intValue()`)
    自动装箱与自动拆箱是从JDK5开始出现的新特性
  - 如:`Integer a = 100`,此时自动装箱
         `int b = a + 200`,此时自动拆箱(在自动拆箱时,会调用`a.intValue()`方法)

#5.注解是什么？有几种类型？什么时候用注解？
  - 注解为我们在代码中添加信息提供了一种形式化的方法,使我们可以在稍后某个时刻非常方便地使用这些数据.
  - 注解主要分为标准注解,元注解,自定义注解.
  - 注解常用于作为标记高数编译器信息,或者编译时动态处理,运行时动态处理信息.
 
#6.反射是什么？什么时候用反射？
  - 反射是在运行时动态获取类的信息以及动态调用对象的方法的Java语言机制.
  - 在编译时对于类的内部信息不可知,需要通过运行时才能获取类的具体信息时,需要使用反射.

#7.泛型使用在什么场景，你有写过使用泛型的代码吗？
  - 当类中要操作的引用数据类型不确定的时候,推荐使用泛型来完成拓展.
#8.异常有几种类型，OOM 属于哪种？
  - Java中异常被分为两大类:编译时异常和运行时异常
  - 编译时异常:Java程序必须显式处,否则程序报错,无法通过编译
  - 运行时异常:无需显式处理,也可以和编译时异常一起处理,所有`RuntimeException`类及其子类的实例被称为运行时异常
  - OOM属于运行时异常
#9.集合你一般使用哪些？列表、哈希表都有哪些实现，优劣清楚吗？
  **集合分为Colletion(单列集合),Map(双列集合)两大类,**其继承体系如下:
  - Colletion(根接口)
        List(存取顺序一致,有索引,可以存储重复元素)
       　　ArrayList:底层数据结构是数组,查询快,增删慢,效率高,线程不安全.
       　　LinkedList:底层数据结构是链表,查询慢,增删快,线程不安全,效率高.
       　　Vector:底层数据结构是数组,查询快,增删慢,线程安全,效率低.
        Set(存取顺序不一致,无索引,不可存储重复元素)
       　　HashSet(哈希算法)
       　　TreeSet(二叉树算法)
  - Map(根接口)
        HashMap(哈希算法,针对key)
        TreeMap(二叉树算法,针对key)

#10.IO 你一般怎么用？
  - IO流一般用于数据传输或者数据持久化
  - IO流按流向分可分为输入流和输出流,按操作类型可分为字节流和字符流.
  - 字节流可以操作任何数据.
  - 字符流只能操作纯字符数据.
#11.String 
String是被final修饰的引用数据类型,一旦被赋值,就不能被改变.底层用Char数组实现,String用自己的常量优化机制,创建一个字符串对象时,如果常量池中没有该对象,就创建一个,如果有将直接使用常量池中的对象.



# JAVA  基础

------

[TOC]

------



# 一 基本语法

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020111407.png)

## 注释



## 标识符

1. 由字母、数字、下划线（_）和美元符号($)组成
2. 不能以数字开头
3. 不能是关键字



## 关键字

1.  const goto 是保留关键字
2. true false null 不属于关键字，是一个单独的标识类型



## 运算符



### 常量

1. 整型常量
   - 二进制 0B 0b
   - 八进制 0开头
   - 十进制
   - 十六进制 0x 0X
2. 浮点型常量
   - 单精度 以F或f结尾
   - 双精度 以D或d结尾
3. 字符常量
   - 单引号‘ ’括起来
4. 字符串常量
   - 双引号“”引起来
5. 布尔常量
   - true
   - false
6. null 常量
   - 表示对象的引用为空



## 选择结构



## 循环结构

九九乘法表

```java
for (int i=1;i<=9;i++){
    for(int j=1;j<=9;j++) {
        if (i >= j) {
            System.out.print(j + "*" + i +" = " + i * j + "  ");
        }
    }
    System.out.println();
}

```

打印三角形

```java
//打印等边三角形 参数 n是行数
int n=4;
for(int i=1;i<=n;i++){
    for (int k=1; k <=n-i; k++) {
        System.out.print(" ");
    }
    for (int k =1; k <= 2*i-1 ; k++) {
        System.out.print("*");
    }
    System.out.println();
}

```

打印正方形

```java
//打印正方形 参数 n
 n=4;
for(int i=1;i<=n;i++){
    for(int j=1;j<=n;j++){
        if(i==1 || i==n ) {//第一行和最后一行打印星号
            System.out.print("*");
        }else if(j==1 || j==n ){//第一列和最后一列打印星号
            System.out.print("*");
        }else{
            System.out.print(" ");
        }
    }
    System.out.println();
}

```



# 二 变量

## 变量的数据类型

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020102524.png)

## 变量的类型转换

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020110911.png)



## 变量和常量的区别



# 三 面向对象

面向对象的特征（继承，封装，多态）。

面向对象是把构成问题的事务按一定规则划分为多个对象，然后通过调用对象的方法解决问题。

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020113940.png)

## 类与对象

类是对象的抽象，用于描述一组对象的共同特征和行为。其中成员变量用于描述对象的特征，也称为属性；成员方法用于描述对象的行为，简称为方法。

 对象是类的实例。

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020114301.png)

### 作用域——访问控制

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020114219.png)

### 构造方法与垃圾回收

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020114419.png)

### this static 关键字

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020114755.png)



## 继承

 ![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020115111.png)



## 抽象类

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020115308.png)



## 接口

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020115449.png)



注意

1. 接口的方法都是抽象的，不能实例化对象
2. 接口中的属性只能是常量
3.  当一个类实现接口时，如果这个类是抽象类，则实现接口的部分方法即可，否则需要实现接口中的所有方法
4. 一个类通过implements实现接口时，可以实现多个接口，被实现的多个接口之间用逗号隔开
5. 一个接口可以通过extends继承多个接口，接口之间用逗号隔开

## 多态

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020115657.png)

## 异常

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020115718.png)

# 四 集合

## java集合框架图

![img](https://www.runoob.com/wp-content/uploads/2014/01/2243690-9cd9c896e0d512ed.gif)

从上面的集合框架图可以看到，

Java 集合框架主要包括两种类型的容器，一种是集合（Collection），存储一个元素集合，另一种是图（Map），存储键/值对映射。

Collection 接口又有 3 种子类型，List、Set 和 Queue，再下面是一些抽象类，最后是具体实现类，常用的有 [ArrayList](https://www.runoob.com/java/java-arraylist.html)、[LinkedList](https://www.runoob.com/java/java-linkedlist.html)、[HashSet](https://www.runoob.com/java/java-hashset.html)、LinkedHashSet、[HashMap](https://www.runoob.com/java/java-hashmap.html)、LinkedHashMap 等等。

集合框架是一个用来代表和操纵集合的统一架构。所有的集合框架都包含如下内容：

- **接口：**是代表集合的抽象数据类型。例如 Collection、List、Set、Map 等。之所以定义多个接口，是为了以不同的方式操作集合对象
- **实现（类）：**是集合接口的具体实现。从本质上讲，它们是可重复使用的数据结构，例如：ArrayList、LinkedList、HashSet、HashMap。
- **算法：**是实现集合接口的对象里的方法执行的一些有用的计算，例如：搜索和排序。这些算法被称为多态，那是因为相同的方法可以在相似的接口上有着不同的实现。

除了集合，该框架也定义了几个 Map 接口和类。Map 里存储的是键/值对。尽管 Map 不是集合，但是它们完全整合在集合中。



![img](https://www.runoob.com/wp-content/uploads/2014/01/java-coll.png)

Java 集合框架提供了一套性能优良，使用方便的接口和类，java集合框架位于java.util包中， 所以当使用集合框架的时候需要进行导包。

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201016224459.jpg)

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201021063645.png)

## **结论**

- 如果是集合类型，有List和Set供我们选择。

  List的特点是插入有序的，元素是可重复的。Set的特点是插入无序的，元素不可重复的。

  至于选择哪个实现类来作为我们的存储容器，我们就得看具体的应用场景。是希望可重复的就得用List，选择List下常见的子类。是希望不可重复，选择Set下常见的子类。

- 如果是`Key-Value`型，那我们会选择Map。如果要保持插入顺序的，我们可以选择LinkedHashMap，如果不需要则选择HashMap，如果要排序则选择TreeMap。

## List



### 2 ArrayList

ArrayList 类是一个可以动态修改的数组，与普通数组的区别就是它是没有固定大小的限制，我们可以添加或删除元素。

ArrayList 继承了 AbstractList ，并实现了 List 接口。

![img](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020115826.png)

ArrayList 类位于 java.util 包中，使用前需要引入它，语法格式如下：

```
import java.util.ArrayList; // 引入 ArrayList 类

ArrayList<E> objectName =new ArrayList<>();　 // 初始化
```

- **E**: 泛型数据类型，用于设置 objectName 的数据类型，**只能为引用数据类型**。

### ArrayList的创建

面试官：“那我们本身就有数组了，为什么要用ArrayList呢？”

三歪：“原生的数组会有一个特点：你在使用的时候必须要为它创建大小，而ArrayList不用”

面试官：“那你说说ArrayList是怎么实现的吧，为什么ArrayList就不用创建大小呢？”

三歪：“其实是这样的，**我看过源码**。当我们`new ArrayList()`的时候，默认会有一个空的`Object`数组，大小为0。当我们**第一次**`add`添加数据的时候，会给这个数组初始化一个大小，这个大小默认值为10”

```java
private static final int DEFAULT_CAPACITY = 10;
public ArrayList() {
        this.elementData = DEFAULTCAPACITY_EMPTY_ELEMENTDATA;
    }
/**
     * The array buffer into which the elements of the ArrayList are stored.
     * The capacity of the ArrayList is the length of this array buffer. Any
     * empty ArrayList with elementData == DEFAULTCAPACITY_EMPTY_ELEMENTDATA
     * will be expanded to DEFAULT_CAPACITY when the first element is added.
     */
    transient Object[] elementData; // non-private to simplify nested class access

    /**
     * The size of the ArrayList (the number of elements it contains).
     *
     * @serial
     */
    private int size;
```

面试官：“嗯”

### ArrayList存取元素

ArrayList集合中的大部分方法是从父类Collection和List继承过来的，其中add()和get()方法用于元素的存取。

- 使用ArrayList在每一次`add`的时候，它都会先去计算这个数组够不够空间，如果空间是够的，那直接追加上去就好了。如果不够，那就得扩容”

```java
// Positional Access Operations

    @SuppressWarnings("unchecked")
    E elementData(int index) {
        return (E) elementData[index];
    }

    /**
     * Returns the element at the specified position in this list.
     *
     * @param  index index of the element to return
     * @return the element at the specified position in this list
     * @throws IndexOutOfBoundsException {@inheritDoc}
     */
    public E get(int index) {
        rangeCheck(index);

        return elementData(index);
    }
/**
     * Checks if the given index is in range.  If not, throws an appropriate
     * runtime exception.  This method does *not* check if the index is
     * negative: It is always used immediately prior to an array access,
     * which throws an ArrayIndexOutOfBoundsException if index is negative.
     */
    private void rangeCheck(int index) {
        if (index >= size)
            throw new IndexOutOfBoundsException(outOfBoundsMsg(index));
    }
```

- get()方法，首先查看下标是否越界，如果越界会抛出IndexOutOfBoundsException异常，根据索引取出对应元素。



### ArrayList 动态扩容的实现

面试官：“那它是怎么实现的呢？”

三歪：“使用ArrayList在每一次`add`的时候，它都会先去计算这个数组够不够空间，如果空间是够的，那直接追加上去就好了。如果不够，那就得扩容”

```java
/**
     * Appends the specified element to the end of this list.
     *
     * @param e element to be appended to this list
     * @return <tt>true</tt> (as specified by {@link Collection#add})
     */
public boolean add(E e) {
        ensureCapacityInternal(size + 1);  // Increments modCount!!
        elementData[size++] = e;
        return true;
    }
private void ensureCapacityInternal(int minCapacity) {
        if (elementData == DEFAULTCAPACITY_EMPTY_ELEMENTDATA) {
            minCapacity = Math.max(DEFAULT_CAPACITY, minCapacity);
        }

        ensureExplicitCapacity(minCapacity);
    }

    private void ensureExplicitCapacity(int minCapacity) {
        modCount++;

        // overflow-conscious code
        if (minCapacity - elementData.length > 0)
            grow(minCapacity);
    }
```

面试官：“那怎么扩容？一次扩多少？”

三歪：“在源码里边，有个`grow`方法，每一次扩原来的`1.5`倍。比如说，初始化的值是10嘛。现在我第11个元素要进来了，发现这个数组的空间不够了，所以会扩到15”

```java
private void grow(int minCapacity) {
        // overflow-conscious code
        int oldCapacity = elementData.length;
        int newCapacity = oldCapacity + (oldCapacity >> 1);
        if (newCapacity - minCapacity < 0)
            newCapacity = minCapacity;
        if (newCapacity - MAX_ARRAY_SIZE > 0)
            newCapacity = hugeCapacity(minCapacity);
        // minCapacity is usually close to size, so this is a win:
        elementData = Arrays.copyOf(elementData, newCapacity);
    }
 private static int hugeCapacity(int minCapacity) {
        if (minCapacity < 0) // overflow
            throw new OutOfMemoryError();
        return (minCapacity > MAX_ARRAY_SIZE) ?
            Integer.MAX_VALUE :
            MAX_ARRAY_SIZE;
    }
```

三歪：“空间扩完容之后，会调用`arraycopy`来对数组进行拷贝”

面试官：“哦，可以的。那为什么你在前面提到，在日常开发中用得最多的是ArrayList呢？”

三歪：“是由底层的数据结构来决定的，在日常开发中，遍历的需求比增删要多，即便是增删也是往往在List的尾部添加就OK了。像在尾部添加元素，ArrayList的时间复杂度也就`O(1)`”

三歪：“另外的是，ArrayList的增删底层调用的`copyOf()`被优化过，现代CPU对内存可以**块操作**，ArrayList的增删一点儿也不会比LinkedList慢”

```

```



### 3 Vector

面试官：“Vector你了解吗？”

三歪：“嗯，Vector是底层结构是数组，一般现在我们已经很少用了。相对于ArrayList，它是线程安全的，在扩容的时候它是直接扩容两倍的，比如现在有10个元素，要扩容的时候，就会将数组的大小增长到20”。

> Vector 类实现了一个动态数组。和 ArrayList 很相似，但是两者是不同的：
>
> - Vector 是同步访问的。
> - Vector 包含了许多传统的方法，这些方法不属于集合框架。
>
> Vector 主要用在事先不知道数组的大小，或者只是需要一个可以改变大小的数组的情况。
>
> ```java
> public class Vector<E>
>     extends AbstractList<E>
>     implements List<E>, RandomAccess, Cloneable, java.io.Serializable
> 
> ```
>
> 

### Vector与ArrayList的比较

https://blog.csdn.net/qq_37113604/article/details/80836025



ArrayList出现于jdk1.2，vector出现于1.0.

相同点

1. 两者底层的数据存储都使用的Object数组实现，因为是数组实现，所以具有查找快（因为数组的每个元素的首地址是可以得到的，数组是0序的，所以： 被访问元素的首地址=首地址+元素类型字节数*下标  ），增删慢（因为往数组中间增删元素时，会导致后面所有元素地址的改变）的特点
2. 继承的类实现的接口都是一样的，都继承了AbstractList类（继承后可以使用迭代器遍历），实现了RandomAccess(标记接口，标明实现该接口的list支持快速随机访问)，cloneable接口（标识接口，合法调用clone方法），serializable（序列化标识接口）
3. 当两者容量不够时，都会进行对Object数组的扩容

不同点

1. ArrayList的默认构造方法，会默认分配长度为10的内存空间，这里的分配不是在创建对象时分配，而是在增加第一条数据的过程中分配，这样防止了内存的浪费)，然后进行Arrays.copyOf 。如果再次扩容的话，扩容到当前容量的1.5倍。arraylist默认增长1.5倍；vector可以自定义若不自定义，则增长2倍，若定义则新长度=之前的长度+增长因子。

2. 线程的安全性不同，vector是线程安全的,在vector的大多数方法都使用synchronized关键字修饰，arrayList是线程不安全的（可以通过Collections.synchronizedList（）实现线程安全）

3. 性能上的差别，由于vector的方法都有同步锁，在方法执行时需要加锁、解锁，所以在执行过程中效率会低于ArrayList，另外，性能上的差别还体现在底层的Object数组上

   vector:![img](https://img-blog.csdn.net/20180808204955346?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM3MTEzNjA0/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)arrayList:![img](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020124020.png)

   可以看出来，arrayList多了一个transient关键字，这个关键字的作用是防止序列化，然后在ArrayList中重写了了readObject和writeObject方法，这样是为了在传输时提高效率，



### 4 CopyOnWriteArrayList

面试官：“嗯，那如果我们不用Vector，线程安全的List还有什么？”

三歪：“首先，我们也可以用Collections来将ArrayList来包装一下，变成线程安全。但这肯定不是你想听的，对吧。在`java.util.concurrent`包下还有一个类，叫做CopyOnWriteArrayList”

面试官：“嗯，你继续说”

三歪：“要讲CopyOnWriteArrayList之前，我还是想说说`copy-on-write`这个意思，下面我会简称为`cow`。比如说在Linux中，我们知道所有的进程都是`init`进程`fork`出来的，除了进程号之外，`fork`出来的进程，默认跟父进程一模一样的。在`fork`之后`exec`之前，两个进程用的是相同的内存空间的，这意味着子进程的代码段、数据段、堆栈都是**指向**父进程的物理空间”

面试官：“嗯”

三歪：“当父子进程中有更改的行为发生时，再为子进程分配相应物理空间。这样做的好处就是，等到真正发生修改的时候，才去分配资源，可以减少分配或者复制大量资源时带来的**瞬间延时**。简单来说，就可以理解为我们的懒加载，或者说单例模式的懒汉式。等真正用到的时候再分配”

面试官：“嗯”

三歪：“在文件系统中，其实也有`cow`的机制。文件系统的`cow`就是在修改数据的时候，不会直接在原来的数据位置上进行操作，而是重新找个位置修改。比如说：要修改数据块A的内容，先把A读出来，写到B块里面去。如果这时候断电了，原来A的内容还在。这样做的好处就是可以保证数据的完整性，瞬间挂掉了容易**恢复**。

三歪：“再回头来看CopyOnWriteArrayList吧，CopyOnWriteArrayList是一个线程安全的List，底层是通过**复制数组**的方式来实现的。

三歪：“我来说说它 的`add()`方法的实现吧”

面试官：“好”

三歪：“在`add()`方法其实他会加`lock`锁，然后会复制出一个新的数组，往新的数组里边`add`真正的元素，最后把array的指向改变为新的数组”

三歪：“其实`get()`方法又或是`size()`方法只是获取array所指向的数组的元素或者大小。读不加锁，写加锁”

三歪：“可以发现的是，CopyOnWriteArrayList跟文件系统的COW机制是很像的”

面试官：“那你能说说CopyOnWriteArrayList有什么缺点吗？”

三歪：“很显然，CopyOnWriteArrayList是很耗费内存的，每次`set()/add()`都会复制一个数组出来，另外就是CopyOnWriteArrayList只能保证数据的**最终一致性**，不能保证数据的实时一致性。假设两个线程，线程A去读取CopyOnWriteArrayList的数据，还没读完，现在线程B把这个List给清空了，线程A此时还是可以把剩余的数据给读出来。”



### 5 LinkedList

Java LinkedList（链表） 类似于 ArrayList，是一种常用的数据容器。

该集合内部维护了一个双向循环链表。与 ArrayList 相比，LinkedList 的增加和删除对操作效率更高，而查找和修改的操作效率较低。

**以下情况使用 ArrayList :**

- 频繁访问列表中的某一个元素。
- 只需要在列表末尾进行添加和删除元素操作。

**以下情况使用 LinkedList :**

- 你需要通过循环迭代来访问列表中的某些元素。
- 需要频繁的在列表开头、中间、末尾等位置进行添加和删除元素操作。


![img](https://www.runoob.com/wp-content/uploads/2020/06/20190328164737.png)

LinkedList 继承了 AbstractSequentialList 类。LinkedList 实现了 Queue 接口，可作为队列使用。

LinkedList 实现了 List 接口，可进行列表的相关操作。LinkedList 实现了 Deque 接口，可作为队列使用。

LinkedList 实现了 Cloneable 接口，可实现克隆。LinkedList 实现了 java.io.Serializable 接口，即可支持序列化，能通过序列化去传输

## Set

与List不同Set接口中的元素无序，并且都会以某种规则保证存入的元素不会重复。

Set接口中主要有两个实现类，分别是HahSet和TreeSet。其中 根据对象的哈希值来确定元素在集合中的存储位置，因此具有良好的存取和查找性能。TreeSet则是以二叉树的实行来存储元素，他可以实现对集合中的元素进行排序。

### HashSet

HashSet 基于 HashMap 来实现的，是一个不允许有重复元素的集合。

HashSet 允许有 null 值。

HashSet 是无序的，即不会记录插入的顺序。

HashSet 不是线程安全的， 如果多个线程尝试同时修改 HashSet，则最终结果是不确定的。 您必须在多线程访问时显式同步对 HashSet 的并发访问。

HashSet 实现了 Set 接口。

### HashSet如何保证不出现重复元素

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020125136.jpg)

```java
**
     * Adds the specified element to this set if it is not already present.
     * More formally, adds the specified element <tt>e</tt> to this set if
     * this set contains no element <tt>e2</tt> such that
     * <tt>(e==null&nbsp;?&nbsp;e2==null&nbsp;:&nbsp;e.equals(e2))</tt>.
     * If this set already contains the element, the call leaves the set
     * unchanged and returns <tt>false</tt>.
     *
     * @param e element to be added to this set
     * @return <tt>true</tt> if this set did not already contain the specified
     * element
     */
    public boolean add(E e) {
        return map.put(e, PRESENT)==null;
    }java
```



### HashSet和HashMap的区别

| *HashMap*                                   | *HashSet*                                                    |
| ------------------------------------------- | ------------------------------------------------------------ |
| HashMap实现了Map接口                        | HashSet实现了Set接口                                         |
| HashMap储存键值对                           | HashSet仅仅存储对象                                          |
| 使用put()方法将元素放入map中                | 使用add()方法将元素放入set中                                 |
| HashMap中使用键对象来计算hashcode值         | HashSet使用成员对象来计算hashcode值，对于两个对象来说hashcode可能相同，所以equals()方法用来判断对象的相等性，如果两个对象不同的话，那么返回false |
| HashMap比较快，因为是使用唯一的键来获取对象 | HashSet较HashMap来说比较慢                                   |

## Map

Map接口是一种双列集合，每个元素都包含一个键对象Key和一个值对象Value,键和值对象之间存在一种对应关系，称为映射。

“Map在Java里边是一个接口，常见的实现类有HashMap、LinkedHashMap、TreeMap和ConcurrentHashMap”

### Map的数据结构

在Java里边，

哈希表的结构是`数组+链表`的方式。

HashMap底层数据机构是`数组+链表/红黑树`、

LinkedHashMap底层数据结构是`数组+链表+双向链表`、

TreeMap底层数据结构是红黑树，

而ConcurrentHashMap底层数据结构也是`数组+链表/红黑树`”

### Map集合常用方法表

| 方法声明                             | 功能描述                                                     |
| ------------------------------------ | ------------------------------------------------------------ |
| boolean containsKey(Object key);     | Returns <tt>true</tt> if this map contains a mapping for the specified  key. |
| boolean containsValue(Object value); | Returns <tt>true</tt> if this map maps one or more keys to the  specified value. |
| V get(Object key);                   | Returns the value to which the specified key is mapped,  or {@code null} if this map contains no mapping for the key. |
| V put(K key, V value);               | Associates the specified value with the specified key in this map  (optional operation).  If the map previously contained a mapping for  the key, the old value is replaced by the specified value. |
| V remove(Object key);                | Removes the mapping for a key from this map if it is present  (optional operation). |
| void clear();                        | Removes all of the mappings from this map (optional operation).  The map will be empty after this call returns. |
| Set<K> keySet();                     | Return a set view of the keys contained in this map          |
| Collection<V> values();              | Return a collection view of the values contained in this map |
| Set<Map.Entry<K, V>> entrySet();     | Return a set view of the mappings contained in this map      |

### HashMap

#### HashMap的实现与存储结构

HashMap 是一个散列表，它存储的内容是键值对(key-value)映射。

HashMap 实现了 Map 接口，根据键的 HashCode 值存储数据，具有很快的访问速度，最多允许一条记录的键为 null，不支持线程同步。

HashMap 是无序的，即不会记录插入的顺序。

HashMap 继承于AbstractMap，实现了 Map、Cloneable、java.io.Serializable 接口。HashMap 实现了 Serializable 接口，因此它支持序列化，实现了 Cloneable 接口，能被克隆。

 HashMap 是非线程安全的，只是用于单线程环境下，多线程环境下可以采用 concurrent 并发包下的 concurrentHashMap

![img](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020132507.png)

HashMap的存储结构



![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201020133738.png)

图中，紫色部分即代表哈希表，也称为哈希数组，数组的每个元素都是一个单链表的头节点，链表是用来解决冲突的，如果不同的 key 映射到了数组的同一位置处，就将其放入单链表中。

   HashMap 内存储数据的 Entry 数组默认是 16，如果没有对 Entry 扩容机制的话，当存储的数据一多，Entry 内部的链表会很长，这就失去了 HashMap 的存储意义了。所以 HasnMap 内部有自己的扩容机制



#### 1 HashMap的创建

面试官：“我们先以HashMap开始吧，你能讲讲当你`new`一个HashMap的时候，会发生什么吗？”

三歪：“HashMap有几个构造方法，但最主要的就是指定初始值大小和负载因子的大小。如果我们不指定，**默认HashMap的大小为`16`，负载因子的大小为`0.75`**”

```java
public HashMap() {
        this.loadFactor = DEFAULT_LOAD_FACTOR; // all other fields defaulted
    }
```

三歪：“HashMap的大小只能是**2次幂**的，假设你传一个10进去，实际上最终HashMap的大小是16，你传一个7进去，HashMap最终的大小是8，具体的实现在`tableSizeFor`可以看到。我们把元素放进HashMap的时候，需要算出这个元素所在的位置（hash）。在HashMap里用的是**位运算**来代替取模，能够更加**高效**地算出该元素所在的位置。为什么HashMap的大小只能是2次幂，因为只有大小为2次幂时，**才能合理用位运算替代取模**。”

```java
static final int tableSizeFor(int cap) {
        int n = cap - 1;
        n |= n >>> 1;
        n |= n >>> 2;
        n |= n >>> 4;
        n |= n >>> 8;
        n |= n >>> 16;
        return (n < 0) ? 1 : (n >= MAXIMUM_CAPACITY) ? MAXIMUM_CAPACITY : n + 1;
    }
```

三歪：“而负载因子的大小决定着哈希表的**扩容**和**哈希冲突**。比如现在我默认的HashMap大小为16，负载因子为0.75，这意味着数组最多只能放12个元素，一旦超过12个元素，则哈希表需要扩容。怎么算出是12呢？很简单，就是`16*0.75`。每次`put`元素进去的时候，都会检查HashMap的大小有没有超过这个阈值，如果有，则需要扩容。”

三歪：“鉴于上面的说法（HashMap的大小只能是2次幂），所以扩容的时候时候默认是扩原来的2倍”

三歪：“显然扩容这个操作肯定是耗时的，那我能不能把**负载因子调高**一点，比如我要调至为1，那我的HashMap就等到16个元素的时候才扩容呢。显然是可以的，但是不推荐。负载因子调高了，这意味着**哈希冲突的概率**会增高，哈希冲突概率增高，同样会耗时（因为查找的速度变慢了）”

#### 3 哈希值的计算

```java
 static final int hash(Object key) {
        int h;
        return (key == null) ? 0 : (h = key.hashCode()) ^ (h >>> 16);
    }
```

三歪：“实现就在`hash`方法上，可以发现的是，它是先算出正常的哈希值，然后与**高16位**做异或运算，产生最终的哈希值。这样做的好处可以**增加了随机性**，减少了碰撞冲突的可能性。”

#### 4 hashMap的 put/get 的方法实现

```java
public V get(Object key) {
        Node<K,V> e;
        return (e = getNode(hash(key), key)) == null ? null : e.value;
    }
    
 public V put(K key, V value) {
        return putVal(hash(key), key, value, false, true);
    }   
```

三歪：”在`put`的时候，首先对key做hash运算，计算出该key所在的index。如果没碰撞，直接放到数组中，如果碰撞了，需要判断目前数据结构是链表还是红黑树，根据不同的情况来进行插入。假设key是相同的，则替换到原来的值。最后判断哈希表是否满了(当前哈希表大小`*`负载因子），如果满了，则扩容“

三歪：”在`get`的时候，还是对key做hash运算，计算出该key所在的index，然后判断是否有hash冲突，假设没有直接返回，假设有则判断当前数据结构是链表还是红黑树，分别从不同的数据结构中取出。“

#### 5 在HashMap中，怎么判断一个元素是否相同

```java
ublic final boolean equals(Object o) {
            if (o == this)
                return true;
            if (o instanceof Map.Entry) {
                Map.Entry<?,?> e = (Map.Entry<?,?>)o;
                if (Objects.equals(key, e.getKey()) &&
                    Objects.equals(value, e.getValue()))
                    return true;
            }
            return false;
        }
```

三歪：”首先会比较hash值，随后会用`==`运算符和`equals()`来判断该元素是否相同。说白了就是：如果只有hash值相同，那说明该元素哈希冲突了，如果hash值和`equals() || ==` 都相同，那说明该元素是同一个。“

#### 6 HashMap 使用红黑树的情况

三歪：”当数组的大小大于**64**且链表的大小大于**8**的时候才会将链表改为红黑树，当红黑树大小为**6**时，会退化为链表。这里转红黑树退化为链表的操作主要出于**查询和插入时对性能的考量**。链表查询时间复杂度O(N)，插入时间复杂度O(1)，红黑树查询和插入时间复杂度O(logN)“

#### 7 HashMap为什么是线程不安全

HashMap 底层是一个 Entry 数组，当发生 hash 冲突的时候，hashmap 是采用链表的方式来解决的，在对应的数组位置存放链表的头结点。对链表而言，新加入的节点会从头结点加入。

我们来分析一下多线程访问：

 

   （1）在hashmap做put操作的时候会调用下面方法：

```java
// 新增Entry。将“key-value”插入指定位置，bucketIndex是位置索引。      
    void addEntry(int hash, K key, V value, int bucketIndex) {      
        // 保存“bucketIndex”位置的值到“e”中      
        Entry<K,V> e = table[bucketIndex];      
        // 设置“bucketIndex”位置的元素为“新Entry”，      
        // 设置“e”为“新Entry的下一个节点”      
        table[bucketIndex] = new Entry<K,V>(hash, key, value, e);      
        // 若HashMap的实际大小 不小于 “阈值”，则调整HashMap的大小      
        if (size++ >= threshold)      
            resize(2 * table.length);      
    }  
```

   在hashmap做put操作的时候会调用到以上的方法。现在假如A线程和B线程同时对同一个数组位置调用addEntry，两个线程会同时得到现在的头结点，然后A写入新的头结点之后，B也写入新的头结点，那B的写入操作就会覆盖A的写入操作造成A的写入操作丢失

（   2）删除键值对的代码

```java
final Entry<K,V> removeEntryForKey(Object key) {      
        // 获取哈希值。若key为null，则哈希值为0；否则调用hash()进行计算      
        int hash = (key == null) ? 0 : hash(key.hashCode());      
        int i = indexFor(hash, table.length);      
        Entry<K,V> prev = table[i];      
        Entry<K,V> e = prev;      
     
        // 删除链表中“键为key”的元素      
        // 本质是“删除单向链表中的节点”      
        while (e != null) {      
            Entry<K,V> next = e.next;      
            Object k;      
            if (e.hash == hash &&      
                ((k = e.key) == key || (key != null && key.equals(k)))) {      
                modCount++;      
                size--;      
                if (prev == e)      
                    table[i] = next;      
                else     
                    prev.next = next;      
                e.recordRemoval(this);      
                return e;      
            }      
            prev = e;      
            e = next;      
        }      
     
        return e;      
    }  
```

   当多个线程同时操作同一个数组位置的时候，也都会先取得现在状态下该位置存储的头结点，然后各自去进行计算操作，之后再把结果写会到该数组位置去，其实写回的时候可能其他的线程已经就把这个位置给修改过了，就会覆盖其他线程的修改

   （3）addEntry中当加入新的键值对后键值对总数量超过门限值的时候会调用一个resize操作，代码如下：

```java
// 重新调整HashMap的大小，newCapacity是调整后的容量      
    void resize(int newCapacity) {      
        Entry[] oldTable = table;      
        int oldCapacity = oldTable.length;     
        //如果就容量已经达到了最大值，则不能再扩容，直接返回    
        if (oldCapacity == MAXIMUM_CAPACITY) {      
            threshold = Integer.MAX_VALUE;      
            return;      
        }      
     
        // 新建一个HashMap，将“旧HashMap”的全部元素添加到“新HashMap”中，      
        // 然后，将“新HashMap”赋值给“旧HashMap”。      
        Entry[] newTable = new Entry[newCapacity];      
        transfer(newTable);      
        table = newTable;      
        threshold = (int)(newCapacity * loadFactor);      
    }  
```

   这个操作会新生成一个新的容量的数组，然后对原数组的所有键值对重新进行计算和写入新的数组，之后指向新生成的数组。

   当多个线程同时检测到总数量超过门限值的时候就会同时调用resize操作，各自生成新的数组并rehash后赋给该map底层的数组table，结果最终只有最后一个线程生成的新数组被赋给table变量，其他线程的均会丢失。而且当某些线程已经完成赋值而其他线程刚开始的时候，就会用已经被赋值的table作为原始数组，这样也会有问题。

## 三  LinkedMap

三歪：“其实在日常开发中LinkedHashMap用得不多。在前面也提到了，LinkedHashMap底层结构是`数组+链表+双向链表`”，实际上它**继承**了HashMap，在HashMap的基础上维护了一个**双向链表**。有了这个双向链表，我们的插入可以是“有序”的，这里的有序不是指大小有序，而是**插入有序**。

三歪：“LinkedHashMap在遍历的时候实际用的是双向链表来遍历的，所以LinkedHashMap的大小不会影响到遍历的性能”

## 四 TreeMap

三歪：“TreeMap在现实开发中用得也不多，TreeMap的底层数据结构是红黑树，TreeMap的key不能为null（如果为null，那还怎么排序呢），TreeMap有序是通过Comparator来进行比较的，**如果comparator为null，那么就使用自然顺序**”

## 五 进程安全的Map

三歪：“HashMap不是线程安全的，在多线程环境下，HashMap有可能会有数据丢失和获取不了最新数据的问题，比如说：线程A`put`进去了，线程B`get`不出来。我们想要线程安全，可以使用ConcurrentHashMap”

## 六 ConcurrentHashMap

三歪：“ConcurrentHashMap是线程安全的Map实现类，它在`juc`包下的。线程安全的Map实现类除了ConcurrentHashMap还有一个叫做Hashtable。当然了，也可以使用Collections来包装出一个线程安全的Map。但无论是Hashtable还是Collections包装出来的都比较低效（因为是直接在外层套synchronize），所以我们一般有线程安全问题考量的，都使用ConcurrentHashMap”

三歪：“ConcurrentHashMap的底层数据结构是`数组+链表/红黑树`，它能支持高并发的访问和更新，是线程安全的。ConcurrentHashMap通过在**部分加锁**和**利用CAS算法**来实现同步，在`get`的时候没有加锁，Node都用了`volatile`给修饰。在扩容时，会给每个线程分配对应的**区间**，并且为了防止`putVal`导致数据不一致，会给线程的所负责的区间加锁”



## HashTable

### HashTable与HashMap的区别

1. 继承的父类不同

      Hashtable继承自Dictionary类，而HashMap继承自AbstractMap类。但二者都实现了Map接口。

2. 线程安全性不同

    Hashtable 中的方法是Synchronize的，而HashMap中的方法在缺省情况下是非Synchronize的。在多线程并发的环境下，可以直接使用Hashtable，不需要自己为它的方法实现同步，但使用HashMap时就必须要自己增加同步处理。（结构上的修改是指添加或删除一个或多个映射关系的任何操作；仅改变与实例已经包含的键关联的值不是结构上的修改。）这一般通过对自然封装该映射的对象进行同步操作来完成。如果不存在这样的对象，则应该使用 [Collections.synchronizedMap](http://write.blog.csdn.net/postedit/51556314#synchronizedMap(java.util.Map)) 方法来“包装”该映射

3. 







# 五 字符串

## String

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201021063755.png)



## StringBuffer

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201021063834.png)S







# 六 其他API



# 七 JDBC



# 八 IO 输入输出



# 九 多线程


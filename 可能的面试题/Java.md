静态方法：可以通过类名直接调用/也可以通过实例调用，在不创建对象的时候就可以使用

重载和重写

重载：类中同名方法参数不同

重写：子类重写超类的方法，改写超类的方法

抽象，封装，继承，多态

多态：一个超类的对象可以使用超类和其子类的任意一个方法，超类和子类可以响应相同的参数，与内部方法有关

public：都可以调用

protected：子类可以调用

private：只有类内部调用

Java的数据结构

Collection

List

- LinkedList：双向链表，只能顺序访问，插入删除方便
- ArrayList：动态数组，随机访问

Set

- TreeSet：红黑树实现，支持有序查找，复杂度logn
- HashSet：基于哈希表实现，插入无序，快速查找，复杂度1
- LinkedHasSet：HashSet的查找效率，双向链表维护顺序

Queue

- LinkedList：双向队列
- PriorityQueue：堆实现

Map

- TreeMap：红黑树
- HashMap：哈希表
- HashTable：线程安全，用ConcurrentHashMap代替
- LinkedHashMap：使用双向链表来维护顺序，插入顺序或LRU

多线程

JVM

Spring
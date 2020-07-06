# Chapter 1

### 1. 面向对象语言的基本特征

- 抽象和封装
  - 共同行为抽象成class，通过类来封装这些行为
- 继承
- 多态

### 2. Java的通用性

通过编译成`.class`文件（称为**字节码**），不同机器均可以识别。

### 3. 基本数据类与表达式

- 文字（常）量：直接出现在程序中并被编译器直接使用
- 标识符：开头只可以是大小写字母，_，$
- 变量：关联到存储位置
- 基本数据类型
  - byte：8位
  - short：16位
  - int：32位
  - long：64位
  - float：32位
  - double：64位
  - boolean：true/false
- 字符串：String
- 条件运算符（表达式1？表达式2；表达式3）
  - 先计算表达式1，true则运行表达式2，false则运行表达式3
- ==字符串转换==：+可以将字符串和任意类型进行组合成新的字符串

### 4. 数组

- 数组是**对象**
  - 动态初始化过程
  - 可以赋值给`Object`类
  - 可以调用`Object`类中所有方法
- 构建数组
  - 数组引用：`Type[] arrayName;`
  - 动态创建：适用`new arryName = new Type[componets number];`
  - 初始化：默认为`0/null/false`
  - 数组使用：`arrayName[index]`
  - 数组长度：`arrayName.length`
- 数组名是一个**引用**：`a2=a1`只是让`a2`指向`a1`所指向的数组，并不会创建出来新的数组。
- **貌似**`class`名用大写字母开头，变量名用小写字母
- 复制数组使用`arraycopy`的方法：

```java
public static void arraycopy(Object source, int srcindex, Object dest, int destindex, int length)
```

- 多维数组
  - 声明和构造：`int[][] myArray;`
  - 二维数组的长度：每一行长度可以不一样，相当于一位数组构成的数组

### 5. 算法流程控制

- if-else
- switch break
- for
- do-while
- while


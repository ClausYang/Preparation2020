# Chapter 1

## 1. 什么是数据结构

- 写程序计算给定多项式在给定点x处的值

从内向外运算效率更高

```c
double f(int n, double a[], double x){
	int i;
	double p = a[n];
	for(i=n;i>0;i--){
		p = a[i-1] + x*p;
	}
	return p;
}
```

- 抽象数据类型的定义

## 2. 什么是算法

- 有限指令集
- 空间复杂度![formula](https://render.githubusercontent.com/render/math?math=S(n))
- 时间复杂度![formula](https://render.githubusercontent.com/render/math?math=T(n))
- 分析一般算法需要注意的两种复杂度
  - **最坏情况复杂度![formula](https://render.githubusercontent.com/render/math?math=T_{worst}(n))
  - 平均复杂度![formula](https://render.githubusercontent.com/render/math?math=T_{avg}(n))
- 复杂度的渐进表示法：![formula](https://render.githubusercontent.com/render/math?math=O(f(n)))
  - ![formula](https://render.githubusercontent.com/render/math?math=T_1(n)=O(f_1(n)), ![](http://latex.codecogs.com/svg.latex?\\T_2(n)=O(f_2(n))
    - ![formula](https://render.githubusercontent.com/render/math?math=T_1(n)+T_2(n)=max(O(f_1(n),O(f_2(n))))
    - ![formula](https://render.githubusercontent.com/render/math?math=T_1(n)\times T_2(n)=O(f_1(n)\times f_2(n)))
  - 一个`for`循环的时间复杂度等于循环次数乘以循环体代码的复杂度
  - `if-else`复杂度取决于if的条件判断复杂度和连个分支部分的复杂度，复杂度取最大。

## 3. 最大子序列和

分而治之：![formula](https://render.githubusercontent.com/render/math?math=nlogn)

<img src="Chapter 1.assets/截屏2020-07-07 下午11.03.24.png" alt="截屏2020-07-07 下午11.03.24" style="zoom:50%;" />

- **在线处理算法**：抛弃负的子列和
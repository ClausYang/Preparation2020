# Union-Find

## 1. Dynamic Connectivity

### 1.1 Steps to developing a usable algorithm.

- Model the problem.
- Find an algorithm to solve it.
- Fast enough? Fits in memory?
- If not, figure out why.
- Find a way to address the problem. 
- Iterate until satisfied.

### 1.2 Dynamic Connectivity

![截屏2020-07-16 下午11.05.04](/Users/yangchenghao/Library/Application Support/typora-user-images/截屏2020-07-16 下午11.05.04.png)

#### 1.2.1 Modeling the connections

We assume **"is connected to"** is an equivalence relation:

- **Reflexive:** *p* is connected to *p*.
- **Symmetric:** if *p* is connected to *q*, then *q* is connected to *p*. 
- **Transitive:** if *p* is connected to *q* and *q* is connected to *r*, then *p* is connected to *r*.

**Connected components.** Maximal set of objects that are mutually connected.

<img src="/Users/yangchenghao/Library/Application Support/typora-user-images/截屏2020-07-16 下午11.10.03.png" alt="截屏2020-07-16 下午11.10.03" style="zoom:50%;" />

#### 1.2.2 Implementing the operations

**Find query.** Check if two objects are in the same component.

**Union command.** Replace components containing two objects

with their union.

![截屏2020-07-16 下午11.15.51](/Users/yangchenghao/Library/Application Support/typora-user-images/截屏2020-07-16 下午11.15.51.png)

#### 1.2.3 Union-find data type (API)

![截屏2020-07-16 下午11.16.45](/Users/yangchenghao/Library/Application Support/typora-user-images/截屏2020-07-16 下午11.16.45.png)

#### 1.2.4 Dynamic-connectivity client

- Read in number of objects *N* from standard input. 

- Repeat:
  - –  read in pair of integers from standard input
  - –  if they are not yet connected, connect them and print out pair

<img src="/Users/yangchenghao/Library/Application Support/typora-user-images/截屏2020-07-16 下午11.20.28.png" alt="截屏2020-07-16 下午11.20.28" style="zoom:80%;" />

### 1.3 Quick Find

**Data Structure**.

- Integer array `id[]` of length N.

- Interpretation: `p` and `q` are connected iff they have the same id.

If the two numbers are connected, put the same index to their id, like the picture, 0,5,6 have the same index of 0 because the are connected.

![截屏2020-07-16 下午11.28.00](/Users/yangchenghao/Library/Application Support/typora-user-images/截屏2020-07-16 下午11.28.00.png)

**Find.** 

Check if `p` and `q` have the same id.

**Union. **

To merge components containing `p` and `q`, change all entries whose id equals `id[p]` to `id[q]`.

<img src="/Users/yangchenghao/Library/Application Support/typora-user-images/截屏2020-07-16 下午11.32.58.png" alt="截屏2020-07-16 下午11.32.58" style="zoom:50%;" />

**Java Implementation**

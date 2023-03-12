# COMP26120 Algorithm and DataStructure 

# 1.Introduction to Algorithms

## 1.1 computational problem VS algorithm

### computational problem

computational Problem: **A desired relationship between inputs and outputs** 

 Example: The sorting problem   

​                    Input. A list L of numbers 

​                    Output. A permutation of L that is in order

### Algorithm

A well-defined set of steps transforming input into output solving computational problem

Example: Insertion Sort, Bubble Sort etc.,

## 1.2 What is a Data Structure?

### Abstract Data Type and Data Structure

#### Abstract Datatype  抽象数据类型

*Defines the **behaviour** of a set of possilble operations on data of certain type* 

Example: A list may have the opearations     

​                  add.Adds and element to the end of the list 

​                  head.Returns the first element of the list 

​      			tail.Return the sublist after the head 

​                   堆栈就是一种典型的ADT  又三个操作定义 （ push，peek， pop） 

#### 1.3 Datastructure

​	*A way to **store** and **organize** data in order facilitate access and modifications* 

   Example: Linked List, Binary Tree, Hash Table 

### 1.4 Describing Algorithm(And Data Structure)

**Pseudocode**

Careful English 

Abstract 

No syntax error 

**Abstract Machine** 

sequential execution 

constant operations 

infinite memory 

## Example question 

You work for an advertising company selling banners. Banners require a frame with four side panels, which come in pairs of the same length. Your supplier has provided a list of the lengths of side panels it provides. When a client requests a banner of a particular area you must check whether you can make a banner of that area. Your job is to write an algorithm for this task. You can assume that any dimension of banner is suitable as long as it is the correct area.

#### Algorithm 1:  Brute Force Solution 

```pesudocode
search( int[] a , int k)
bool Found = false 
for i=1 to i=length(a)
	for j=i to length(a)
		if a[i]*a[j] = k 
		return Found = true 

```

​    这里外层遍历了 n 次 内层 每次都遍历 n-i+1 次 ，

​    所以复杂度为   
$$
\sum_{n=1}^{n}{n-i-1}
$$
​       
$$
n+\frac{n(n+1)}{2}
$$
​                                            

很显然 复杂度还是
$$
O(n^2)
$$

#### Algorithm 2: A Sorting Solution 

```
search(int[] a , int k) 
	sort(a)
	int i = 0
	int j = length(a)
while(i<=j)
	if(i*j==k)
		return true 
else if (i*j<k)
		i++
		else 
		i--
return false 
```

complexity : *O(n)*

#### Algorithm 3: Remebering Solution

```
search(int[] a , int k)
    set s = empty
    for i=1 to length(a)
    if  a[i] divide k 
     add a[i] to s 
     	let b = k/a[i]
     	if b is in s
     	return true 
     	else 
     	return false 
   return false   	
```

complexity:
$$
O(n^2)
$$
if use hashset then *O(n)*



# 2.Introducing Algorithm Complexity

## 2.1 Search Problem 

```
j=1
while j<=length(A) and A[j]！= q
	do j++
if j<= length(A) then return j
else return NIL
```

## 2.2 Binary Search 

​      Assume the array is sorted

```
left=1 
right=length(A)
do 
   j = (right+left)/2
   if A[j]==q then return j
   else if A[j]>q then right = j-1
   else left=j+1
while left <= right 
return NIL
```

 How many times is the loop executed ? 

- ​	At each interaction, the number of position n is cut in half
- ​    How  many times do we cut in half n to reach 1? 

​                             ![image-20230123113708205](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123113708205.png)

​                       
$$
log_2n
$$

## 2.3 Input Size 

- *Time and space complexity*
- This is generally a function of the input size
- How we characterize input size depends: 
  - sorting: number of input items   数量
  - Multiplication:total number of bits   总共bits数
  - Graph algorithms: number of nodes and edges  节点个数

## 2.4 Running time 

- Number of **primitive steps** that are executed   执行的多少步

  

## 2.5 Analysis 

- Worst case 
  - Provide an upper bound on running time 
  - An guarantee

-  Average case 
  -  Provide the expected running time 
  - Very useful , but treat with care: what is "average "
    - Random input

## 2.6 Insertion Sort 插入排序 

```python
InsertionSort(A,n){
 for i=2 to n{
   key = A[i]
   j=i-1 
   while(j>0)and(A[j]>key){
   A[j+1]=A[j]
   j=j-1
   }
   A[j+1]=key
   }
   }
```

1. 取第一个数字
2. 取第二个数字，记当前值为key
3. 如果二处值大于一处值，则把指针2处的值变成1的值，指针一变成key 
4. 循环直到遍历完整个array

![image-20230123124108149](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123124108149.png)

while 这里不确定会花费多少时间  有可能是average case 也有可能是 bast case 所以设定这里的effort 为 T , 

所以总共的时间复杂度为 
$$
T(n)=c_1n + c_2(n-1)+ c_3(n-1)+c_4T+c_5(T-(n-1))+c_6(T-(n-1))+c_7(n-1)
$$
Best Case :    while 内部循环不执行                    
$$
T=t_2+t_3+...+t_n=n-1 
$$
while 这里的 condition check 会check n-1 次 所以是 n -1 

因此 Best case 的时间复杂度为 
$$
T(n) = c_1n + c_2(n-1)+ c_3(n-1)+c_4(n-1)+c_7(n-1)
$$

$$
T(n) = (c_1+c_2+c_3+c_4+c_7)\cdot n - (c_2+c_3+c_4+c_7)
$$

   很显然复杂度是
$$
O(n)=an+b
$$
Worst Case : while 内部被全部执行  

外部一次循环，while 内部被执行 n次 所以总共 
$$
\sum_{j=2}^{n}{j}=\frac{(1+n)\cdot n}{2}-1
$$
​                                                  

j+1执行了
$$
\sum_{j=2}^{n}{j-1}=\frac{(1-n)\cdot n}{2}
$$
所以可以计算出总的 时间复杂度 
$$
T(n)=(\frac{c_4}{2}+\frac{c_5}{2}+\frac{c_6}{2})n^2 + (c_1+c_2+c_3+\frac{c_4}{2}-\frac{c_5}{2}-\frac{c_6}{2})n-(c_2+c_3+c_4+c_7)
$$
复杂度为
$$
O(n)=an^2+bn+c
$$




## 2.7 Uper Bound Notation 上界限符号

- InsertionSort's runtime is *O(n)*

  - runtime is in O(n^2)
  - Read O as "big O"

  

- ![image-20230123141755794](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123141755794.png)

![image-20230123141831471](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123141831471.png)

## 2.8 Insertion Sort is O(n^2)

证明插入排序的时间复杂度为*O(n^2)*

![image-20230123142200625](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123142200625.png)

很显然 在三种 case 下 前两种case 是满足条件的但是第三种不满足 所以插入排序的时间复杂度不是*O(n^2)*

## 2.9 Lower Bound Notation 下界限符号

![image-20230123142659040](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123142659040.png)

![image-20230123142801664](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123142801664.png)

很显然插入排序的复杂度满足  


$$
\Omega(n)
$$


## 2.9.1 Asymptotic Tight Notation 

![image-20230123143236514](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123143236514.png)

例题1：证明 
$$
\frac{1}{2}n^2-3n=\Theta(n^2)
$$
根据定义有
$$
c_1 n^2\le \frac{1}{2}n^2-3n\le c_2n^2
$$
化简得
$$
c_2\ge \frac{1}{2}
$$

$$
c1\ge \frac{1}{14}
$$



​                                                                                                      当n＞7时c1 满足条件

例题2 ：

![image-20230123144825726](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123144825726.png)

很显然 当 n 很大的时候这个就不成立了

## 2.9.2 Other Asymptotic Notation 

![image-20230123145114088](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123145114088.png)

## 2.9.3 Asymptotic Comparisons 

![image-20230123145256797](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230123145256797.png)

## 2.9.4 Space Complexity 

​       既然时间复杂度不是用来计算程序具体耗时的，那么我也应该明白，空间复杂度也不是用来计算程序实际占用的空间的。

空间复杂度是对一个算法在运行过程中临时占用存储空间大小的一个量度，同样反映的是一个趋势，我们用 S(n) 来定义。

空间复杂度比较常用的有：O(1)、O(n)、O(n²)，我们下面来看看：

如果算法执行所需要的临时空间不随着某个变量n的大小而变化，即此算法空间复杂度为一个常量，可表示为 O(1)

```java
int i = 1;
int j = 2;
++i;
j++;
int m = i + j;
```

代码中的 i、j、m 所分配的空间都不随着处理数据量变化，因此它的空间复杂度 S(n) = O(1)



## SEMESTER 2 

### 1.Introduction to Graphs 

#### 1.2 Directed Graphs    

​     A **directed graph** is a set of **nodes V** and **edges E**, where 	𝐸 ⊆ 𝑉 × 𝑉 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230130180411208.png" alt="image-20230130180411208" style="zoom:67%;" />

​        **path**: sequence of nodes  

​        path are **cycle-free** no **repeated nodes** 

​          <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230130203118343.png" alt="image-20230130203118343" style="zoom: 67%;" />

​         **cycle**: **Path** has **same start and end node** 

​       **Simple Graph:** 

- No parrallel edges (two edges with the same orgin and destination)
- No self-loops(origin same as destination)

​       **Spanning subgraph** : A subgraph that contaions all nodes  

​        如果 node 都连起来了 那么叫做 edge ，而 spanning subgraph 的 

​        node 可以不连起来 

​       **Operations :** 

​       <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230130204529109.png" alt="image-20230130204529109" style="zoom:67%;" />

​        **Adjacency Lists** :

​         Store list/set of successors for each node

​         ![image-20230130204811333](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230130204811333.png)

![image-20230130205033658](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230130205033658.png)

![image-20230130205117692](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230130205117692.png)

![image-20230130205357393](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230130205357393.png)

#### 1.3 Generic	Graph	Traversal	Algorithm

• Explore edges to new nodes, until all nodes discovered	

 • Create sets as we go: 

-  D:	discovered,	but	outgoing	edges	yet	to	be	explored	 

-  F:	finished,	outgoing	edges	have	been	explored

  

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230206102944383.png" alt="image-20230206102944383" style="zoom:67%;" />

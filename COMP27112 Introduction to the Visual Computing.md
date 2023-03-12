# COMP27112 Introduction to Visual Computing

## Week 1 

### 1.OpenGL

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205215932775.png" alt="image-20230205215932775" style="zoom:67%;" />

​                       <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205220017204.png" alt="image-20230205220017204" style="zoom:67%;" />

### 2.Where OpenGL fits in

![image-20230205221708009](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205221708009.png)

### 3.The OpenGL API

-  OpenGL is a specification of an Application Programmer’s Interface (API), so language in 

  

-  A set of functions for doing 3D computer graphics

  

- used in mobile devices, industry, engineering, CAD, CGI, FX, research, games, education – everywhere

### 4.Portability

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205230331575.png" alt="image-20230205230331575" style="zoom:67%;" />

### 5.OpenGL evolution

▪ OpenGL functionality has evolved over time: 

▪ OpenGL v1, v2: fixed pipeline – fixed functionality 

▪ OpenGL v3+: programmable pipeline – extensible functionality: programmers write micro-programs called **shaders** 

▪ OpenGL 4.6 (2019)

### 6.Basic graphics system architecture

![image-20230205230456996](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205230456996.png)

### 7.The graphics pipeline

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205230529819.png" alt="image-20230205230529819" style="zoom:67%;" />

 Graphics pipeline – fixed functionality

![image-20230205230628551](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205230628551.png)

Graphics pipeline – programmable functionality

![image-20230205230714371](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205230714371.png)

### 8.Fixed versus programmable

![image-20230205231003298](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231003298.png)

### 9.OpenGL and interaction

![image-20230205231049814](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231049814.png)

Points 

![image-20230205231201107](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231201107.png)

Lines

![image-20230205231218080](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231218080.png)

Polygons

![image-20230205231237564](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231237564.png)

Transformations

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231305247.png" alt="image-20230205231305247" style="zoom:67%;" />

​                         <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231330614.png" alt="image-20230205231330614" style="zoom:67%;" />

The camera model

![image-20230205231401085](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231401085.png)

Hidden-surface removal

![image-20230205231420012](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231420012.png)

![image-20230205231435537](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231435537.png)

Lighting and shading

![image-20230205231454895](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231454895.png)

![image-20230205231516427](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231516427.png)

![image-20230205231528338](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231528338.png)

Textures

![image-20230205231559905](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231559905.png)

Modelling and rendering

![image-20230205231617846](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231617846.png)

Blending/transparency

![image-20230205231646941](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231646941.png)

### 10.GLU

![image-20230205231720122](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231720122.png)

GLUT

![image-20230205231750996](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231750996.png)

OpenGL on Linux

![image-20230205231844822](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230205231844822.png)

## Week 2 : Matrices and Vectors, and Shaders 

### 1. Coordinates and Vectors  向量和坐标

   visual computing 中的 pixel（像素点） 以笛卡尔空间坐标系中的坐标 （x,y,z）的形式表示 

因此，我们也可以把他们看作 是Vector（x，y,z） 



### 2.Geometric Transformation 几何变换

#### 1.Translate Object  平移

Applies a **3D** **shift (tx, ty, tz)** to all coordinates

​      
$$
x' = x +tx \\

       y' =  y +ty \\

       z' = z + tz
$$
  <img src="https://s2.loli.net/2023/02/13/RcDJGVthK1NuO6x.png" alt="1676219281156" style="zoom:67%;" />

#### 2. Scaling Object 尺度

​       Applies a **3D scale** (sx, sy, sz) to all **coordinates**  (with respect to the origin)

​       


$$
x' = x \cdot sx\\
y' = y \cdot sy\\
z' = z \cdot sz
$$


####     3.Rotation 旋转

##### 3.1 Rotation(2D)  

​      我们来看图形在2D坐标系中 关于原点O 的旋转

 <img src="https://s2.loli.net/2023/02/13/92x6YNafXrCcPZg.png" alt="1676221088152" style="zoom:67%;" />

  Rotation about a point  关于一个点的旋转

<img src="https://s2.loli.net/2023/02/13/CyD67FZmSehUqXL.png" alt="1676221796622" style="zoom:67%;" />

通过一些简单的的数学公式我们可以有：
$$
x= RcosΦ\\
y= RsinΦ\\
x’= Rcos(θ+Φ)\\
x’= RcosΦcosθ - RsinΦsinθ\\
y’= Rsin(θ+Φ)\\
y’= RcosΦsinθ + RsinΦcosθ\\
$$
   替换掉  **RcosΦ** 和 **RsinΦ** 得到:
$$
x’= xcosθ  –  ysinθ\\
y’= xsinθ + ycosθ
$$


   这样我们就可以通过关于原点的**旋转角度 θ** 和 **当前坐标**  (x,y)  得到**目标坐标**（x‘，y'）





​    那么，如果这个**原点不在 O** 呢？

​    <img src="https://s2.loli.net/2023/02/13/dCj8iyzELsODTR3.png" alt="1676222155887" style="zoom:67%;" />



如图， 我们关于 Q(qx，qy)进行2D旋转 ，我们可以直接先假设 ( x , y ) 关于原点 O（0，0）旋转， 

因此当前的  的p坐标就为 （x-qx，y-qx） 然后再进行上述的旋转操作
$$
x’= (x-qx)cosθ – (y-qx)sinθ\\
 y’= (x-qx)sinθ + (y-qx)cosθ
$$


​        

##### 3.2 Rotation (3D) 

我们把上面 2D 的点放到 3D 坐标系里 ，



3D中点的旋转会 遇到轴的问题 ， 比如说我们按照之前的旋转方式， 只在 x,y 轴这个平面上旋转，也就是围绕Z轴的旋转

![1676229771945](https://s2.loli.net/2023/02/13/7OhPMHE3F8u6dSk.png)



那么坐标（x,y,z） 围绕 z 轴旋转角度 θ之后的 坐标为 
$$
x’= xcosθ  –  ysinθ\\
y’= xsinθ + ycosθ\\
z'=z
$$
如果我们将围绕的这个轴扩展到**任意一个轴**，那么就能够得到**任意空间坐标系里的旋转坐标**

这个轴也就是我们所说的**向量（vectors）**



**向量（vectors）**在数学中有两种表示方式 

- **矩阵（matrices）**

  <img src="https://s2.loli.net/2023/02/13/MgWritd3TfZ6Imc.png" alt="1676232811867" style="zoom:50%;" />

- **向量**
  $$
  \overrightarrow{x,y,z}
  $$

​		

所以，**二维空间**的三种**基本变换（transforamtions）**在 **三维坐标系**中同样适用

**尺度变化（scaling）**
$$
x' = x + tx\\
y' = y + ty \\
z' = z + tz\\
$$
**旋转（rotation）**
$$
x' = x . cosθ – y . sinθ\\
y' = x . sinθ + y . cosθ\\
z' = z\\
$$
**平移（translation）**
$$
x' = x . sx \\
y' = y . sy \\
z' = z . sz\\
$$


### 3.Using matrices 使用矩阵

#### 3.1 Scaling 



**矩阵**是一个很好的工具来计算计算机视觉中的**像素点变换**

例如，我们可以用矩阵来计算一个**像素点的缩放**：

 scale (x,y,z) by (2,3,5)：

<img src="https://s2.loli.net/2023/02/13/9GJrnbmTxY78Mjz.png" alt="1676242150891" style="zoom:67%;" />
$$
x’ = 2*x + 0*y + 0*z = 2x\\
y’ = 0*x + 3*y + 0*z = 3y\\
z’ = 0*x + 0*y + 5*z = 5\\
$$
**运算方式**则是简单的矩阵乘法:**行乘列**



#### 3.2 Rotation

用这种方式，我们可以得到**三维空间**中的**矩阵旋转(Rotation)**

例如：

rotate (x,y,z) about Z axis by θ：

<img src="https://s2.loli.net/2023/02/13/sITFS1RWunpt3Ed.png" alt="1676242425619" style="zoom:67%;" />


$$
x’ = cosθ*x - sinθ*y + 0*z = xcosθ - ysinθ\\
y’ = sinθ*x + cosθ*y + 0*z = xsinθ + ycosθ\\
z’ = 0*x + 0*y + 1*z = z\\
$$


#### 3.3 Translation

同样可以用在 **平移（translation）**上

例如 ：

translate (x,y,z) by (tx,ty,tz) : 

<img src="https://s2.loli.net/2023/02/13/QnM3UAVRbN6lz4K.png" alt="1676242729901" style="zoom:67%;" />
$$
x’ = 1*x + 0*y + 0*z + tx*1= x + tx\\
y’ = 0*x + 1*y + 0*z + ty*1= y + ty\\
z’ = 0*x + 0*y + 1*z + tz*1= z + tz\\
w’ = 0*x + 0*y + 0*z + 1*1= 1\\
$$


### 4.Homogeneous coordinates 齐次坐标

可以发现，三种矩阵变换的方式都是**矩阵乘矩阵**，为了将这种方式扩展到**所有的矩阵变换**我们需要加上一个**特别的坐标**

**w** 来用到我们的**3D坐标上（x，y，z）**



那么我们可以得到 ***（x，y，z，w）***，我们称之为 **齐次坐标（Homogeneous coordinates）**



和数学上的四维空间一样 ， **w对我们来说通常为1** ，因此我们常常可以忽略它，如果他不是1的话，我们则需要去 **归一化（Normalise）**



回顾之前的**三种矩阵变化**，我们可以将这个**齐次坐标**代入进去





#### 4.1  **3D Scale matrix**

<img src="https://s2.loli.net/2023/02/13/78wJh36TcHegqtX.png" alt="1676243565762" style="zoom:67%;" />





#### 4.2  **3D Translation matrix**

![1676243636016](https://s2.loli.net/2023/02/13/cAzTDJdFOB78K5v.png)



#### 4.3 **3D Rotation matrix (around X axis)**

![1676243685813](https://s2.loli.net/2023/02/13/yFiYe7MQbLPK8jr.png)





#### 4.4  **3D Rotation matrix (around Y axis)**



![1676243724882](https://s2.loli.net/2023/02/13/kYoPWAEbzJSnxus.png)







#### 4.5 **3D Rotation matrix (around Z axis)**

![1676243771285](https://s2.loli.net/2023/02/13/l4RAPpztUkGHiaX.png)







因此我们可以把所有的**矩阵变化**变成下面这种形式

用矩阵变化 **T1** 将 点 **P** 变换成 **P’**

<img src="https://s2.loli.net/2023/02/13/jEgClG85yu7ackI.png" alt="1676244036643" style="zoom:67%;" />

可以看出**决定**这个**矩阵变换**是哪种的因素在于这**16个值（a ..p)**







那么，如果我们想在一个已经变换的**P‘**上在进行一次**变换**呢？



#### 4.6 Composition transformation 组合变化




$$
Pʹʹ= T2 ⋅ Pʹ\\
Pʹʹ= T2 ⋅ T1 ⋅ P
$$


我们将**P'**在**T1的基础上**进行了第二次的**T2变换**,得到了**P'’**



这里我们称之进行了 **组合变换（Composition transformation）**

我们可以将这里的 **T1 和 T2 乘在一起 得到 Tc** ，T**c就是我们的组合变换**（composition transformation）
$$
TC = T2 *T1 \\
Pʹʹ= TC *P
$$




![1676244805821](https://s2.loli.net/2023/02/13/7Iar3ngJPj9sfTQ.png)





 **矩阵组合变换的顺序**非常重要 ，

例如：

Given two matrices **M1** and **M2**, **M1 * M2 ≠ M2 * M1**

在左边的例子中，P首先被旋转了θ，然后被(Tx,Ty)移位。在右边的例子中，P首先被(Tx,Ty)移位，然后旋转θ，结果是不同的。![1676244956223](https://s2.loli.net/2023/02/13/naMubw5rtkiG1N2.png)







矩阵组合变换在 2D 中也有着很多应用

例如：

我们在2D中怎样去尺度变换一个 **任意点 P？**

我们可以把他分为 **M1,M2,M3**三步

![1676245185421](https://s2.loli.net/2023/02/13/rzUksjFe7LBwaSp.png)





 如果我们设这个点P的坐标为（px，py），我们想去尺度变换（sx，sy）



那么我们可以把它为下面三步:

1. 建立矩阵M1使之平移（-px，-py）到原点
2. 建立矩阵M2来基于原点（-px，-py）尺度变换（sx，sy）
3. 建立矩阵M3把他平移（px，py）我们最终的目标坐标



因此 组合矩阵变换则为 **M3 · M2 · M1**

**注意顺序：M1然后M2 最后再M3**



可以看出，**关键**是是第三步 ， 我们撤销了 **M1 的效果**



#### 4.7 Undoing a transformation （撤销变换）

我们来具体分析上面的矩阵变换

矩阵A变换

Matrix **A**: shift by (Tx, Ty, Tz): 

![1676246495011](https://s2.loli.net/2023/02/13/gRZXUYhklKQAIDF.png)

矩阵B撤销矩阵A的变换

Matrix **B**: shift by (-Tx, -Ty, -Tz): 

![1676246527049](https://s2.loli.net/2023/02/13/kLFKYaMhUe8E6QR.png)

A乘B,变换抵消

Matrix product of A and B:

![1676246580449](https://s2.loli.net/2023/02/13/LvZhPEgQxBd7ik3.png)

**A** 和 **B** 被称作**互逆（Inverse）** 

因此 点 P 经过 **互逆变换 A 与 B** 最后对于 P 是没有影响的

 B 叫做 A 的 **逆矩阵**（inverse matrix）

两个互逆矩阵的乘积则为**单位矩阵**（identity matrix）
$$
A \cdot B = I
$$
**单位矩阵**的结构很简单：

1.它是“正方形”（行数与列数相同）

2.所有沿主对角线的元素都是1，而所有其他位置的元素都是0
$$
{\left[\matrix{1,0,0,0\\0,1 ,0 ,0\\0,0,1,0\\0,0,0,1}\right]}
$$


当然，不是所有的矩阵都有**逆矩阵**



例如：这个尺度变换矩阵将所有的y坐标都变为0

![1676247643981](https://s2.loli.net/2023/02/13/ECIhUDH5fXtrp4b.png)

这个矩阵没有逆矩阵因此它是 **奇异矩阵（singular matrix）**

在变换中，如果一个矩阵是**singular**的话

我们可以得到下面的信息：

![1676247861282](https://s2.loli.net/2023/02/13/OnspRoXN3GCu6D2.png)



我们可以广泛得将**组合矩阵**应用在 3D中

#### 4.8 Composition transformation in rotation  组合变换在旋转中的应用

我们来看下面这个案例：

![1676248058113](https://s2.loli.net/2023/02/13/mlLvgX7PWayFbDH.png)







我们想要绕着任意向量A旋转 θ ，但是我们只知道怎么去关于 x，y，z轴来进行旋转，我们可以把这个问题通过**组合矩阵**来一步步简化





回到我们的问题，我们希望将向量A进行旋转



![1676248413832](https://s2.loli.net/2023/02/13/JMLciFCrfRKHgV1.png)

第一步：将 A 移动到原点



![1676248477729](https://s2.loli.net/2023/02/13/dltUPDzuyHmXTOv.png)

我们将这一步写作**矩阵 M1**,我们称此时的向量**为A1**

第二步:

我们将A1 旋转至 X-Y 平面上，我们写作矩阵**M2**，现在的新向量为**A2**



![1676248569133](https://s2.loli.net/2023/02/13/niXhfwdQ4K8ETUG.png)





现在A2已经到达了x-y平面





![1676248740022](https://s2.loli.net/2023/02/13/HxjrG4MCgSkXpmf.png)



第三步：

将A2绕着Z轴旋转至和X轴重合，我们称为**M3**,并得到向量 **A3**



第四步：

我们绕着X轴旋转θ 现在变换为**M4**,我们也得到向量**A4**

第五步，第六步，第七步分别为  $M_3^-1,M_2^-1,M_1^-1$

第五步第六步第七步则是消除1，2，3带来的效果

整个变换则为:
$$
P’ = M_1
^-1 · M_2
^-1 · M_3
^-1 · M_4 · M_3 · M_2 · M_1 · P
$$






### 5.Transformations in OpenGL

OpenGL 内置了两种变换矩阵：

**modelview matrix**：用于转换你所画的几何体，并指定相机的位置。

**projection matrix**：用于控制摄像机图像投射到屏幕上的方式 
的方式投射到屏幕上

这些我们都能在 **vertexShader**里见到：
$$
P_{drawn} = ProjectionMatrix \times ModelviewMatrix \times P_{specifed} 
$$


#### 5.1 Essential vector geometry

向量给我们提供了非常方便的方式来思考物体在3D空间中的各种变换

所以，我们需要关注向量在数学中的运用



#### 5.2 Vector addition                

![1676250229877](https://s2.loli.net/2023/02/13/l6gVk7PcdmbwAOz.png)

#### 5.3 Vector subtraction

![1676250259332](https://s2.loli.net/2023/02/13/A6YcTJ2P91U7Brk.png)



向量的减法可以表达空间中的一条线

![1676250317098](https://s2.loli.net/2023/02/13/Fuj6QwpPGqUWhrK.png)

#### 5.4 Multiplication by a scalar

![1676250347311](https://s2.loli.net/2023/02/13/RW5bjenVYuBDmvE.png)

向量的标量积能够放大向量

![1676250455612](https://s2.loli.net/2023/02/13/1oLxjVrX8t2DgYB.png)

#### 5.5 Vector magnitude

![1676250503567](https://s2.loli.net/2023/02/13/SvXQ1M6qksFoRtA.png)

向量的模能够得到向量的长度

![1676250526485](https://s2.loli.net/2023/02/13/Ab5aNtrdoU6cHzT.png)

#### 5.6 Vector normalization

向量的normalization 是一个将任意非0向量 ***V*** 转换为 **长度为1** 的同向 向量 ***v*** 的过程

![1676250717631](https://s2.loli.net/2023/02/13/zYN4p7AVnb9sgdZ.png)

5.7  Vector multiplication

向量乘法分为两种：

- 点乘（dot product/inner product/scalar product）：

  根据翻译，内积又叫标量积、点积，还叫数量积。是指接受在实数R上的两个向量并返回一个实数值标量的二元运算。

![1676251014801](https://s2.loli.net/2023/02/13/Sk3utR7gsyxVimb.png)

![1676250995224](https://s2.loli.net/2023/02/13/39FqNIBQirOuRTJ.png)

- 叉乘（cross product/Out product）：

根据翻译，又称向量积、叉乘。数学中称向量积、外积、叉积，物理中称矢积、叉乘，是一种在[向量空间](https://baike.baidu.com/item/向量空间/5936597)中向量的[二元运算](https://baike.baidu.com/item/二元运算/748189)。与[点积](https://baike.baidu.com/item/点积/9648528)不同，它的运算结果是一个向量而不是一个标量。并且两个向量的叉积与这两个向量和垂直。其应用也十分广泛，通常应用于物理学光学和[计算机图形学](https://baike.baidu.com/item/计算机图形学/279486)中。

对三维空间中的两个向量和作叉积，返回一个向量，垂直于和。在三维几何中，向量a和向量b的叉乘结果是一个向量，更为熟知的叫法是法向量，该向量垂直于a和b向量构成的平面。在3D图像学中，叉乘的概念非常有用，可以通过两个向量的叉乘，生成第三个垂直于a，b的法向量，从而构建X、Y、Z坐标系。如下图所示：


<img src="https://imgconvert.csdnimg.cn/aHR0cDovL2ltZy5ibG9nLmNzZG4ubmV0LzIwMTYwOTAyMjMyODE0NDI5?x-oss-process=image/format,png" alt="img" style="zoom:50%;" />

![1676251205053](https://s2.loli.net/2023/02/13/iF2mpYROxsrJktd.png)

![1676251219371](https://s2.loli.net/2023/02/13/BOy4RaGJ6UbTHuC.png)

#### 5.7 Vector geometry is essential

向量在 3D 图像中能够定义操作几何（defining and manipulating geometry）和评估渲染（specifying and evaluating rendering）

有许多矢量操作库可供选择，它们隐藏了底层数学，使矢量操作变得简单。底层数学，使矢量操作变得容易。



### 6. Shaders 渲染 

**wiki**：**绘图流水线**（Graphics pipeline，亦称**绘图管线**）是计算机图形系统将三维模型[渲染](https://zh.wikipedia.org/wiki/渲染)到二维屏幕上的过程。[[1\]](https://zh.wikipedia.org/wiki/繪圖管線#cite_note-1)简单地说，在计算机即将显示[电子游戏](https://zh.wikipedia.org/wiki/电子游戏)或[三维动画](https://zh.wikipedia.org/wiki/三維動畫)内的[三维模型](https://zh.wikipedia.org/wiki/三维模型)时，绘图流水线就是把该模型转换成屏幕画面的过程。由于这个过程中所进行的操作严重依赖用户所使用的软件、硬件等，因此并不存在通用的绘图流水线。尽管如此，现今存在着类似[Vulkan](https://zh.wikipedia.org/wiki/Vulkan)、[OpenGL](https://zh.wikipedia.org/wiki/OpenGL)和[DirectX](https://zh.wikipedia.org/wiki/DirectX)的图形接口，将相似的操作统一起来，并把底层硬件[抽象化](https://zh.wikipedia.org/wiki/抽象化_(計算機科學))，以减轻程序员的负担。*



![1676308325188](https://s2.loli.net/2023/02/14/Z9M8kzNCY2oA6yR.png)



如图，我们将 3D 的 **vertices** 通过一系列的**算法操作**最后得到了我们

所熟悉的 **pixels**，我们称这个过程为 **绘图管线（graphic pipelines）**



![1676308539860](https://s2.loli.net/2023/02/14/JQsXw2nNcWu93Gq.png)





算法处理的具体过程分为上图中的**五步**，可以看出

**图像系统**按**固定的顺序**和**固定的算法**去处理，这些算法过程中**data**和

**参数的改变**都是由**API** 来实现的，



![1676308922162](https://s2.loli.net/2023/02/14/xrckni2dRjqaPU8.png)



wiki：

**顶点着色器（vertex shader）**

顶点着色器是最常见的一种 **3D 着色器**，对每个交给图形处理器的[顶点](https://zh.wikipedia.org/wiki/頂點_(電腦圖學))都运行一次。目的是将每个顶点在虚拟空间中的 3D 坐标变换到在屏幕上显示的 2D 坐标（[深度缓冲](https://zh.wikipedia.org/wiki/深度缓冲)（Z-Buffer）的深度值也是如此）。顶点着色器可以掌控顶点的位置、颜色和[纹理坐标](https://zh.wikipedia.org/w/index.php?title=纹理坐标&action=edit&redlink=1)等属性，但无法生成新的顶点。顶点着色器的输出传递到流水线的下一步。如果有之后定义了[几何着色器](https://zh.wikipedia.org/wiki/幾何著色器)，则几何着色器会处理顶点着色器的输出数据，否则，[光栅化器](https://zh.wikipedia.org/wiki/光栅化器)继续流水线任务。

**片段着色器（fragment shader）**

，用于计算“片段”的[颜色](https://zh.wikipedia.org/wiki/颜色)和其它属性，此处的“片段”通常是指单独的[像素](https://zh.wikipedia.org/wiki/像素)。最简单的像素着色器只有输出**颜色值**；复杂的像素着色器可以有多个输入输出[[4\]](https://zh.wikipedia.org/wiki/着色器#cite_note-4)。像素着色器既可以永远输出同一个颜色，也可以考虑光照、做[凹凸贴图](https://zh.wikipedia.org/wiki/凹凸贴图)、生成[阴影](https://zh.wikipedia.org/wiki/陰影)和[高光](https://zh.wikipedia.org/wiki/高光)，还可以实现半透明等效果。像素着色器还可以修改片段的[深度](https://zh.wikipedia.org/wiki/深度缓冲)，也可以为多个渲染目标输出多个颜色。

三维图形学中，单独一个像素着色器并不能实现非常复杂的效果，因为它只能处理单独的像素，没有场景中其它几何体的信息。不过，像素着色器有屏幕坐标信息，如果将屏幕上的内容作为纹理传入，它就可以对当前像素附近的像素进行采样。利用这种方法，可以实现大量二维后期特效，例如模糊和[边缘检测](https://zh.wikipedia.org/wiki/边缘检测)。

像素着色器还可以处理管线中间过程中的任何二维图像，包括[精灵](https://zh.wikipedia.org/wiki/精灵图)和[纹理](https://zh.wikipedia.org/wiki/纹理贴图)。因此，如果需要在[栅格化](https://zh.wikipedia.org/wiki/栅格化)后进行后期处理，像素着色器是唯一选择。



所有的形状都是由**顶点（vertex）**构成的，**顶点着色器**一次接受一个顶点然后再进行下面的加工过程，当顶点在2D平面上出现时我们要设定 **gl_position** 的值，然后信息最后传到片段处理器上，**片段着色器**必须设定 **gl_FragColor** 的值作为最后的颜色





**Input** to the vertexShader：

![1676310859485](https://s2.loli.net/2023/02/14/rJqY1dP3xnRkw72.png)







**Simplest vertexShader**：

```glsl
// projection and modelView are provided by three.js 
void main () 
{ 
 gl_Position = projectionMatrix 
 modelViewMatrix 
 vec4(position, 1.0); 
}
```



**main（）**时 shader program 的**入口**

vec(position,1.0) 将3D空间的向量变成**四维向量**

**gl_position** 代表了 vertex 在 3D 空间中的位置，



**projectionMatrix**  代表了投影变换将场景中的三维点映射到一个二维平面，这就是最终渲染的图像平面。



In between the vertex and fragment shaders



![1676312551342](https://s2.loli.net/2023/02/14/j2QaSR5O1P9yX3d.png)



![1676312573469](https://s2.loli.net/2023/02/14/g4lqRenBDf7YGMb.png)



Simplest fragmentShader

```javascript
void main () 
{ 
 gl_FragColor = vec4(1.0, 0.0, 1.0, 1.0); 
 // RGBa 
}
```



How do the shaders get data?

![1676312622843](https://s2.loli.net/2023/02/14/VLBwpGZ9o7XYbrh.png)







## Week 3  Polygons and pixels



### 1.What is a polygon? 什么是多边体

- An ordered set of vertices ($V_1$…$V_N$)

- A set of edges between each pair of vertices ($E_1$…$E_N$) 

- The polygon (P) is then the space bounded by the vertices

  

<img src="https://s2.loli.net/2023/03/03/GwgCJplEPnQ5Zka.png" alt="1677801185404" style="zoom: 50%;" />



- OpenGL needs convex polygons

  

<img src="C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1677801322963.png" alt="1677801322963" style="zoom:33%;" />

<img src="https://s2.loli.net/2023/03/03/FPsz2OGCVXtDES5.png" alt="1677801340818" style="zoom:33%;" />



### 2.Tessellation

![1677801388158](https://s2.loli.net/2023/03/03/7cw5Okgif4yMLsG.png)

### 3. Surface Normal

![1677801419862](https://s2.loli.net/2023/03/03/JMXYOVH4ZT8rBWi.png)

- Finding the surface normal

1. Choose a pair of sequential edges $E_1$ and $E_2$ and compute their vectors
2. Invert the direction of the first so they now emanate from their shared vertex
3. Their cross product gives the surface normal N
4. $E=E_2 \times -E_1$
5. We then almost always normalize N (make its length 1)

<img src="https://s2.loli.net/2023/03/03/kWmIcQEg1XHD7Fv.png" alt="1677801692111" style="zoom:67%;" />





### 4.Representing scenes with polygons

- Polygon soup 

  <img src="C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1677801794521.png" alt="1677801794521" style="zoom:67%;" />

- Polygon meshes 

  ​         
  
  <img src="https://s2.loli.net/2023/03/03/2bFlupzevwHNMWJ.png" alt="1677839400855" style="zoom: 50%;" />



<img src="https://s2.loli.net/2023/03/03/7e8lzypj9aOfH6E.png" alt="1677839465996" style="zoom: 50%;" />



- Triangle strip in OpenGL

  ```
  glBegin(GL_TRIANGLE_STRIP);
   glVertex3f(x0, y0, z0);
   glVertex3f(x1, y1, z1);
   glVertex3f(x2, y2, z2);
   glVertex3f(x3, y3, z3);
   /* and similar for more vertices */
  glEnd();
  ```

  

- Meshes: Triangle fan 

  

<img src="https://s2.loli.net/2023/03/03/sOQESepqriM2YB4.png" alt="1677840802994" style="zoom:50%;" />

​      **N** linked triangles can be defined using **N+2** vertices – compared with **3N** vertices if each triangle were defined separately

```
glBegin(GL_TRIANGLE_FAN);
 glVertex3f(x0, y0, z0);
 glVertex3f(x1, y1, z1);
 glVertex3f(x2, y2, z2);
 /* etc */
glEnd();

```

- Meshes: quadrilateral strips

  <img src="https://s2.loli.net/2023/03/03/vR9JfDWZ6dtPmAc.png" alt="1677841085354" style="zoom:67%;" />

```
glBegin(GL_QUAD_STRIP);
 glVertex3f(x0, y0, z0);
 glVertex3f(x1, y1, z1);
 glVertex3f(x2, y2, z2);
 glVertex3f(x3, y3, z3);
 /* etc */
glEnd();
```



<img src="https://s2.loli.net/2023/03/03/M1mJKIdWuqX8xD5.png" alt="1677841157593" style="zoom: 67%;" />



- Meshes: quadrilateral meshes

  <img src="https://s2.loli.net/2023/03/03/KrH2h7RSmWYV5gj.png" alt="1677841242517" style="zoom: 50%;" />

**N x M** quads can be defined using **(N+1) * (M+1)** vertices, compared with 4 M*N* separate vertices























### 5. Scan-converting a line 







- We sample the true geometry of the line, and **approximate** it using the nearest pixels available.

<img src="https://s2.loli.net/2023/03/06/1FXUcwfkbs26olY.png" alt="image-20230305164945755" style="zoom:67%;" />



- Bresenham’s algorithm

​	$y = mx + c $

​	As we move horizontally x changes by 1 pixel 

​	So $y_n+1 = y_n + m$

​	Round  $y_n+1$  to the nearest pixel 

​    Need to swap x and y according to gradient of the line

​    Bresenham (1965) developed a fast algorithm using only integer arithmetic 

​     Still in use today

​     <img src="https://s2.loli.net/2023/03/06/ys76V1iG39QahIC.png" alt="image-20230305165340189" style="zoom:50%;" />

### 6. Scan converting a polygon



<img src="https://s2.loli.net/2023/03/06/AQecxZdFoRMfX3C.png" alt="image-20230305165510069" style="zoom:50%;" />

There are many approaches to scanconverting a polygon, and we’ll look at two

The polygon has been transformed by the viewing pipeline, so we know its (x,y,z) vertex coordinates in screen space 

The (x,y) coordinates corresponds to a pixel position 

The z coordinate is a measure of the vertex’s distance from the eye (or "camera"). We won’t use that information just yet. 



- Scan converting a triangle

​                                                          



   We can scan-convert each of the edges.



<img src="https://s2.loli.net/2023/03/06/NowaZStCYglcUMA.png" alt="image-20230305165722577" style="zoom:50%;" />



Now we can process each row of pixels and fill in the remaining interior pixels.



<img src="https://s2.loli.net/2023/03/06/1RCqW8nzrjSymBK.png" alt="image-20230305165843275" style="zoom:50%;" />


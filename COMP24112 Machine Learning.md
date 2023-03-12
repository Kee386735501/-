# COMP24112 Machine Learning 

# Week 1 Machine Learning Basic

## 1.1 What is machine learning 

- A machine learning system can be used to   

   Automate a process 

   Automate decision making 

   Extract future event 

    Predict future event     

- Machine Learning writes code to **make the computer** 

  **learn form data** how to do the above tasks

- Machine Learning is important in ds and ai 

## 1.2  Machine Learning Strategy 

  <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131144049265.png" alt="image-20230131144049265" style="zoom:67%;" />

- Data X: collection of experience E. 
- Function f: Function output provides answers/solutions to Task T
- Parameters θ: control model behaviour
- Objective function O(θ): It computes a performance P of task T.
- Optimisation min O(θ): learning (or training).

## 1.3 What is Optimisation 

- Mathematic optimisation(a branch of applied mathmematics)

- finds the input that can given the minumum (or maxium) output value of a real valued function 

## 1.4 Example  MCQ course 

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131163518113.png" alt="image-20230131163518113" style="zoom:50%;" />

​                                                       <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131163710549.png" alt="image-20230131163710549" style="zoom:50%;" />

​                                                       <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131163829764.png" alt="image-20230131163829764" style="zoom:50%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131163910948.png" alt="image-20230131163910948" style="zoom:50%;" />

​                                                       <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131164050742.png" alt="image-20230131164050742" style="zoom:50%;" /> 

​                                                       <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131164216558.png" alt="image-20230131164216558" style="zoom:50%;" />  

​                                                        只有0 或 1 作为答案的 是 classification 

​                                                         <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131164615816.png" alt="image-20230131164615816" style="zoom:50%;" />

​                                                        <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131164857686.png" alt="image-20230131164857686" style="zoom:50%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131165027587.png" alt="image-20230131165027587" style="zoom:50%;" />

​                                                     <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131165059313.png" alt="image-20230131165059313" style="zoom:50%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131194213622.png" alt="image-20230131194213622" style="zoom:50%;" />

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131194226836.png" alt="image-20230131194226836" style="zoom:50%;" />

​           选d 

## 1.5 Machine Learning Pipline 

Key stages in building a **machine learning system**: 

***Model Contruction:***

- To prepare **experience(E)** in proper **data** format 
- To characterise a **task(T)** by a **parametric model** 
- To characterise a performance **metric(P)** by an **objective function**

***Training:***

- To determine the model through **optimising** the objectives function

***Evaluation***: 

-    To assess the determined model through model using a performance metric        

Machine learning pipeline builds on optimisation theory,linear algebra , probability theory 

##   1.6 例子——葡萄辨别

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131194116235.png" alt="image-20230131194116235" style="zoom: 67%;" />

​                 我们需要判断这个葡萄酒是由下面哪种葡萄生产出来的 ，对于人来说可以直接通过品尝的方式和闻气味的方式直接判断，但是对于电脑来说就不一样了。  

​                我们首先要收集葡萄各种feature的 data 

​                      ![image-20230131194421574](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131194421574.png)

​              然后再将这些数据整理出来 ， 

​           Task：基于葡萄种类不同导致的各种feature 的measurement 不同 从而识别葡萄的种类 

​            Experience：  

​             <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131194702117.png" alt="image-20230131194702117" style="zoom:67%;" />

​              13种feature不同的测量值整理出来

​              Model：  

​              我们设计一个数学模型来预测出葡萄的种类，这个模型基于w1 到 w13 

​                  <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131194912933.png" alt="image-20230131194912933" style="zoom:67%;" />

​             对于这里的 w0 我们需要找到一个最好的值通过optimising也就是下面的 system traning

​             System Training： 

​               找到best model parameter 通过 minimising 一个 loss function  来找 performance 最好的值（匹配程度最高的）

​               <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131195106317.png" alt="image-20230131195106317" style="zoom:67%;" />



## 1.7 Machine Learning Ingredient 

**Data**: (Experience)

**Model**:A piece of code(model function) with some parameter that need to be optimised 

**Loss Function**: The function u use to judge how well the parameter of the model are set.it's also called error function , cost function , objective function

**Training algorithm**: The alg that optimises the model parameters,using the error function to judge how well a model is performing



## 1.8 Supervised Learning 

- the machine learning task of learning a function that **maps an input  to an output** based on example input-output pairs 

  - There is a "teacher" provide a **target output** for each data pattern  
  - A **pair** of input data pattern and its output is called a **training example**
  - Typically supervised learning tasks inclue **classfication** and **regression** ,differing from their output type 

  

  简单来说就是给定一定的训练样本(这里一定要注意，样本是既有数据，也有数据对应的结果)，利用这个样本进行训练得到一个模型(可以说是一个函数)，然后利用这个模型，将所有的输入映射为相应的输出，之后对输出进行简单的判断从而达到了分类(或者说回归)的问题。简单做一个区分，分类就是离散的数据，回归就是连续的数据。

  

## 1.9 Unsupervised Learning 

- Unsupervised learning is a type of algorithm that learns pattern from **untagged data** (也就是单纯的数据不是pair)
  - There is no explicit "teacher" (不存在一个 teacher )
  -  The system form a natural "understanding " of the hidden structure from unlabled data 

同样，给了样本，但是这个样本是只有数据，但是没有其对应的结果，要求直接对数据进行分析建模。

比如我们去参观一个画展，我们完全对艺术一无所知，但是欣赏完多幅作品之后，我们也能把它们分成不同的派别(比如哪些更朦胧一点，哪些更写实一些，即使我们不知道什么时候叫做朦胧派，什么叫做写实派，但是至少我们能够把它们分为两类)。无监督学习里面典型的例子就是聚类，聚类的目的在于把相似的东西聚在一起，而我们并不关心这一类是什么，因此，一个聚类算法通常只需要知道如何计算相似度就可以开始工作了。

“再比如，买房的时候，给了房屋面积以及其对应的价格，进行分析，这个就叫做监督学习；但是给了面积，没有给价格，就叫做非监督学习。监督，意味着给了一个标准作为'监督' (或者理解为限制)。就是说建模之后是有一个标准用来衡量你的对与错；非监督就是没有这个标准，对数据进行聚类之后，并没有一个标准进行对其的衡量。”

- Typical unsupervised learning tasks inclue 

  - Clustering(聚类) : group similar data pattern together

  - Generative modelling: estimate distribution of the observed data pattern (对已观测的数据的分布进行预估，去除多余的数据...)

  - Unsupervised representation learning : remove noise , caputure data , statistic , capture inherent data structure 

    

## 1.10 Reinforcement Learning 

Reinforcement Learning is an area of machine learning concerned with how intelligent **agents ought to take actions in an environment** in order to **maximize the notion of cumulative reward** 

- There is a "teacher" who provides feedback on the action of an agent , in term of **reward and punishment**

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131204202769.png" alt="image-20230131204202769" style="zoom:67%;" />

强化学习算法的思路非常简单，以游戏为例，如果在游戏中采取某种策略可以取得较高的得分，那么就进一步“强化”这种策略，以期继续取得较好的结果。这种策略与日常生活中的各种“绩效奖励”非常类似。我们平时也常常用这样的策略来提高自己的游戏水平。

在 Flappy bird 这个游戏中，我们需要简单的点击操作来控制小鸟，躲过各种水管，飞的越远越好，因为飞的越远就能获得更高的积分奖励。

这就是一个典型的强化学习场景：

- 机器有一个明确的小鸟角色——agent
- 需要控制小鸟飞的更远——target
- 整个游戏过程中需要躲避各种水管——environment
- 躲避水管的方法是让小鸟用力飞一下——action
- 飞的越远，就会获得越多的积分——reward

<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230131204702659.png" alt="image-20230131204702659" style="zoom:67%;" />

你会发现，强化学习和监督学习、无监督学习 最大的不同就是不需要大量的“数据喂养”。而是通过自己不停的尝试来学会某些技能。

## 1.11 Classfication and Regression

- Classfication and regression are both **supervised learning tasks**, but differ in **output types** 
- Classfication(class output):
  -  Goal : Identify which categories a **data pattern** belongs to
  - Training data: Observed data pattern and their **category memberships** 
- Regression(continuous output):
  -   Goal : Estimate the relationship among the input and output variables 
  - Training data: Obeserved input variables and their correspoding **continuous output variables**

          分类问题是用于将事物打上一个标签，通常结果为离散值。例如判断一幅图片上的动物是一只猫还是一只狗，分类通常是建立在回归之上，分类的最后一层通常要使用softmax函数进行判断其所属类别。分类并没有逼近的概念，最终正确结果只有一个，错误的就是错误的，不会有相近的概念。最常见的分类方法是逻辑回归，或者叫逻辑分类。
      
       回归问题通常是用来预测一个值，如预测房价、未来的天气情况等等，例如一个产品的实际价格为500元，通过回归分析预测值为499元，我们认为这是一个比较好的回归分析。一个比较常见的回归算法是线性回归算法（LR）。另外，回归分析用在神经网络上，其最上层是不需要加上softmax函数的，而是直接对前一层累加即可。回归是对真实值的一种逼近预测。
## 1.12 Different Types Of  Classification 

- There are different types of classification tasks.

  - Binary classification: classify into **one** of the **two** classes.

  - Multi-class classification: classify into **one** of the **many** classes.

  - Multi-label classification: classify into **some** of the **many** classes

  - Structured classification: classify into **structured** classes Classes can be organised in sequence, tree, lattices, graph.

    

# Week 2  k-Nearest Neighbours  

## 2.1 History

- k-NN is the simplest of all machine learning algorithm 
- The philosophy behind k-NN dates back very early







## 2.2 K-NN Classification  

​			<img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207134106768.png" alt="image-20230207134106768" style="zoom:67%;" />

  Iris Classification 

  ![image-20230207134428423](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207134428423.png)

根据花的萼片长度和花瓣宽度作为特征来classify 三种花的类别





##  2.3 k-NN Classification Rule 

-  已知一组training samples  {features，class labels}

- 每组sample 都对应一个 data point 在 feature space上

- **k--NN classification rule** 

   **Testing point**  ***X*te**  测试点 

   对于 **training data** **point** ***Xtr***  训练数据点
   
   计算 **distance (Xte,Xtr)**
   
   End 
   
   将distances 进行排序 
   
   Select 出K个距离最近的点
   
   Assign 出（most common class） 出现频率最高的类
   
   ​                    ![image-20230207225744005](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207225744005.png)
   
   ​                               **majority voting**

****

   <img src="C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207230056243.png" alt="image-20230207230056243" style="zoom:67%;" />

  ![image-20230208004044749](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208004044749.png)











## 2.4 k-NN Regression 

​    ![image-20230207230830956](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207230830956.png)













##  2.5 **k-NN Regression Rule** 

- 已知一组 training samples {feature，output}

- 每组sample 都对应一个 data point 在 feature space上

- k-NN regression Rule 

  

  ​		 **k--NN regression rule** 

  

  ***Testing point**  **Xte**  测试点* （input）

  *对于 **training data** **point** **Xtr**  **训练数据点***

  *测量 **distance (Xte,Xtr)***

  *End* 

  *将 distances 进行**排序*** 

  *Select 出K个距离**最近**的点 : Xnn1，Xnn2 ... Xnnk*

  *计算 Yte 这些点的**平均值** :*

   *Yte = (Ynn1，Ynn2 ... Ynnk )  /  K*

​                 ![image-20230207232039656](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207232039656.png)

   ![image-20230207232120069](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207232120069.png)

**我们的测试点是 Xte = 6  ，距离最近的三个 Xtr 为 Xnn1= 6.1，   Xnn2 = 5.9 ， Xnn3 = 5.7  可以计算出 yNN1= -0.1822，yNN2= -0.3739, yNN3 = -0.5507 . 所以 Average 可以计算出来 -0.3689**

  思考：上图的regression 的范围仅仅是在 【-20，20】这个区间上面是成立的 ， 如果我们的测试数据超过了这话范围那么我们的3-NN 是否还可靠？









![image-20230207233141354](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207233141354.png)

  ![image-20230207233232992](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207233232992.png)

![image-20230207233349480](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207233349480.png)

![image-20230207233740285](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207233740285.png)

![image-20230207233832016](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207233832016.png)

![image-20230207233847604](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207233847604.png)







## 2.6 Instance-based Learning

- 很多的算法都是基于相似度或者距离来在 **training set** 里面去找出 **”最相近“** （NN)的
- 这种算法统称为 k-NN 算法 
- 需要思考的点：
  1.   如何计算距离
  2.   如何选出 K (最近的几个) 
  3.   如何推断出最近点的 output   









## 2.7 Distance  Measure 

1.  欧几里得距离 Euclidean Distance 

   ![image-20230207235004114](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207235004114.png)

2. 明可夫斯基距离 Minkowski Distance 

   ![image-20230207235843692](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207235843692.png)

   两点

   ![{\displaystyle P=(x_{1},x_{2},\ldots ,x_{n}){\text{ and }}Q=(y_{1},y_{2},\ldots ,y_{n})\in \mathbb {R} ^{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ae41df02f02c7f837b06c1f5146aa0693cdbc5b9)

   之间的明氏距离公式为：

   ![{\displaystyle \left(\sum _{i=1}^{n}|x_{i}-y_{i}|^{p}\right)^{1/p}.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fff874830761e929d94ce49f016e60581cc8b2ee)

   p取1或2时的明氏距离是最为常用的，p=2即为[欧氏距离](https://zh.wikipedia.org/wiki/欧氏距离)，而p=1时则为[曼哈顿距离](https://zh.wikipedia.org/wiki/曼哈頓距離)。当p取无穷时的极限情况下，可以得到[切比雪夫距离](https://zh.wikipedia.org/wiki/切比雪夫距离)：

   ![{\displaystyle \lim _{p\to \infty }{\left(\sum _{i=1}^{n}|x_{i}-y_{i}|^{p}\right)^{\frac {1}{p}}}=\max _{i=1}^{n}|x_{i}-y_{i}|.\,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a25e6422d6342df00a038d97507e8ff9a6d56b04)

3. 曼哈顿距离  Manhattan Distance

   <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/Manhattan_distance.svg/300px-Manhattan_distance.svg.png" alt="img" style="zoom:67%;" />

**计程车几何**（Taxicab geometry）或**曼哈顿距离**（英语：Manhattan distance/Manhattan length）或**方格线距离**是由[十九世纪](https://zh.wikipedia.org/wiki/十九世紀)的[赫尔曼·闵可夫斯基](https://zh.wikipedia.org/wiki/赫尔曼·闵可夫斯基)所创辞汇，为[欧几里得几何](https://zh.wikipedia.org/wiki/歐幾里得幾何)[度量空间](https://zh.wikipedia.org/wiki/度量空间)的[几何学](https://zh.wikipedia.org/wiki/幾何學)之用语，用以标明两个点上在标准[坐标系](https://zh.wikipedia.org/wiki/坐標系)上的绝对轴距之总和。我们可以定义**曼哈顿距离**的正式意义为**L1-距离**或**城市区块距离**（City Block），也就是在[欧几里得空间](https://zh.wikipedia.org/wiki/欧几里得空间)的固定[直角坐标系](https://zh.wikipedia.org/wiki/直角坐标系)上两点所形成的[线段](https://zh.wikipedia.org/wiki/线段)对轴产生的投影的距离总和。

例如在[平面](https://zh.wikipedia.org/wiki/平面_(数学))上，坐标（*x*1, *y*1）的点*P*1与坐标（*x*2, *y*2）的点*P*2的曼哈顿距离为：

![{\displaystyle d(x,y)=\left|x_{1}-x_{2}\right|+\left|y_{1}-y_{2}\right|.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1430091e78a7f8e98eb3e3847d1c172f64665539)







## 2.8 Similarity Measure 

![image-20230207235924327](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230207235924327.png)

Convert cosine to distance:

![image-20230208000000241](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208000000241.png)

![image-20230208000015628](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208000015628.png)



similarity 在 文本上使用多一些 （文本出现的频率） 

而欧式距离则是图片比较多一点







## 2.9 Effect of Training Sample 

- 使用少的 Training Sample 

   信息不够充分

- 大量的 Training Sample

​       更多的信息 ，但是会花费更多的时间和内存

-   Noisy Training Sample 

   判断不够准确

​    



例1 在 1-NN classifer 中 我们 training sample 过少的话 ，放入更多training sample的话会明显出现 error 因为信息不充分

![image-20230208003903545](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208003903545.png)

![image-20230208004307058](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208004307058.png)

![image-20230208004327988](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208004327988.png)

![image-20230208004419675](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208004419675.png)

当我们不断去提升训练数据时，我们的error rate 会明显下降 ， accuracy 会有一个明显的提升

![image-20230208100053778](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208100053778.png)

上图的红色区域因为没有足够的训练sample 所以红色部分会变小变成绿色

![image-20230208100108037](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208100108037.png)

![image-20230208100156268](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208100156268.png)

![image-20230208100220905](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208100220905.png)

在这个例子中圈内的蓝色训练sample 过多 所以当我们predict新的 value的时候这一块很容易classfy成蓝色 ， 所以我们不能对于某个数据在某个区域的数据过多 overfit



## 2.10 Neighbour Number k 



- Hyper-parameter :  neighbour number k         **近邻常数 k**
- 决定近邻常数 K 的过程被称作 hyper-paramer selection 或者 model selection
- 在一个 binary classification 中 最好不要用偶数  K
- K 取大了可以减小 model noise ，但是会影响 prediction
- K取小了noise 会变大

​     如何选择一个最佳的K值取决于数据。一般情况下，在分类时较大的K值能够减小噪声的影响，但会使类别之间的界限变得模糊。一个较好的K值能通过各种启发式技术来获取。

噪声和非相关性特征的存在，或特征尺度与它们的重要性不一致会使K近邻算法的准确性严重降低。对于选取和缩放特征来改善分类已经作了很多研究。一个普遍的做法是利用[进化算法](https://zh.wikipedia.org/wiki/进化算法)优化功能扩展，还有一种较普遍的方法是利用训练样本的[互信息](https://zh.wikipedia.org/wiki/互信息)进行选择特征。

在二元（两类）分类问题中，选取*k*为奇数有助于避免两个分类平票的情形。在此问题下，选取最佳经验*k*值的方法是自助法。



![image-20230208103103868](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208103103868.png)

![image-20230208103134227](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208103134227.png)

![image-20230208103238106](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208103238106.png)

![image-20230208103415212](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208103415212.png)

![image-20230208112141394](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208112141394.png)



![image-20230208113035263](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208113035263.png)



![image-20230208113101541](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230208113101541.png)



## 2.11 Neighbour Search Algorithm

Study fast computation of nearest neighbours is an active research area in machine learning. 

• Naïve Approach: brute-force compute distances between all pairs of samples and sort. 

• Tree-based methods: 

– Basic idea: Knowing A is very distant from B, and B is very close to C, it is certain that A and C are very distant, without having to explicitly calculate their distance. Apply this to reduce the number of distance calculations.  

– Variaties: K-D tree, Ball tree, etc 

 

# Week 3  Machine Learning Experiments



## 3.1.Measure Classification Performance



<img src="https://s2.loli.net/2023/02/27/UzRKIgXHMShtNA6.png" alt="1677449005499" style="zoom:67%;" />







## 3.2 Classification Accuracy and Error



- **Correct**: Sample 1 is truly from Class A and assigned to Class A by a machine learning model.
- **Error**: Sample 1 is truly from Class A but assigned to Class B by a machine learning model
- $ Classification\, accuracy=\frac{number\,of\, correctly\, classified \,samples}{total\, sample\, number}$

- $ Classification\,error\, rate=\frac{number\,of\, wrongly\, classified \,samples}{total\, sample\, number}$





为什么不只用 Accuracy 和 Error ？



 Disadvantage 1 ：**精确率**和**错误率**有可能都来自一组不均衡的数据



- Example：Given 95 samples from class A and 5 samples from class B

- A classifier assigns all the samples to class A.
- Accuracy 95%, but this is NOT a good classifier



Disadvantage 2 ：可能不足以来辨别出分类的特性



- ![1677450082925](https://s2.loli.net/2023/02/27/E7P6IsNV4wnLpJR.png)

绿色代表正确，红色代表错误，很明显这两个classifier的精确度都是60%但是，Classifier1 判断B 更好，Classfier2 判断A 更好



能解决这个问题的方法有两种



- error matrix 

![1677450347546](https://s2.loli.net/2023/02/27/J9i63Pe8OKkHjUW.png)



- 2x2 confusion matrix

  Report the number of **false positives (FP), false negatives (FN), true positives (TP), and true negatives (TN).** 

![1677450424439](https://s2.loli.net/2023/02/27/6oBimQveqrsh5Ig.png)



Precision和Recall是二分类问题中的两个评估指标，通常用于衡量模型的性能。

Precision指模型在所有预测为正例的样本中，实际上是正例的样本占比，即：

**Precision = TP / (TP + FP)**

其中TP是真正例的数量，FP是假正例的数量。

Recall指模型在所有真正例的样本中，成功预测为正例的样本占比，即：

**Recall = TP / (TP + FN)**

其中TP是真正例的数量，FN是假反例的数量。

在理想情况下，我们希望Precision和Recall都能够很高。但是，在某些情况下，它们之间存在一个折衷关系。例如，在一个非常严格的分类问题中，一个模型可能会偏向于更保守的预测，从而减少假正例的数量，但这也会增加假反例的数量，从而降低Recall。相反，如果一个模型更倾向于做出更多的预测，即使其中有一些是假正例，也会增加真正例的数量，从而提高Recall，但同时也会降低Precision。

因此，我们需要根据具体问题来选择合适的评估指标。在某些情况下，我们可能更关心Precision，例如在假阳性会导致严重后果的情况下。在其他情况下，我们可能更关心Recall，例如在需要找到尽可能多的正例的情况下。



Specificity（特异性）是指二分类问题中负类样本（实际上是负例）被正确分类的比例。具体地说，它表示所有实际上是负例的样本中，被分类器正确分类为负例的比例。它可以用以下公式表示：

**Specificity = TN / (TN + FP)**

其中，TN表示真负例的数量，FP表示假正例的数量。与Recall和Precision不同，Specificity是一种度量分类器在负类样本方面的性能的指标。

Specificity通常用于评估二分类问题中分类器的性能，尤其是在负类样本非常重要的情况下。例如，在医学诊断中，假阳性可能会导致错误的治疗决策，因此Specificity可以帮助评估一个诊断系统在准确识别正常人群的方面的能力。

需要注意的是，Specificity和Recall之间存在一种权衡关系，提高Specificity可能会降低Recall。因此，在选择评估指标时，需要根据具体问题的特点和应用场景进行综合考虑。







## 3.3 Regression error

Regression error（回归误差）是指在回归分析中，**模型预测结果与实际结果之间的差异或误差**。回归误差可以用不同的指标来衡量，如均方误差（Mean Squared Error，MSE）、平均绝对误差（Mean Absolute Error，MAE）、平均绝对百分比误差（Mean Absolute Percentage Error，MAPE）等。





![1677451134975](https://s2.loli.net/2023/02/27/7iQw6yoN3IPeSBM.png)

![1677451200642](https://s2.loli.net/2023/02/27/RjCaW9JLZKdD1h8.png)

## 3.4 Sample Error and True Error 



Hypothsis: 训练模型所作的预测

- **Sample error：Sample Error（样本误差）（$error_s$）**

Error computed by a performance metric using a set of data samples.

- True error:True Error（真实误差）($error_D$)

1. For classification, it is the probability that a single sample is misclassified, where the sample is randomly drawn from a distribution.

   2.For regression case, it is the expectation of the error

![1677452211422](https://s2.loli.net/2023/02/27/csIlenwtRh6NEfv.png)



What we wish to know is the true error. 

• In most cases, it is very hard or not possible to compute the true error. 

• We can always compute the sample error. 

• Infinite samples: Sample error converges to true error.

 • Insufficient samples: Sample error may not approximate true error well.



## 3.5 Limited Data: Bias and Variance Issues

在机器学习中，数据量的大小对模型的性能和泛化能力有很大的影响。当数据量较少时，模型容易产生Bias和Variance问题。

Bias问题（偏差问题）是指模型在训练集上表现不佳，预测结果与真实值之间存在较大偏差的情况。一般来说，Bias问题通常是由于模型过于简单而导致的，即模型无法捕捉数据的真实特征，从而产生了较大的误差。为了解决Bias问题，我们可以增加模型的复杂度，使用更复杂的模型来拟合数据，从而提高模型的拟合能力和准确性。

Variance问题（方差问题）是指模型在测试集上表现不佳，泛化能力较差，预测结果的方差较大的情况。一般来说，Variance问题通常是由于模型过于复杂而导致的，即模型过度拟合了训练数据，从而无法很好地适应新数据，产生了较大的误差。为了解决Variance问题，我们可以采用一些正则化方法，如L1正则化、L2正则化等，限制模型的复杂度，避免过度拟合。

当数据量较少时，Bias和Variance问题同时存在，这称为Limited Data问题（数据有限问题）。在这种情况下，我们需要权衡Bias和Variance之间的关系，选择一个适当的模型复杂度，以获得较好的泛化性能。通常来说，我们可以采用一些经验方法来解决Limited Data问题，如增加数据量、采用交叉验证等方法，从而提高模型的泛化能力和准确性。



## 3.6 Holdout 方法

- 将数据分为训练集（70-80%）和测试集（20-30%）
- 用训练集来训练数据，用测试集来评估误差



holdout方法的缺点：

- 如果数据太小就不好分了
- 如果因为一些偶然的因素导致测试误差不等于测试误差的话就不准确了





## 3.7 Random Subsampling

Random Subsampling是一种数据集划分方法，也是一种交叉验证的形式，用于评估机器学习模型的泛化能力。

在Random Subsampling中，我们将原始数据集随机地分成许多个子集，通常将数据集分成n个子集，每个子集的数据量相同或者相近。然后，我们从这n个子集中选取k个子集作为训练集，将剩下的n-k个子集作为测试集。这个过程会重复进行m次，直到每个子集都被用作了一次测试集。最终，我们将这m次评估的结果取平均值作为模型的性能评估结果。

Random Subsampling的优点是能够充分利用数据集中的所有数据，避免了Holdout Method中数据不足的问题。同时，由于重复进行多次，评估结果相对Holdout Method更加准确。缺点是由于需要多次训练模型，计算量较大，对计算资源的要求较高。

总的来说，Random Subsampling是一种简单、有效的评估模型性能的方法，特别适用于数据量较小的情况下。但是，它也存在着计算量较大、评估结果不稳定等缺点。因此，在使用Random Subsampling时，需要根据实际情况进行选择和调整。

![1677453276511](https://s2.loli.net/2023/02/27/Xv82QqHIYKeRJAW.png)



## 3.8 K-fold Cross Validation 



K-fold Cross Validation是一种常用的交叉验证方法，用于评估机器学习模型的泛化能力。

在K-fold Cross Validation中，我们将原始数据集随机地分成k个子集，通常将数据集分成k个子集，每个子集的数据量相同或者相近。然后，我们从这k个子集中选取一个子集作为测试集，将剩下的k-1个子集作为训练集。这个过程会重复进行k次，每次选择一个不同的子集作为测试集。最终，我们将这k次评估的结果取平均值作为模型的性能评估结果。

K-fold Cross Validation的优点是可以充分利用数据集中的所有数据，减少了数据不足的问题。同时，由于重复进行多次，评估结果相对Holdout Method更加准确。此外，K-fold Cross Validation也比Random Subsampling更加稳定，能够避免一些偶然情况对模型评估结果的影响。

缺点是由于需要多次训练模型，计算量较大，对计算资源的要求较高。此外，K-fold Cross Validation也可能存在过拟合的问题，即模型在训练集上的表现很好，但在测试集上的表现很差，需要注意避免。

总的来说，K-fold Cross Validation是一种比较稳定、有效的评估模型性能的方法，特别适用于数据量较小的情况下。但是，它也存在着计算量较大、存在过拟合等缺点。因此，在使用K-fold Cross Validation时，需要根据实际情况进行选择和调整。

![1677454021652](https://s2.loli.net/2023/02/27/GLgDM4HbZlOcJdk.png)



Comments on K-fold CV

- Each sample is used as the testing samples only once, but as the training samples K-1 times.
- All the test sets are independent, but there is overlapping between training sets
- Low number of K results in insufficient training-testing trials.
- High number of K results in small testing set potentially with high variance.
- Some standard settings: 10-fold CV, 5-fold CV.



## 3.9 Leave One Out

Leave-One-Out Cross Validation（留一交叉验证）是一种交叉验证方法，它将原始数据集中的一个样本作为测试集，其余的样本作为训练集。对于一个含有n个样本的数据集，Leave-One-Out Cross Validation会进行n次训练和测试，每次将不同的一个样本作为测试集，其余的n-1个样本作为训练集。最终将n次测试的结果取平均值作为模型的性能评估结果。

相对于K-fold Cross Validation，Leave-One-Out Cross Validation的主要优点在于能够更充分地利用数据集中的所有数据，并且能够更准确地评估模型的性能。但是，Leave-One-Out Cross Validation的计算量很大，尤其是当数据集很大时，可能会导致计算时间过长。此外，Leave-One-Out Cross Validation还容易受到噪声数据的影响，因为每次测试只使用了一个样本。

因此，在实际使用时，需要根据数据集大小、模型复杂度和计算资源等因素综合考虑，选择合适的交叉验证方法



## 3.10 Bootstrip

Bootstrap是一种统计学方法，用于估计统计量的分布以及评估估计量的精度。在机器学习中，Bootstrap常常用于估计模型的统计性能和评估模型的稳定性。

Bootstrap的基本思想是通过从原始数据集中有放回地抽取一定数量的样本来构造新的数据集，然后基于新的数据集计算统计量。重复这个过程多次，每次抽取的样本数和重复的次数都可以自行设定，最终得到统计量的分布。通过对这个分布进行分析，可以计算置信区间、标准误差和偏差等信息，从而评估模型的性能和稳定性。

在机器学习中，Bootstrap常用于以下几个方面：

1. 估计模型的偏差和方差：Bootstrap可以通过重复抽样构造不同的训练集来估计模型的偏差和方差，从而评估模型的稳定性。
2. 评估模型的泛化能力：Bootstrap可以通过重复抽样构造不同的训练集和测试集来评估模型的泛化能力。
3. 特征选择：Bootstrap可以通过对特征进行有放回抽样来评估特征的重要性和稳定性。

需要注意的是，Bootstrap是一种基于抽样的统计方法，其结果可能会受到随机性的影响，因此需要重复多次实验来验证结果的稳定性和可靠性。

![1677454398149](https://s2.loli.net/2023/02/27/u8CNqUaLZir6ORn.png)



## 3.11 Machine Learning Experiments

- A complete machine learning experiment includes 
- 1) Model training 
  2) Model evaluation 
  3) Model selection: Select a best model among different options (also known as hyper-parameter selection, model selection) 

- Do not train, assess and select hyper-parameters using the same sample set. 

-  You need to split the data with an appropriate strategy, utilising, e.g., hold-out, random subsampling, K-fold CV, LOO, Bootstrap.

  

Example: Hyper-parameter Selection

在机器学习中，超参数（hyper-parameters）是指那些不能由模型自身从数据中学习得到的参数，而是需要手动设置的参数。例如，神经网络中的学习率、正则化系数等就是超参数。这些超参数的设置通常会影响到模型的性能和泛化能力。

超参数的选择是机器学习中一个重要的问题。不同的超参数设置会导致不同的模型性能和泛化能力，因此需要在训练模型之前选择合适的超参数。

超参数选择通常采用交叉验证的方法来进行。具体来说，将原始数据集划分为训练集和验证集两部分，使用训练集进行模型训练，使用验证集来评估模型性能。针对不同的超参数组合，通过交叉验证来评估模型的性能，并选择性能最好的超参数组合作为最终模型的超参数。

常用的超参数选择方法包括网格搜索（Grid Search）和随机搜索（Random Search）。网格搜索是指在预定义的超参数范围内，对所有超参数组合进行尝试，然后选择性能最好的超参数组合。随机搜索是指在预定义的超参数范围内，随机采样超参数组合进行尝试，然后选择性能最好的超参数组合。随机搜索相比于网格搜索具有更高的效率，但是也可能会漏掉性能更好的超参数组合。

需要注意的是，超参数的选择可能会受到数据集大小、特征数量、模型复杂度等因素的影响，因此需要在实际应用中综合考虑这些因素，选择合适的超参数选择方法和策略。

![1677454779721](https://s2.loli.net/2023/02/27/RypDXln6VTaqSmu.png)

![1677454888624](https://s2.loli.net/2023/02/27/kTsjiOm3exr9Q7y.png)

![1677454908592](https://s2.loli.net/2023/02/27/GlCEMfOqTJabN5X.png)

![1677454931143](https://s2.loli.net/2023/02/27/IgFCU8L2VpaMnbs.png)

![1677454962260](https://s2.loli.net/2023/02/27/z5i8BeRPOyqnrI1.png)

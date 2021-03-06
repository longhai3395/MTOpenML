# 深度学习-21:概率论基础

> [深度学习原理与实践(开源图书)-总目录](https://blog.csdn.net/shareviews/article/details/83040730)

本章讨论概率论，在机器学习或人工智能领域中，智能系统往往需要处理不确定性或随机数据。我们需要借助概率论，从不确定性关系中寻找确定性规律，为我们在不确定性存在的情况下进行推理提供了工具集。在人工智能领域，概率论提供了系统方法能够指导AI系统如何推理，也能从理论上辅助我们分析AI系统的行为。

在任何几乎都存在或多或少的不确定性因素，不确定性因素的来源于多个方面:

- 系统内在的不确定性，比如飞机引擎模拟系统，自动驾驶系统或天气预报系统等。
- 不完全观测。当确定性系统不完全观测时，系统也会呈现出某些不确定性。
- 不完全建模。当系统忽略一些次要的观测信息时，系统也会呈现出某些不确定性。

**概率分布**用来描述随机变量或一组随机变量在每一个可能取到的状态的可能性大小。随机变量的概率分布可用离散型函数或连续型函数表示。

## 1 条件概率

在多数情况下，我们关心的是某个事件在其他事件发生的情况下出现的概率，这种概率被称为条件概率。我们将给定 x=X 时，y=Y 发生的条件概率记为P(y=Y | x=X)。这个条件概率可以通过下面的公式计算:
$$P(y=Y | x=X) = P(y=Y, x=X)/P(x=X)$$

## 2 条件概率的链式法则

任何多维随机变量的联合概率分布，都可以分解成只有一个变量的条件概率相乘的形式。这个规则称为概率的链式法则或乘法法则。

$$P(a,b,c) = P(a|b,c)*P(b,C)$$
$$P(b,c)   = P(b|c)*P(c)$$
$$P(a,b,c) = P(a|b,c)*P(b*c)*P(c)$$

## 3 期望、方差

### 3.1 期望

函数f(x)对于某分布P(x)的期望，对于离散型随机变量，计算方法如下:
$$E[f(x)] = \sum\limits_{n=1}^NP(x)f(x)$$

函数f(x)对于某分布P(x)的期望，对于连续型随机变量，计算方法如下:
$$E[f(x)] = \int P(x)f(x)dx$$

线性函数的期望服从线性性质，线性函数的期望等价于期望的线性函数。
$$E(ax+by+c)= aE(x) + bE(y) + c$$

### 3.2 方差

方差权衡的是随机变量x在给定的概率分布中差异。当方差很小时，f(x)的值比较接近函数的期望值。方差的平方根称为**标准差**

$$Var(fx) = E[(f(x)-E[f(x)])^2]$$  

## 4 常见概率分布

以下常见概率分布在人工智能领域使用较多。

### 4.1 Bernoulli分布

Bernoulli分布又叫二值分布。公式表达为:

$$P(x=1)= \Phi$$

$$P(x=0) = 1 - \Phi$$

### 4.2 高斯分布

实数上常用的分布就是正态分布，又称为高斯分布(Gaussian Distribution):

$$N(x,\mu, \delta) = \sqrt{ \frac{1}{2\pi\delta^2} } exp(-\frac{1}{2\delta^2}(x-\mu)^2)$$

### 4.3 指数分布

在深度学习中，经常遇到一个x=0处取得边界点的分布，被称为指数分布。

$$p(x, \lambda)=\lambda exp(-\lambda)$$

## 5 贝叶斯公式

贝叶斯公式可以从条件概率公式直接导出，这里给出结论。该公式由Thomas Bayes牧师最早提出。

$$P(x|y) = \frac{P(x) P(y|x)}{P(y)}$$

## 系列文章

- [深度学习原理与实践(开源图书)-总目录](https://blog.csdn.net/shareviews/article/details/83040730)
- [机器学习原理与实践(开源图书)-总目录](https://blog.csdn.net/shareviews/article/details/83030331)
- [Github: 机器学习&深度学习理论与实践(开源图书)](https://github.com/media-tm/MTOpenML)

## 参考文献

- [1] Ian Goodfellow, Yoshua Bengio. [Deep Learning](http://www.deeplearningbook.org/). MIT Press. 2016.
- [2] 焦李成等. 深度学习、优化与识别. 清华大学出版社. 2017.
- [3] 佩德罗·多明戈斯. 终极算法-机器学习和人工智能如何重塑世界. 中信出版社. 2018.
- [4] 雷.库兹韦尔. 人工智能的未来-揭示人类思维的奥秘.  浙江人民出版社. 2016.

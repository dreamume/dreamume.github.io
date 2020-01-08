
# Table of Contents

1.  [Algorithm](#orgedea58d)
2.  [Review](#org2061e39)
3.  [Tips](#orgc8a3646)
4.  [Share](#orga378145)
    1.  [一个选举投票问题的例子](#orga763a6d)
    2.  [简介](#org504db4d)
    3.  [标准形和松散形](#orgc8d015b)
        1.  [转换线性规划为标准形](#org38e7994)


<a id="orgedea58d"></a>

# Algorithm


<a id="org2061e39"></a>

# Review


<a id="orgc8a3646"></a>

# Tips

-   如果书上算法讲解内容比较长，不确定看懂了所有细节，可能写博客并写出算法实现是比较好的确定看明白的一种方法


<a id="orga378145"></a>

# Share

Linear programming

算法导论29章中提到的算法

线性规划是通过指定一些包含变量的等式或不等式作为限制条件，获取目标函数最大值、最小值的问题。


<a id="orga763a6d"></a>

## 一个选举投票问题的例子

假设你是一个政客想赢得选举。你的选区有三种类型区域&#x2013;城市、城乡结合部、农村。对应有100000，200000，50000注册选民。

你希望每个类型区域有至少一半的投票给你。你的主要主张是建造更多的路、控制枪支、投资农业、增收汽油税改善公共交通。

通过调研发现每花费1000美金广告支持某主张的投票变化表（投票人数单位：千）：

![img](../img/effect_of_policies_on_voters.png)

如何通过最小的花费达到每个类型区域至少一半投票给你的效果？

我们引入4个变量：

-   x<sub>1</sub> 为广告建造公路花费的金额（单位：千美金）
-   x<sub>2</sub> 为广告枪支控制花费的金额（单位：千美金）
-   x<sub>3</sub> 为广告投资农业花费的金额（单位：千美金）
-   x<sub>4</sub> 为广告汽油税花费的金额（单位：千美金）

可以得出以下公式：

为赢得至少50000城市居民投票：

-2x<sub>1</sub> + 8x<sub>2</sub> + 0x<sub>3</sub> + 10x<sub>4</sub> >= 50

赢得至少100000城乡结合部居民投票和25000农村居民投票：

5x<sub>1</sub> + 2x<sub>2</sub> + 0x<sub>3</sub> + 0x<sub>4</sub> >= 100

3x<sub>1</sub> - 5x<sub>2</sub> + 10x<sub>3</sub> - 2x<sub>4</sub> >= 25

以及最小的花费表达式：

x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + x<sub>4</sub>

同时：

x<sub>1</sub> >= 0, x<sub>2</sub> >= 0, x<sub>3</sub> >= 0, x<sub>4</sub> >= 0

根据以上不等式，我们构造一个线性规划问题，整理如下：

最小化    x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + x<sub>4</sub>

约束

-2x<sub>1</sub> + 8x<sub>2</sub> + 0x<sub>3</sub> + 10x<sub>4</sub> >= 50

5x<sub>1</sub> + 2x<sub>2</sub> + 0x<sub>3</sub> + 0x<sub>4</sub> >= 100

3x<sub>1</sub> - 5x<sub>2</sub> + 10x<sub>3</sub> - 2x<sub>4</sub> >= 25

x<sub>1</sub>, x<sub>2</sub>, x<sub>3</sub>, x<sub>4</sub> >= 0


<a id="org504db4d"></a>

## 简介

我们看一个例子：

最小化    x<sub>1</sub> + x<sub>2</sub>

约束

4x<sub>1</sub> - x<sub>2</sub> <= 8

2x<sub>1</sub> + x<sub>2</sub> <= 10

5x<sub>1</sub> - 2x<sub>2</sub> >= -2

x1, x2 >= 0

满足所有约束的x<sub>1</sub>、x<sub>2我们称之为该线性规划问题的可行解</sub>，如下图：

![img](../img/feasible_solution_of_linear_programming.png)

我们称图中阴影部分为有解区域，目标函数在某一点的值为目标值。使目标值最大的点为最优解。

可以看到线性规划的最优解在可解区域的顶点上。由于有解区域是凸的，最优解必须出现在顶点上。相似的，可以推广到N维空间，如果我们有n个变量，每条约束定义了n维空间里的一个半空间，由于任具有凸性，最优解依然在一个顶点上。


<a id="orgc8d015b"></a>

## 标准形和松散形

线性规划中

标准形：

给定n个实数c<sub>1</sub>, c<sub>2</sub>, &#x2026;, c<sub>n</sub>，m个实数b<sub>1</sub>, b<sub>2</sub>, &#x2026;, b<sub>m</sub>，和mn个实数a<sub>ij</sub>，i = 1,2,&#x2026;,m，j = 1,2,&#x2026;,n

![img](../img/standard_form_of_linear_programming.png)


<a id="org38e7994"></a>

### 转换线性规划为标准形

考虑如下4种情况：

1.  目标函数为求最小值而不是最大值
2.  变量不是非负的
3.  约束为等式
4.  不等式约束为大于等于

我们通过例子来说明：

![img](../img/convert_standard_form_example.png)

改变目标函数为最大值，求得最大值，取负即为原最小值。

![img](../img/fit_objective_function_to_maximize_for_standard_form.png)

如果x<sub>j缺少非负约束</sub>，我们将用x'<sub>j</sub> - x''<sub>j替代x</sub><sub>j</sub>，并添加约束x'<sub>j</sub>>=0和x''<sub>j</sub>>=0。


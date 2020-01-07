
# Table of Contents

1.  [Algorithm](#org0988480)
2.  [Review](#orgcdcbf53)
3.  [Tips](#orgb643a63)
4.  [Share](#org6f04917)
    1.  [一个政治问题的例子](#orgc5ea8b2)
    2.  [简介](#org6e57764)


<a id="org0988480"></a>

# Algorithm


<a id="orgcdcbf53"></a>

# Review


<a id="orgb643a63"></a>

# Tips

-   如果书上算法讲解内容比较长，不确定看懂了所有细节，可能写博客并写出算法实现是比较好的确定看明白的一种方法


<a id="org6f04917"></a>

# Share

Linear programming

算法导论29章中提到的算法

线性规划是通过指定一些包含变量的等式或不等式作为限制条件，获取目标函数最大值、最小值的问题。


<a id="orgc5ea8b2"></a>

## 一个政治问题的例子

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


<a id="org6e57764"></a>

## 简介

我们看一个例子：

最小化    x<sub>1</sub> + x<sub>2</sub>


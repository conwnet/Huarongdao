# 华容道

[在线 Demo](https://conwnet.github.io/huarongdao/)

## 简介

[华容道](https://baike.baidu.com/item/华容道) 是一个中国的经典游戏。

## 本项目

看到 gnome 桌面自带了这个经典的小游戏，一时兴起，利用周六周日不上班的时间做了这个小游戏，UI 使用 Vue 开发。

## 操作

操作很简单，首先选择关卡，然后鼠标拖动滑块移动即可。

顺便写了个小算法求解，查看 [算法](#算法)

## 自定义布局

每个小棋子的移动都会改变布局，为了简单方便的表示布局，我直接采用一个字符串表示整个棋盘的布局，有以下几种棋子。

0. 空位，此处没有棋子
1. 占位，是其他棋子的一部分
2. 1x1 的棋子
3. 2x1 的棋子
4. 1x2 的棋子
5. 2x2 的棋子

如经典横刀立马布局：

~~~
┌─┬───┬─┐
│ │   │ │
├─┼───┼─┤
│ ├─┬─┤ │
├─┼─┴─┼─┤
└─┘   └─┘   

3 5 1 3
1 1 1 1
3 4 1 3
1 2 2 1
2 0 0 2
~~~



所以用字符串表示就是 35131111341312212002

## 算法

传入一个字符串，代表当前布局，对该布局进行广度优先遍历。
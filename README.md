# -Minimum_coin_proccess
# 一，问题与思想

## 1问题描述

有n种不同面值的硬币，各硬币面值存于数组Coins[1:n]，现用这些面值的钱来找钱。对于给定的n，硬币面值数组及钱数m，设计一个算法，计算找钱m的最少硬币数，要求用动态规划法。

输入：总钱数Money，面值种类n，实际面值列表Coins[i] 

输出：最少硬币数，以及具体的硬币面值。

## 2基本思路

如果要求money=n的情况，就只要知道money=money-coins[j]的时候情况即可，由此类推，只需要从0（初始态）开始，填满一下表格即可得知最终情况。

目的：求k和k的path

通过划分子问题的思路得到最终结果

| Money   | 1元开始直到money为止 | 0    | 1    | 2    | 3    | 4    |      | 5    | ……   | n-2  | n-1  | n    |
| ------- | -------------------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| coinNum | 动态规划数组         | 0    |      |      |      |      |      |      | …….  |      |      | k    |
| path    | 硬币编号记录         | 0    |      |      |      |      |      |      |      |      |      |      |

子问题：k-1到底需要几个硬币？

初始问题：0元的时候需要0个硬币

## 3为什么创作

因为

1现行网络上少有

（1）路径保存的程序

（2）循环体是以money作为第一重循环，最小硬币数量为第二重循环的思路

2我经历了

（1）长达一周的探索和学习

（2）向大佬请教

所以特此记录。

# 二，16之前的情况（未去重）

1  
999  
[]  
2  
999  
[]  
3  
1  
[3]  
4  
1  
[4]  
5  
1  
[5]  
6  
2  
[3,3]  
7  
2  
[3,4],[4,3]  
8  
2  
[5,3],[4,4],[3,5]  
9  
2  
[4,5],[5,4]  
10  
2  
[5,5]  
11  
3  
[5,3,3],[4,4,3],[3,5,3],[3,4,4],[4,3,4],[3,3,5]  
12    
3  
[4,5,3],[5,4,3],[5,3,4],[4,4,4],[3,5,4],[3,4,5],[4,3,5]  
13  
3  
[5,5,3],[4,5,4],[5,4,4],[5,3,5],[4,4,5],[3,5,5]  
14  
3  
[5,5,4],[4,5,5],[5,4,5]  
15  
3  
[5,5,5]  
16  
4  
[5,5,3,3],[4,5,4,3],[5,4,4,3],[5,3,5,3],[4,4,5,3],[3,5,5,3],[4,5,3,4],[5,4,3,4],[5,3,4,4],[4,4,4,4],[3,5,4,4],[3,4,5,4],[4,3,5,4],[5,3,3,5],[4,4,3,5],[3,5,3,5],[3,4,4,5],[4,3,4,5],[3,3,5,5]  

# 三，文件说明

1程序内包含注释

2动态规划（输入记录版）.py：最终成果

3动态规划（固定记录版）.py：3步骤成果

4动态规划（输入版）.py：2步骤成果

5动态规划（固定数据版）.py：1步骤成果

6成功的最小钱币.py：来自大佬的思路

7最小钱币的过程问题.py：曾经卡过的点

# 四，动态规划（输入记录版）.py运行结果

有解输入  
![屏幕截图 2021-10-31 212728](https://user-images.githubusercontent.com/58925720/139601963-e34df21e-3558-4c2d-86db-256a2e816ec6.png)

无解输入  
![屏幕截图 2021-11-01 053111](https://user-images.githubusercontent.com/58925720/139601970-603b0d67-6e23-485e-aa86-822090eafbdc.png)


最后，特别感谢帮助过我的大佬和老师，我不说是谁，但我相信您一定能够收到我真诚的感谢。  


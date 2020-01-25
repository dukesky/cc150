# 项目简介

算法面试圣经(俗称cc150)《Cracking the Coding Interview: 150 Programming Interview Questions and Solutions》。LeetCode上很多的题目都是来自这本书的。

这本书覆盖了后端开发知识体系的方方面面。([第六版](https://www.ituring.com.cn/book/1876))。官方给出的是Java版，这整理了第六版的Python实现。由于是个人的业余实现，可能存在错误。

本项目使用jupyter编写，导出markdown格式。这样既可以像阅读ppt一样浏览，也可以随时动手验证自己的想法。

- [使用指南](#使用指南)
- [备注](#备注)
- [第六版题目列表](#第六版题目列表)
- [计划表](#计划表)

## 使用指南

```bash
# 安装jupyter
pip3 install jupyter

# 进入项目下的jupter目录,启动jupyter服务器.访问地址http://localhost:8888/tree
jupyter notebook
```

## 备注

- 链表节点的定义：
```python
# Definition for singly-linked list.
class ListNode:
    
    def __init__(self, x):
        self.val = x
        self.next = None
```
- 相关的公共放在了`jupyter/common`目录，引入方式如下：
```python
import os
import sys
sys.path.insert(0, os.path.abspath('./common'))
```

## 第六版题目列表

| 序号           | 题目           | 描述           |
| ------------- |----------------|----------------|
|        | | <h4>数组与字符串<h4> |
| 1.1    | [**判定字符是否唯一**](https://github.com/panxl6/cc150/blob/master/markdown/1.1%20判断字符串是否有重复的字符.md) | 实现一个算法,确定一个字符串的所有字符是否全都不同。假使不允许使用额外的数据结构,又该如何处理? |
| 1.2    | **判定是否互为字符重排** | 给定两个字符串,请编写程序,确定其中一个字符串的字符重新排列后,能否变成另一个字符串。 |
| 1.3    | **URL 化** | 编写一种方法,将字符串中的空格全部替换为 %20 。假定该字符串尾部有足够的空间存放新增字符,并且知道字符串的“真实”长度。(注:用 Java 实现的话,请使用字符数组实现,以便直接在数组上操作。) <br>*示例*:<br>*输入:* "Mr John Smith", 13 <br>*输出:* "Mr%20John%20Smith" |
| 1.4    | **回文排列**  | 给定一个字符串,编写一个函数判定其是否为某个回文串的排列之一。回文串是指正反两个方向都一样的单词或短语。排列是指字母的重新排列。回文串不一定是字典当中的单词。<br>*示例:*<br>*输入:* Tact Coa<br>*输出:* True (排列有 "taco cat" 、 "atco cta" ,等等) |
| 1.5    | **一次编辑**  | 字符串有三种编辑操作:插入一个字符、删除一个字符或者替换一个字符。给定两个字符串,编写一个函数判定它们是否只需要一次(或者零次)编辑。<br>*示例:* <br> pale, ple -> true <br>pales, pale -> true <br>pale, bale -> true <br> pale, bake -> false |
| 1.6    | **字符串压缩**  | 利用字符重复出现的次数,编写一种方法,实现基本的字符串压缩功能。比如,字符串 aabcccccaaa 会变为 a2b1c5a3 。若“压缩”后的字符串没有变短,则返回原先的字符串。你可以假设字符串中只包含大小写英文字母(a 至 z) |
| 1.7    | **旋转矩阵**  | 给定一幅由 N × N 矩阵表示的图像,其中每个像素的大小为 4 字节,编写一种方法,将图像旋转 90 度。不占用额外内存空间能否做到? |
| 1.8    | **零矩阵**  | 编写一种算法,若 M × N 矩阵中某个元素为 0,则将其所在的行与列清零。 |
| 1.9    | **字符串轮转**  | 假定有一种 isSubstring 方法,可检查一个单词是否为其他字符串的子串。给定两个字符串 s1 和 s2 ,请编写代码检查 s2 是否为 s1 旋转而成,要求只能调用一次isSubstring (比如, waterbottle 是 erbottlewat 旋转后的字符串)。 |
|        | | <h4>链表<h4> |
| 2.1    | **移除重复节**  | 编写代码，移除未排序链表中的重复节点。<br> *进阶：*如果不得使用临时缓冲区，该怎么解决？ |
| 2.2    | **返回倒数第k个节点**  | 实现一种算法，找出单向链表中倒数第k 个节点。 |
| 2.3    | **删除中间节点**  | 实现一种算法，删除单向链表中间的某个节点（除了第一个和最后一个节点，不一定是中间节点），假定你只能访问该节点。<br> *示例：* <br> *输入：*  单向链表a->b->c->d->e->f 中的节点c <br> *结果：* 不返回任何数据，但该链表变为a->b->d->e->f |
| 2.4    | **分割链表**  | 编写程序以x 为基准分割链表，使得所有小于x 的节点排在大于或等于x 的节点之前。如果链表中包含x，x 只需出现在小于x 的元素之前（如下所示）。分割元素x只需处于“右半部分”即可，其不需要被置于左右两部分之间。<br> 示例：<br>输入：3 -> 5 -> 8-> 5 -> 10 -> 2 -> 1 [分节点为5] <br>输出：3 -> 1 -> 2 -> 10 -> 5-> 5 -> 8 |
| 2.5    | **链表求和**  | 给定两个用链表表示的整数，每个节点包含一个数位。这些数位是反向存放的，也就是个位排在链表首部。编写函数对这两个整数求和，并用链表形式返回结果。 <br>示例：<br> 输入：(7-> 1 -> 6) + (5 -> 9 -> 2)，即617 + 295 <br>输出：2 -> 1 -> 9，即912 <br> 进阶：假设这些数位是正向存放的，请再做一遍。 <br><br>示例：<br>输入：(6 -> 1 -> 7) + (2 -> 9 -> 5)，即617 + 295 <br> 输出：9 -> 1 -> 2，即912|
| 2.6    | **回文链表**  | 编写一个函数，检查链表是否为回文。 |
| 2.7    | **链表相交**  | 给定两个（单向）链表，判定它们是否相交并返回交点。请注意相交的定义基于节点的引用，而不是基于节点的值。换句话说，如果一个链表的第k 个节点与另一个链表的第j 个节点是同一节点（引用完全相同），则这两个链表相交。 |
| 2.8    | **环路检测**  | 给定一个有环链表，实现一个算法返回环路的开头节点。有环链表的定义：在链表中某个节点的next 元素指向在它前面出现过的节点，则表明该链表存在环路。 <br>示例：<br>输入：A -> B -> C -> D -> E -> C（C 节点出现了两次）<br>输出：C|
|  | | <h4>栈和队列<h4> |
| 3.1    | **三合一**  | 描述如何只用一个数组来实现三个栈。 |
| 3.2    | **栈的最小**  | 请设计一个栈，除了pop 与push 函数，还支持min 函数，其可返回栈元素中的最小值。执行push、pop 和min 操作的时间复杂度必须为O(1)。 |
| 3.3    | **堆盘子**  | 设想有一堆盘子，堆太高可能会倒下来。因此，在现实生活中，盘子堆到一定高度时，我们就会另外堆一堆盘子。请实现数据结构SetOfStacks，模拟这种行为。SetOfStacks 应该由多个栈组成，并且在前一个栈填满时新建一个栈。此外，SetOfStacks.push()和SetOfStacks.pop()应该与普通栈的操作方法相同（也就是说，pop()返回的值，应该跟只有一个栈时的情况一样）。<br>进阶：实现一个popAt(int index)方法，根据指定的子栈，执行pop 操作。 |
| 3.4    | **化栈为队**  | 实现一个MyQueue 类，该类用两个栈来实现一个队列。 |
| 3.5    | **栈排序**  | 编写程序，对栈进行排序使最小元素位于栈顶。最多只能使用一个其他的临时栈存放数据，但不得将元素复制到别的数据结构（如数组）中。该栈支持如下操作：push、pop、peek 和isEmpty。 |
| 3.6    | **动物收容所**  | 有家动物收容所只收容狗与猫，且严格遵守“先进先出”的原则。在收养该收容所的动物时，收养人只能收养所有动物中“最老”（由其进入收容所的时间长短而定）的动物，或者可以挑选猫或狗（同时必须收养此类动物中“最老”的）。换言之，收养人不能自由挑选想收养的对象。请创建适用于这个系统的数据结构，实现各种操作方法，比如enqueue、dequeueAny、dequeueDog 和dequeueCat。允许使用Java 内置的LinkedList 数据结构。 |
|  | | <h4>树与图<h4> |
| 4.1    | **节点间通路**  | 给定有向图，设计一个算法，找出两个节点之间是否存在一条路径。 |
| 4.2    | **最小高度树**  | 给定一个有序整数数组，元素各不相同且按升序排列，编写一个算法，创建一棵高度最小的二叉搜索树。 |
| 4.3    | **特定深度节点链表**  | 给定一棵二叉树，设计一个算法，创建含有某一深度上所有节点的链表（比如，若一棵树的深度为D，则会创建出D 个链表） |
| 4.4    | **检查平衡性**  | 实现一个函数，检查二叉树是否平衡。在这个问题中，平衡树的定义如下：任意一个节点，其两棵子树的高度差不超过1。 |
| 4.5    | **合法二叉搜索树**  | 实现一个函数，检查一棵二叉树是否为二叉搜索树。 |
| 4.6    | **后继者**  | 设计一个算法，找出二叉搜索树中指定节点的“下一个”节点（也即中序后继）。可以假定每个节点都含有指向父节点的连接。 |
| 4.7    | **编译顺序**  | 给你一系列项目（projects）和一系列依赖关系（依赖关系dependencies为一个链表，其中每个元素为两个项目的编组，且第二个项目依赖于第一个项目）。所有项目的依赖项必须在该项目被编译前编译。请找出可以使得所有项目顺利编译的顺序。如果没有合法的编译顺序，返回错误。 <br>示例：<br>输入：<br>projects: a, b, c, d, e, f<br>dependencies: (a, d), (f, b), (b, d), (f, a), (d, c)<br>输出：f, e, a, b, d, c |
| 4.8    | **首个共同祖先**  | 设计并实现一个算法，找出二叉树中某两个节点的第一个共同祖先。不得将其他的节点存储在另外的数据结构中。注意：这不一定是二叉搜索树。 |
| 4.9    | **二叉搜索树序列**  | 从左向右遍历一个数组，通过不断将其中的元素插入树中可以逐步地生成一棵二叉搜索树。给定一个由不同节点组成的二叉树，输出所有可能生成此树的数组。 |
| 4.10    | **检查子树**  | 你有两棵非常大的二叉树：T1，有几百万个节点；T2，有几百个节点。设计一个算法，判断T2 是否为T1 的子树。<br>如果T1 有这么一个节点n，其子树与T2 一模一样，则T2 为T1 的子树，也就是说，从节点n 处把树砍断，得到的树与T2 完全相同。 |
| 4.11    | **随机节点**  | 你现在要从头开始实现一个二叉树类，该类除了插入（insert）、查找（find）和删除（delete）方法外，需要实现getRandomNode()方法用于返回树中的任意节点。该方法应该以相同的概率选择任意的节点。设计并实现getRandomNode 方法并解释如何实现其他方法。 |
| 4.12    | **求和路径**  | 给定一棵二叉树，其中每个节点都含有一个整数数值（该值或正或负）。设计一个算法，打印节点数值总和等于某个给定值的所有路径。注意，路径不一定非得从二叉树的根节点或叶节点开始或结束，但是其方向必须向下（只能从父节点指向子节点方向）。 |
|  | | <h4>位操作<h4> |
| 5.1    | **插入**  | 给定两个32 位的整数N 与M，以及表示比特位置的i 与j。编写一种方法，将M插入N，使得M从N 的第j 位开始，到第i 位结束。假定从j 位到i 位足以容纳M，也即若M = 10 011，那么j 和i 之间至少可容纳5 个位。例如，不可能出现j = 3 和i = 2 的情况，因为第3 位和第2 位之间放不下M。<br>示例：<br>输入：N = 10000000000, M = 10011, i = 2, j = 6<br>输出：N = 10001001100 |
| 5.2    | **二进制数转字符串**  | 给定一个介于0 和1 之间的实数（如0.72），类型为double，打印它的二进制表达式。如果该数字无法精确地用32 位以内的二进制表示，则打印“ERROR”。 |
| 5.3    | **翻转数位**  | 给定一个整数，你可以将一个数位从0 变为1。请编写一个程序，找出你能够获得的最长的一串1 的长度。<br>示例：<br>输入：1775（或者：11011101111）<br>输出：8 |
| 5.4    | **下一个数**  | 给定一个正整数，找出与其二进制表达式中1 的个数相同且大小最接近的那两个数（一个略大，一个略小）。 |
| 5.5    | **调试**  | 解释代码((n & (n-1)) == 0)的具体含义。 |
| 5.6    | **整数转换**  | 编写一个函数，确定需要改变几个位才能将整数A 转成整数B。<br>示例：<br>输入：29（或者: 11101），15（或者: 01111）<br>输出：2 |
| 5.7    | **配对交换**  | 编写程序，交换某个整数的奇数位和偶数位，尽量使用较少的指令（也就是说，位0 与位1 交换，位2 与位3 交换，以此类推）。 |
| 5.8    | **绘制直线**  | 有个单色屏幕存储在一个一维字节数组中，使得8 个连续像素可以存放在一个字节里。屏幕宽度为w，且w 可被8 整除（即一个字节不会分布在两行上），屏幕高度可由数组长度及屏幕宽度推算得出。请实现一个函数，绘制从点(x1, y)到点(x2, y)的水线。该方法的签名应形似于drawLine(byte[] screen, int width, int x1, int x2, int y)。 |
|  | | <h4>数学与逻辑题<h4> |
| 6.1    | **较重的药丸**  | 有20 瓶药丸，其中19 瓶装有1.0 克的药丸，余下1 瓶装有1.1 克的药丸。<br>给你一台称重精准的天平，怎么找出比较重的那瓶药丸？天平只能用一次。 |
| 6.2    | **篮球问题**  | 有个篮球框，下面两种玩法可任选一种。<br>玩法1：一次出手机会，投篮命中得分。<br>玩法2：三次出手机会，必须投中两次。<br>如果p 是某次投篮命中的概率，则p 的值为多少时才会选择玩法1 或玩法2？ |
| 6.3    | **多米诺骨牌**  | 有个8 × 8 棋盘，其中对角的角落上，两个方格被切掉了。给定31 块多米诺骨牌，一块骨牌恰好可以覆盖两个方格。用这31 块骨牌能否盖住整个棋盘？请证明你的答案（提供范例或证明为什么不能）。 |
| 6.4    | **三角形上的蚂蚁**  | 三角形的三个顶点上各有一只蚂蚁。如果蚂蚁开始沿着三角形的边爬行，两只或三只蚂蚁撞在一起的概率有多大？假定每只蚂蚁会随机选一个方向，每个方向被选到的概率相等，而且三只蚂蚁的爬行速度相同。<br>类似问题：在n 个顶点的多边形上有n 只蚂蚁，求出这些蚂蚁发生碰撞的概率。 |
| 6.5    | **水壶问题**  | 有两个水壶，容量分别为3 夸脱①和5 夸脱，若水的供应不限量（但没有量杯），怎么用这两个水壶得到刚好的水？注意，这两个水壶呈不规则状，无法精准地装满“半壶”水。 |
| 6.6    | **蓝眸岛**  | 有个岛上住着一群人，有一天来了个游客，定了一条奇怪的规矩：所有蓝眼睛的人都必须尽快离开这个岛。每晚8 点会有一个航班离岛。每个人都看得见别人眼睛的颜色，但不知道自己的（别人也不可以告知）。此外，他们不知道岛上到底有多少人有蓝眼睛，只知道至少有一个人的眼睛是蓝色的。所有蓝眼睛的人要花几天才能离开这个岛？ |
| 6.7    | **大灾难**  | 在大灾难后的新世界，世界女王非常关心出生率。 因此，她规定所有家庭都必须有一个女孩，否则将面临巨额罚款。如果所有的家庭都遵守这个政策——所有家庭在得到一个女孩之前不断生育，生了女孩之后立即停止生育——那么新一代的性别比例是多少（假设每次怀孕后生男生女的概率是相等的）？通过逻辑推理解决这个问题，然后使用计算机进行模拟。 |
| 6.8    | **扔鸡蛋问题**  | 有栋建筑物高100 层，若从第N 层或更高的楼层扔下来，鸡蛋就会破碎；若从第N 层以下的楼层扔下来则不会破碎。给你两个鸡蛋，请找出N，并要求最差情况下扔鸡蛋的次数为最少。 |
| 6.9    | **100个储物柜**  | 走廊上有100 个关上的储物柜。有个人先是将100 个柜子全都打开。接着，每数两个柜子关上一个。然后，在第三轮时，再每隔两个就切换第三个柜子的开关状态（也就是将关上的柜子打开，将打开的关上）。照此规律反复操作100 次，在第i 轮，这个人会每数i 个就切换第i 个柜子的状态。当第100 轮经过走廊时，只切换第100 个柜子的开关状态，此时有几个柜子是开着的？ |
| 6.10    | **有毒的苏打水**  | 你有1000 瓶苏打水，其中有一瓶有毒。 你有10 条可用于检测毒物的试纸。一滴毒药会使试纸永久变黄。你可以一次性地将任意数量的液滴置于试纸上，你也可以多次重复使用试纸（只要结果是阴性的即可）。 但是，每天只能进行一次测试，用时7 天才可得到测试结果。你如何用尽量少的时间找出哪瓶苏打水有毒？<br>进阶：编写程序模拟你的方法。 |
|  | | <h4>面向对象设计<h4> |
| 7.1    | **扑克牌**  | 请设计用于通用扑克牌的数据结构，并说明你会如何创建该数据结构的子类，实现“二十一点”游戏。 |
| 7.2    | **呼叫中心**  | 设想你有个呼叫中心，员工分3 级：接线员、主管和经理。客户来电会先分配给有空的接线员。若接线员处理不了，就必须将来电往上转给主管。若主管没空或是无法处理，则将来电往上转给经理。请设计这个问题的类和数据结构，并实现一种dispatchCall()方法，将客户来电分配给第一个有空的员工。 |
| 7.3    | **音乐点唱机**  | 运用面向对象原则，设计一款音乐点唱机。 |
| 7.4    | **停车场**  | 运用面向对象原则，设计一个停车场。 |
| 7.5    | **在线图书阅读器**  | 请设计在线图书阅读器系统的数据结构。 |
| 7.6    | **拼图**  | 实现一个N × N 的拼图程序。设计相关数据结构并提供一种拼图算法。假设你有一种fitsWith 方法，传入两块拼图，若两块拼图能拼在一起，则返回true。 |
| 7.7    | **聊天服务器**  | 请描述该如何设计一个聊天服务器。要求给出各种后台组件、类和方法的细节，并说明其中最难解决的问题会是什么。 |
| 7.8    | **黑白棋**  | “奥赛罗棋”（黑白棋）的玩法如下：每一枚棋子的一面为白，一面为黑。游戏双方各执黑、白棋子对决，当一枚棋子的左右或上下同时被对方棋子夹住，这枚棋子就算是被吃掉了，随即翻面为对方棋子的颜色。轮到你落子时，必须至少吃掉对方一枚棋子。任意一方无子可落时，游戏即告结束。最后，棋盘上棋子较多的一方获胜。请运用面向对象设计方法，实现“奥赛罗棋”。 |
| 7.9    | **环状数组**  | 实现一个CircularArray 类。该类需要支持类似于数组的数据结构且该数组可以被高效地轮转。如果可以的话，该类应该使用泛型类型（也被称作模板），同时可以通过标准循环语句for (Obj o : circularArray)进行迭代。 |
| 7.10    | **扫雷**  | 设计和实现一个基于文字的扫雷游戏。扫雷游戏是经典的单人电脑游戏，其中在N × N 的网格上隐藏了B 个矿产资源（或炸弹）。网格中的单元格后面或者是空白的，或者存在一个数字。数字反映了周围8 个单元格中的炸弹数量。游戏开始之后，用户点开一个单元格。如果是一个炸弹，玩家即失败。如果是一个数字，数字就会显示出来。如果它是空白单元格，则该单元格和所有相邻的空白单元格（直到遇到数字单元格，数字单元格也会显示出来）会显示出来。当所有非炸弹单元格显示时，玩家即获胜。 玩家也可以将某些地方标记为潜在的炸弹。这不会影响游戏进行，只是会防止用户意外点击那些认为有炸弹的单元格。（读者提示：如果你不熟悉此游戏，请先在网上玩几轮。） <br>![扫雷](https://raw.githubusercontent.com/panxl6/blog/master/Images/7-10.png)|
| 7.11    | **文件系统**  | 设计一种内存文件系统（in-memory file system）的数据结构和算法，并说明其具体做法。如若可行，请用代码举例说明。 |
| 7.12    | **散列表**  | 设计并实现一个散列表，使用链接（即链表）处理碰撞冲突。 |
|  | | <h4>递归与动态规划<h4> |
| 8.1    | **三步问题**  | 有个小孩正在上楼梯,楼梯有 n 阶台阶,小孩一次可以上 1 阶、2 阶或 3 阶。实现一种方法,计算小孩有多少种上楼梯的方式。 |
| 8.２    | **迷路的机器人**  | 设想有个机器人坐在一个网格的左上角,网格 r 行 c 列。机器人只能向下或向右移动,但不能走到一些被禁止的网格。设计一种算法,寻找机器人从左上角移动到右下角的路径。 |
| 8.3   | **魔术索引**  | 在数组 A[0...n-1] 中,有所谓的魔术索引,满足条件 A[i] = i 。给定一个有序整数数组,元素值各不相同,编写一种方法找出魔术索引,若有的话,在数组 A 中找出一个魔术索引。<br> 进阶:如果数组元素有重复值,又该如何处理呢? |
| 8.4    | **幂集**  | 编写一种方法,返回某集合的所有子集。 |
| 8.5    | **递归乘法**  | 写一个递归函数,不使用 * 运算符, 实现两个正整数的相乘。可以使用加号、减号、位移,但要吝啬一些。 |
| 8.6    | **汉诺塔问题**  | 在经典汉诺塔问题中,有 3 根柱子及 N 个不同大小的穿孔圆盘,盘子可以滑入任意一根柱子。一开始,所有盘子自上而下按升序依次套在第一根柱子上(即每一个盘子只能放在更大的盘子上面)。移动圆盘时受到以下限制:<br>(1) 每次只能移动一个盘子;<br>(2) 盘子只能从柱子顶端滑出移到下一根柱子;<br>(3) 盘子只能叠在比它的盘子上。<br>请编写程序,用栈将所有盘子从第一根柱子移到最后一根柱子。 |
| 8.7    | **无重复字符串的排列组合**  | 编写一种方法,计算某字符串的所有排列组合,字符串每个字符均不相同。 |
| 8.8    | **重复字符串的排列组合**  | 编写一种方法,计算字符串所有的排列组合,字符串中可能有字符相同,但结果不能有重复组合。 |
| 8.9    | **括号**  | 设计一种算法,打印 n 对括号的所有合法的(例如,开闭一一对应)组合。<br>示例:<br>输入: 3<br>输出: ((())), (()()), (())(), ()(()), ()()() |
| 8.10    | **颜色填充**  | 编写函数,实现许多图片编辑软件都支持的“颜色填充”功能。给定一个屏幕(以二维数组表示,元素为颜色值)、一个点和一个新的颜色值,将新颜色值填入这个点的周围区域,直到原来的颜色值全都改变。 |
| 8.11    | **硬币**  | 给定数量不限的硬币,币值为 25 分、10 分、5 分和 1 分,编写代码计算 n 分有几种表示法。 |
| 8.12    | **八皇后**  | 设计一种算法,打印八皇后在 8 × 8 棋盘上的各种摆法,其中每个皇后都不同行、不同列,也不在对角线上。这里的“对角线”指的是所有的对角线,不只是平分整个棋盘的那两条对角线。 |
| 8.13    | **堆箱子**  | 给你一堆 n 个箱子,箱子宽 w i 、高 h i 、深 d i 。箱子不能翻转,将箱子堆起来时,下面箱子的宽度、高度和深度必须大于上面的箱子。实现一种方法,搭出最高的一堆箱子。箱堆的高度为每个箱子高度的总和。 |
| 8.14    | **布尔运算**  | 给定一个布尔表达式和一个期望的布尔结果 result ,布尔表达式由 0 、 1、 & 、\| 和 ^ 符号组成。实现一个函数,算出有几种可使该表达式得出 result 值的括号方法。该表达式要用全括号(如 (0)^(1) )表示,而不能包含半括号(如 (((0))^(1)) )。<br>示例:<br>countEval("1^0\|0\|1", false) -> 2<br>countEval("0&0&0&1^1\|0", true) -> 10 |
|  | | <h4>系统设计与可扩展性<h4> |
| 9.1    | **股票数据**  | 假设你正在搭建某种服务,有多达 1000 个客户端软件会调用该服务,取得每天盘后股票价格信息(开盘价、收盘价、最高价与最低价)。假设你手里已有这些数据,存储格式可自行定义。你会如何设计这套面向客户端的服务从而向客户端软件提供信息?你将负责该服务的研发、部署、持续监控和维护。描述你想到的各种实现方案,以及为何推荐采用你的方案。该服务的实现技术可任选,此外,可以选用任何机制向客户端分发信息。|
| 9.2    | **社交网络**  | 你会如何设计诸如 Facebook 或 LinkedIn 的超大型社交网站的数据结构?请设计一种算法,展示两人之间最短的社交路径(比如,我 → 鲍勃 → 苏珊 → 杰森 → 你)。 |
| 9.3    | **网络爬虫**  | 如果要设计一个网络爬虫,该怎样避免陷入死循环呢? |
| 9.4    | **重复网址**  | 给定 100 亿个网址(URL),如何检测出重复的文件?这里所谓的“重复”是指两个 URL 完全相同。 |
| 9.5    | **缓存**  | 想象有个 Web 服务器,实现简化版搜索引擎。这套系统有 100 台机器来响应搜索查询,可能会对另外的机器集群调用 processSearch(string query) 以得到真正的结果。响应查询请求的机器是随机挑选的,因此两个同样的请求不一定由同一台机器响应。processSearch 方法过于昂贵,请设计一种缓存机制,缓存最近几次查询的结果。当数据发生变化时,请解释说明该如何更新缓存。 |
| 9.6    | **销售排名**  | 一家大型电子商务公司希望列出所有类别及每个类别最畅销的产品,例如,在所有类别中,一款产品可能是第 1056 个畅销产品,但在“ 运动器械 ”类排名第 13,在“ 安全 ”类排名第 24。简述你要如何设计这个系统。 |
| 9.7    | **个人理财管理**  | 要你设计款个人理财管理系统(类似 Mint.com),简述你的设计思路。系统的功能可以连接到你的银行账户,分析你的消费习惯,并给出建议。 |
| 9.8    | **文本分享**  | 设计一个类似于 Pastebin 1 的系统,用户输入一段文本,就可以得到一个随机生成的 URL 来访问该系统。 |
|  | | <h4>排序与查找<h4> |
| 10.1    | **合并排序的数组**  | 给定两个排序后的数组 A 和 B ,其中 A 的末端有足够的缓冲空间容纳B 。编写一个方法,将 B 合并入 A 并排序。 |
| 10.2    | **变位词组**  | 编写一种方法,对字符串数组进行排序,将所有变位词排在相邻的位置。 |
| 10.3    | **搜索旋转数组**  | 给定一个排序后的数组,包含 n 个整数,但这个数组已被旋转过很多次了,次数不详。请编写代码找出数组中的某个元素,假设数组元素原先是按升序排列的。<br>示例:<br>输入:在数组 {15, 16, 19, 20, 25, 1, 3, 4, 5, 7, 10, 14} 中找出 5<br>输出: 8 (元素 5 在该数组中的索引) |
| 10.4    | **排序集合的查找**  | 给定一个类似数组的长度可变的数据结构 Listy ,它有个 elementAt(i)方法,可以在 O(1)的时间内返回下标为 i 的值,但越界会返回1。因此,该数据结构只支持正整数。给定一个排好序的正整数 Listy ,找到值为 x 的下标。如果 x 多次出现,任选一个返回。 |
| 10.5    | **稀疏数组搜索**  | 有个排好序的字符串数组,其中散布着一些空字符串,编写一种方法,找出给定字符串的位置。<br>示例:<br>输入:在字符串数组 {"at", "", "", "", "ball", "", "", "car", "","","dad", "", ""} 中查找“ ball ”<br>输出: 4 |
| 10.6    | **大文件排序**  | 设想你有个 20 GB 的文件,每行有一个字符串,请阐述一下将如何对这个文件进行排序。 |
| 10.7    | **失踪的整数**  | 给定一个输入文件,包含 40 亿个非负整数,请设计一种算法,生成一个不包含在该文件中的整数,假定你有 1 GB 内存来完成这项任务。<br>进阶:如果只有 10 MB 内存可用,该怎么办?假设所有值均不同,且有不超过 10 亿个非负整数。 |
| 10.8    | **寻找重复数**  | 给定一个数组,包含 1 到 N 的整数,N 最大为 32 000,数组可能含有重复的值,且 N 的取值不定。若只有 4 KB 内存可用,该如何打印数组中所有重复的元素。 |
| 10.9    | **排序矩阵查找**  | 给定 M × N 矩阵,每一行、每一列都按升序排列,请编写代码找出某元素。 |
| 10.10    | **数字流的秩**  | 假设你正在读取一串整数。每隔一段时间,你希望能找出数字 x 的秩(小于或等于 x 的值的个数)。请实现数据结构和算法来支持这些操作,也就是说,实现track(int x) 方法,每读入一个数字都会调用该方法;实现 getRankOfNumber(int x)方法,返回小于或等于 x(x 除外)的值的个数。<br>示例:<br>数据流为(按出现的先后顺序): 5, 1, 4, 4, 5, 9, 7, 13, 3<br>getRankOfNumber(1) = 0<br>getRankOfNumber(3) = 1<br>getRankOfNumber(4) = 3 |
| 10.11    | **峰与谷**  | 在一个整数数组中,“峰”是大于或等于相邻整数的元素,相应地,“谷”是小于或等于相邻整数的元素。例如,在数组 {5, 8, 6, 2, 3, 4, 6} 中, {8, 6} 是峰,{5, 2} 是谷。现在给定一个整数数组,将该数组按峰与谷的交替顺序排序。<br>示例:<br>输入: [5, 3, 1, 2, 3]<br>输出: [5, 1, 3, 2, 3] |
|  | | <h4>测试<h4> |
| 11.1    | **找错**  | 找出以下代码中的错误(可能不止一处)。<br>unsigned int i;<br>for (i = 100; i >= 0; --i)<br>&nbsp;&nbsp; printf("%d\n", i); |
| 11.2    | **随机崩溃**  | 有个应用程序一运行就崩溃,现在你拿到了源码。在调试器中运行10次之后,你发现该应用每次崩溃的位置都不一样。这个应用只有一个线程,并且只调用 C 标准库函数。究竟是什么样的编程错误导致程序崩溃?该如何逐一测试每种错误? |
| 11.3    | **测试国际象棋**  | 有个国际象棋游戏程序使用了 boolean canMoveTo(int x, int y)方法,这个方法是 Piece 类的一部分,可以判断某个棋子能否移动到位置(x, y)。请阐述你会如何测试该方法。 |
| 11.4    | **无工具测试**  | 不借助任何测试工具,该如何对网页进行负载测试? |
| 11.5    | **测试一支笔**  | 如何测试一支笔? |
| 11.6    | **测试 ATM**  | 在一个分布式银行系统中,该如何测试一台自动柜员机(ATM)? |
|  | | <h4>C和C++<h4> |
| 12.1    | **最后K行**  | 用C++写个方法,打印输入文件的最后K行。 |
| 12.2    | **反转字符串**  | 用 C 或 C++实现一个名为`reverse(char* str)`的函数,它可以反转一个null 结尾的字符串。 |
| 12.3    | **散列表与 STL map**  | 比较并对比散列表和 STL map。散列表是怎么实现的?如果输入的数据量不大,可以选用哪些数据结构替代散列表? |
| 12.4    | **虚函数原理**  | C++虚函数的工作原理是什么? |
| 12.5    | **浅复制与深复制**  | 浅复制和深复制之间有何区别?请阐述两者的不同用法。 |
| 12.6    | **volatile 关键字**  | C++语言的关键字`volatile`有何作用? |
| 12.7    | **虚基类**  | 基类的析构函数为何要声明为virtual? |
| 12.8    | **复制节点**  | 编写一种方法,传入参数为指向 Node 结构的指针,返回传入数据结构的完整副本,其中, Node 数据结构含有两个指向其他 Node 的指针。 |
| 12.9    | **智能指针**  | 编写一个智能指针类。智能指针是一种数据类型,一般用模板实现,模拟指针行为的同时还提供自动垃圾回收机制。它会自动记录SmartPointer<T*> 对象的引用计数,一旦 T 类型对象的引用计数为 0,就会释放该对象。 |
| 12.10   | **分配内存**  | 编写支持对齐分配的 malloc 和 free 函数,分配内存时, malloc 函数返回的地址必须能被 2 的 n 次方整除。<br>示例: align_malloc(1000,128)返回的内存地址可被128整除,并指向一块1000字节大小的内存。 aligned_free() 会释放 align_malloc 分配的内存。 |
| 12.11   | **二维数组分配**  | 用 C 编写一个 my2DAlloc 函数,可分配二维数组。将 malloc 函数的调用次数降到最少,并确保可通过 arr[i][j] 访问该内存。 |
|  | | <h4>Java<h4> |
| 13.1    | **私有构造函数**  | 从继承的角度看,把构造函数声明为私有会有何作用? |
| 13.2    | **异常处理中的返回**  | 在 Java 中,若在 try-catch-finally 的 try 语句块中插入 return语句, finally 语句块是否还会执行? |
| 13.3    | **final 们**  | final 、 finally 和 finalize 之间有何差异? |
| 13.4    | **泛型与模板**  | C++模板和 Java 泛型之间有何不同? |
| 13.5    | **TreeMap 、 HashMap 、 LinkedHashMap**  | 解释一下TreeMap 、 HashMap 、 LinkedHashMap三者的不同之处。举例说明各自最适合的情况。|
| 13.6    | **反射**  | 解释下 Java 中对象反射是什么,有什么用处。 |
| 13.7    | **lambda 表达式**  | 有一个名为 Country 的类,它有两种方法,一种是 getContinent() 返回该国家所在大洲,另一种是 getPopulation() 返回本国人口。实现一种名为 getPopulation (List<Country> counties,String continent) 的方法,返回值类型为 int 。它能根据指定的大洲名和国家列表计算出该大洲的人口总数。 |
| 13.8    | **lambda 随机数**  | 使用 lambda 表达式写一种名为 getRandomSubset(List<Integer> list)的方法,返回值类型为 List<Integer> ,返回一个任意大小的随机子集,所有子集(包括空子集)选中的概率都一样。 |
|  | | <h4>数据库<h4> |
| 14.1    | **多套公寓**  | 编写SQL查询,列出租住不止一套公寓的承租人。 |
| 14.2    | **“ open ”的申请数量**  | 编写 SQL 查询,列出所有建筑物,并取得状态为“ Open ”的申请数量( Requests 表中 Status 为“ Open ”的条目)。 |
| 14.3    | **关闭所有请求**  | 11 号建筑物正在进行大翻修。编写 SQL 查询,关闭这栋建筑物里所有公寓的入住申请。 |
| 14.4    | **连接**  | 连接有哪些不同类型?请说明这些类型之间的差异,以及为何在某些情形下,某种连接会比较好。 |
| 14.5    | **反规范化**  | 什么是反规范化?请说明其优缺点。 |
| 14.6    | **画一个实体关系图**  | 有个数据库,里面有公司( companies )、人( people )和在职专业人员( professional ),请绘制实体关系图。 |
| 14.7    | **设计分级数据库**  | 给定一个存储学生成绩的简单数据库。设计这个数据库的大体框架,并编写 SQL 查询,返回以平均分排序的优等生名单(排名前 10%)。<br> ![表设计](https://raw.githubusercontent.com/panxl6/blog/master/Images/table.png) |
|  | | <h4>线程与锁<h4> |
| 15.1    | **进程与线程**  | 进程和线程有何区别? |
| 15.2    | **上下文切换**  | 如何测量上下文切换时间? |
| 15.3    | **哲学家用餐**  | 在著名的哲学家用餐问题中,一群哲学家围坐在圆桌周围,每两位哲学家之间有一根筷子。每位哲学家需要两根筷子才能用餐,并且一定会先拿起左手边的筷子,然后才会去拿右手边的筷子。如果所有哲学家在同一时间拿起左手边的筷子,就有可能造成死锁。请使用线程和锁,编写代码模拟哲学家用餐问题,避免出现死锁。|
| 15.4    | **无死锁的类**  | 设计一个类,只有在不可能发生死锁的情况下,才会提供锁。 |
| 15.5    | **顺序调用**  | 给定以下代码:<br>public class Foo {<br>&nbsp;&nbsp;public Foo() { ... }<br>&nbsp;&nbsp;public void first() { ... }<br>&nbsp;&nbsp;public void second() { ... }<br>&nbsp;&nbsp;public void third() { ... }<br>}<br>同一个 Foo 实例会被传入 3 个不同的线程。 threadA 会调用 first , threadB 会调用second , threadC 会调用 third 。设计一种机制,确保 first 会在 second 之前调用,second 会在 third 之前调用。 |
| 15.6    | **同步方法**  | 给定一个类,内含同步方法 A 和普通方法 B 。在同一个程序实例中,有两个线程,能否同时执行 A ?两者能否同时执行 A 和 B ? |
| 15.7    | **FizzBuzz**  | 在经典面试题 FizzBuzz 中,要求你从 1 到 n 打印数字。并且,当数字能被3整除时,打印 Fizz,能被 5 整除时,打印 Buzz。倘若同时能被 3 和 5 整除,就打印FizzBuzz。但与以往不同的是,这里要求你用 4 个线程,实现一个多线程版本的 FizzBuzz,其中,一个用来检测是否被 3 整除和打印 Fizz,另一个用来检测是否被 5 整除和打印 Buzz。第三个线程检测能否被 3 和 5 整除和打印 FizzBuzz。第四个线程负责遍历数字。 |
|  | | <h4>中等难题<h4> |
| 16.1    | **交换数字**  | 编写一个函数,不用临时变量,直接交换两个数。 |
| 16.2    | **单词频率**  | 设计一个方法,找出任意指定单词在一本书中的出现频率。如果我们多次使用此方法,应该怎么办? |
| 16.3    | **交点**  | 给定两条线段(表示为起点和终点),如果它们有交点,请计算其交点。 |
| 16.4    | **井字游戏**  | 设计一个算法,判断玩家是否赢了井字游戏。 |
| 16.5    | **阶乘尾数**  | 设计一个算法,算出 n 阶乘有多少个尾随零。 |
| 16.6    | **最小差**  | 给定两个整数数组,计算具有最小差(非负)的一对数值(每个数组中取一个值),并返回该对数值的差。<br>示例:<br>&nbsp;&nbsp;输入: {1, 3, 15, 11, 2}, {23, 127, 235, 19, 8}<br>&nbsp;&nbsp;输出: 3 ,即数值对 (11, 8) |
| 16.7    | **最大数值**  | 编写一个方法,找出两个数字中最大的那一个。不得使用 if-else 或其他比较运算符。 |
| 16.8    | **整数的英语表示**  | 给定一个整数,打印该整数的英文描述(例如“One Thousand, Two Hundred Thirty Four”)。 |
| 16.9    | **运算**  | 请实现整数数字的乘法、减法和除法运算,运算结果均为整数数字,程序中只允许使用加法运算符。 |
| 16.10    | **生存人数**  | 给定一个列有出生年份和死亡年份的名单,实现一个方法以计算生存人数最多的年份。你可以假设所有人都出生于 1900 年至 2000 年(含 1900 和 2000)之间。如果一个人在某一年的任意时期都处于生存状态,那么他们应该被纳入那一年的统计中。例如,生于 1908 年、死于 1909 年的人应当被列入 1908 年和 1909 年的计数。 |
| 16.11    | **跳水板**  | 你正在使用一堆木板建造跳水板。 有两种类型的木板,其中一种长度较短(长度记为 shorter ),一种长度较长(长度记为 longer )。你必须正好使用 K 块木板。编写一个方法,生成跳水板所有可能的长度。 |
|  | | <h4>高难度题<h4> |
| 17.1    | **不用加号的加法**  | 设计一个函数把两个数字相加。不得使用 + 或者其他算术运算符。 |
| 17.2    | **洗牌**  | 设计一个用来洗牌的函数。要求做到完美洗牌,也就是说,这副牌 52! 种排列组合出现的概率相同。假设给定一个完美的随机数发生器。 |
| 17.3    | **随机集合**  | 编写一个方法,从大小为 n 的数组中随机选出 m 个整数。要求每个元素被选中的概率相同。 |
| 17.4    | **消失的数字**  | 数组 A 包含从 0 到 n 的所有整数,但其中缺了一个。在这个问题中,只用一次操作无法取得数组 A 里某个整数的完整内容。此外,数组 A 的元素皆以二进制表示,唯一可用的访问操作是“从 A[i] 中取出第 j 位数据”,该操作的时间复杂度为常量。请编写代码找出那个缺失的整数。你有办法在 O(n)时间内完成吗? |
| 17.5    | **字母与数字**  | 给定一个放有字符和数字的数组,找到最长的子数组,且包含的字符和数字的个数相同。 |
| 17.6    | **2 出现的次数**  | 编写一个方法,计算从 0 到 n(含 n)中数字 2 出现的次数。<br>示例:<br>输入: 25<br>输出: 9(2, 12, 20, 21, 22, 23, 24, 25) (注意 22 应该算作两次) |
| 17.7    | **婴儿名字**  | 每年,政府都会公布一万个最常见的婴儿名字和它们出现的频率,也就是同名婴儿的数量。有些名字有多种拼法,例如,John 和 Jon 本质上是相同的名字,但被当成了两个名字公布出来。给定两个列表,一个是名字及对应的频率,另一个是本质相同的名字对。设计一个算法打印出每个真实名字的实际频率。注意,如果 John 和 Jon 是相同的,并且 Jon 和 Johnny 相同,则 John 与 Johnny 也相同,即它们有传递性和对称性。<br>在结果列表中,任选一个名字做为真实名字就可以。<br>示例:<br>输入: Names: John(15)、Jon(12)、Chris(13)、Kris(4)、Christopher(19) Synonyms: (Jon, John)、(John, Johnny)、(Chris, Kris)、(Chris, Christopher)<br>输出: John(27)、Kris(36) |
| 17.8    | **马戏团人塔**  | 有个马戏团正在设计叠罗汉的表演节目,一个人要站在另一人的肩膀上。出于实际和美观的考虑,在上面的人要比下面的人矮一点且轻一点。已知马戏团每个人的身高和体重,请编写代码计算叠罗汉最多能叠几个人。<br>示例:<br>输入: (ht, wt) : (65, 100) (70, 150) (56, 90) (75, 190) (60, 95) (68, 110)<br>输出:从上往下数,叠罗汉最多能叠 6 层: (56, 90) (60,95) (65,100) (68,110)
(70,150) (75,190) |
| 17.9    | **第k个数**  | 有些数的素因子只有 3,5,7,请设计一个算法找出第k个数。注意,不是必须有这些素因子,而是必须不包含其他的素因子。例如,前几个数按顺序应该是 1,3,5,7,9,15,21。 |
| 17.10   | **主要元素**  | 有些数的素因子只有 3,5,7,请设计一个算法找出第 k 个数。注意,不是必须有这些素因子,而是必须不包含其他的素因子。例如,前几个数按顺序应该是 1,3,5,7,9,15,21。 |
| 17.11   | **单词距离**  | 有个内含单词的超大文本文件,给定任意两个单词,找出在这个文件中这两个单词的最短距离(相隔单词数)。如果寻找过程在这个文件中会重复多次,而每次寻找的单词不同,你能对此优化吗? |
| 17.12   | **BiNode**  | 有个名为 BiNode 的简单数据结构,包含指向另外两个节点的指针。<br>public class BiNode {<br>public BiNode node1, node2;<br>public int data;<br>}<br>BiNode 可用来表示二叉树(其中 node1 为左子节点, node2 为右子节点)或双向链表(其中 node1 为前趋节点, node2 为后继节点)。实现一个方法,把用 BiNode 实现的二叉搜索树转换为双向链表,要求值的顺序保持不变,转换操作应是原址的,也就是在原始的二叉搜索树上直接修改。 |
| 17.13   | **恢复空格**  | 哦,不!你不小心把一个长篇文章中的空格、标点都删掉了,并且大写也弄成了小写。像句子“ I reset the computer. It still didn’t boot! ”已经变成了“ iresetthecomputeritstilldidntboot ”。在处理标点符号和大小写之前,你得先把它断成词语。当然了,你有一本厚厚的词典,用一个 string 的集合表示。不过,有些词没在词典里。假设文章用 string 表示,设计一个算法,把文章断开,要求未识别的字符最少。<br>示例:<br>输入: jesslookedjustliketimherbrother<br>输出: jess looked just like tim her brother (7 个未识别的字符) |
| 17.14   | **最小k个数**  | 设计一个算法,找出数组中最小的 k 个数。 |
| 17.15   | **最长单词**  | 给定一组单词,编写一个程序,找出其中的最长单词,且该单词由这组单词中的其他单词组合而成。<br>示例:<br>输入: cat, banana, dog, nana, walk, walker, dogwalker<br>输出: dogwalker |
| 17.16   | **按摩师**  | 一个有名的按摩师会收到源源不断的预约请求,每个预约都可以选择接或不接。在每次预约服务之间要有 15 分钟的休息时间,因此她不能接受时间相邻的预约。给定一个预约请求序列(都是 15 分钟的倍数,没有重叠,也无法移动),替按摩师找到最优的预约集合(总预约时间最长),返回总的分钟数。<br>示例:<br>输入: {30, 15, 60, 75, 45, 15, 15, 45}<br>输出: 180 minutes ({30, 60, 45, 45}) |
| 17.17   | **多次搜索**  | 给定一个字符串 b 和一个包含较短字符串的数组 T ,设计一个方法,根据T中的每一个较短字符串,对 b 进行搜索。 |
| 17.18   | **最短超串**  | 假设你有两个数组,一个长一个短,短的元素均不相同。找到长数组中包含短数组所有的元素的最短子数组,其出现顺序无关紧要。<br>示例:<br>输入: {1, 5, 9} | {7, 5, 9, 0, 2, 1, 3, 5, 7, 9, 1, 1, 5, 8, 8, 9, 7}<br>输出: [7, 10] (the underlined portion above) |
| 17.19   | **消失的两个数字**  | 给定一个数组,包含从 1 到 N 所有的整数,但其中缺了一个。你能在O(N)时间内只用 O(1)的空间找到它吗?如果是缺了两个数字呢? |
| 17.20   | **连续中值**  | 随机产生数字并传递给一个方法。你能否完成这个方法,在每次产生新值时,寻找当前所有值的中间值并保存。 |
| 17.21   | **直方图的水量**  | 给定一个直方图(也称柱状图),假设有人从上面源源不断地倒水,最后直方图能存多少水量?直方图的宽度为 1。<br>示例(黑色部分是直方图,灰色部分是水):<br>输入: {0, 0, 4, 0, 0, 6, 0, 0, 3, 0, 5, 0, 1, 0, 0, 0}<br>输出: 26 <br> ![hist](https://raw.githubusercontent.com/panxl6/blog/master/Images/hist.png)|
| 17.22   | **单词转换**  | 给定字典中的两个词,长度相等。写一个方法,把一个词转换成另一个词,但是一次只能改变一个字符。每一步得到的新词都必须能在字典中找到。<br>示例:<br>输入: DAMP, LIKE<br>输出: DAMP -> LAMP ->LIMP ->LIME ->LIKE |
| 17.23   | **最大黑方阵**  | 给定一个方阵,其中每个单元(像素)非黑即白。设计一个算法,找出条边皆为黑色像素的最大子方阵。 |
| 17.24   | **最大子矩阵**  | 给定一个正整数和负整数组成的 N × N 矩阵,编写代码找出元素总和最大的子矩阵。 |
| 17.25   | **单词矩阵**  | 给定一份几百万个单词的清单,设计一个算法,创建由字母组成的最大矩形,其中每一行组成一个单词(自左向右),每一列也组成一个单词(自上而下)。不要求这些单词在清单里连续出现,但要求所有行等长,所有列等高。 |
| 17.26   | **稀疏相似度**  | 两个(具有不同单词的)文档的交集(intersection)中元素的个数除以并集(union)中元素的个数,就是这两个文档的相似度。例如, {1, 5, 3} 和 {1, 7, 2, 3}的相似度是 0.4,其中,交集的元素有 2 个,并集的元素有 5 个。给定一系列的长篇文档,每个文档元素各不相同,并与一个 ID 相关联。它们的相似度非常“稀疏”,也就是说任选 2 个文档,相似度都很接近 0。请设计一个算法返回每对文档的 ID 及其相似度。<br>只需输出相似度大于 0 的组合。请忽略空文档。为简单起见,可以假定每个文档由一个含有不同整数的数组表示。<br>示例:<br>输入:<br>13: {14, 15, 100, 9, 3}<br>16: {32, 1, 9, 3, 5}<br>19: {15, 29, 2, 6, 8, 7}<br>24: {7, 10}<br><br>输出:<br>ID1, ID2 : SIMILARITY<br>13, 19 : 0.1<br>13, 16 : 0.25<br>19, 24 : 0.14285714285714285 |

## 计划表

- [x] 统一代码格式
- [ ] 美化文字格式，提升阅读体验
- [ ] 增加LeetCode的相关专题
- [ ] 完成后续的章节
- [ ] 增加示意图或动画
- [x] 增加第六版的内容
- [ ] 对比官方的Java版答案，校验一次
- [ ] 抽象测试用例运行框架，实现一个Online judge

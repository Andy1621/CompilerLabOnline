# CompilerLabOnline

## Demo

http://139.199.104.107:4000/

## 第一次实验

#### 实验目的

加深对词法分析原理的理解，掌握编写简单词法分析程序的一般步骤。

#### 实验步骤

1. 分析所给的PL0文法，确定关键字，分界符，运算符，常量。
2. 设计词法分析器代码。
3. 完善出错处理、输入输出。
4. 用flask框架建站展示。

#### 特性

* 可分出关键词、分节符、运算符、常量（整数输出二进制）
* 对非法字符报错
* 支持小数
* 有图形化界面

#### 实验感想

加深了对词法分析原理的理解

1. 词法分析时往往需要在两种单词之间选择，它的规则可概括为选更长和更优先的那个。理解了这一点就容易设计代码了。
2. 词法分析的本质是利用多个正则表达式去匹配文本。

## 第二次试验

#### 实验目的

* 理解算符优先文法（OPG）的概念
* 掌握OPG语义分析的一般方法
* 学会编码实现FIRSTVT, LASTVT, 优先关系矩阵的计算方法
* 学会编码实现OPG Parser的一般写法

#### 实验步骤

1. 根据输入的文法规则得出文法的标识符、词汇表、终结符号、非终结符号
2. 根据书上的伪代码，计算FIRSTVT和LASTVT
3. 利用FIRSTVT和LASTVT，计算优先关系矩阵
4. 编写语义处理程序
5. 设计错误处理
6. 完善输出格式，实现UI

#### 特性

（假定给出的语法是规范的OG文法且程序为连续无空格的字符串）

* 可根据文法计算算符优先矩阵，并以此为基础进行语义分析
* 当文法不属于OPG时，语义分析失败时报错
* 有图形化界面

#### 实验感想

1. 加深了对OPG的理解：
    * OPG是一种Deterministic Context-Free Grammar，它可以被确定的下推自动机识别
2. 加深了对算符优先矩阵构造的理解：
    * FIRSTVT(U)包含的是那些非终结符号，它们可以出现在【U推导出的句型们】的第一个位置或第二个位置（仅当第一个位置是Vn）。同理LASTVT(U)。
    * 有了FIRSTVT和LASTVT数组，就可以方便的计算出优先关系矩阵，因为不需要再去考虑【推导】了。
3. 加深了对OPG Parsing的理解：
    * 最左素短语的选择将所有Vn一视同仁，只有语义处理的时候才会考虑它们的区别。
# 2018.6.27 BMPT 会议文档

[TOC]

## 会议重点问题

_有其他问题再群里提，讨论要不要加进会议内容。_



### 1.确定开发时间

用放暑假的 **第一个月** 做完全部功能。_`Gridsah`个人想法_ 。

剩下时间准备其他的事情。

_`Gridsah`要准备十月份的网络安全比赛和年底的 `Kaggle` 比赛，暑假之后开发组的项目还要上线，年后要准备考研。这个项目明年三月用来报科创，时间非常紧。所以时间花费能压缩就压缩_ 。



### 2.确定开发需求

基础需求是什么。

会议开始由 `Gridsah` 介绍指（甲）导（方）老（爸）师（爸）的基础需求。

然后讨论出暑假要做的功能。

如果早于一个月完工，可以再做哪些需求。



### 3.确定分工定位

`Gridsah` 擅长后端，准备暑假借着这个项目练习前端。定位是前后端均参与，前端干杂活，主后端。

贾 sir：擅长，定位。

周 sir：擅长，定位。



### 4.确定开发工具

`PyCharm` 作为 IDE 项目后端预计采用 `Django` + `Redis` + `Celery` 。

前端待定。开会时讨论。

采用 Python 3.6 + MySQL 5.7 + Django 2.0 。

使用 `GitHub` 进行协作，不会用的自己提前模拟熟悉一下。



### 5.兼容性问题

`vue` 兼容性有缺陷，讨论要不要更改框架以兼容大多数浏览器。



### 本项目的代码规范

以下是本项目的代码规范。有异议开会时讨论。

1. 所有新建文件开头必须添加 `# -*- coding: utf-8 -*-` 。
2. 类、方法及变量的命名禁止使用谭浩强命名法。
3. 变量名：小写，由下划线连接各个单词。如 `color = WHITE` ， `this_is_a_variable = 1 ` 。**注意** ：
   1. 不论是类成员变量还是全局变量，均不使用 `m` 或 `g` 作为前缀。
   2. 私有类成员使用单一下划线前缀标识。
   3. Python 是动态类型语言，变量名不应带有类型信息。如 `iValue` 、`names_list` 、`dict_obj` 等命名都不应出现。 
4. 类命名：总是使用首字母大写单词串。如 `MyClass` 。内部类可以使用额外的前导下划线。 
5. 函数和方法的参数：如果一个函数的参数名称和保留的关键字冲突，通常使用一个后缀下划线 。
6. 全局变量：对于 `from M import *` 导入语句，如果想阻止导入模块内的全局变量可以使用旧有的规范，在全局变量上加一个前导的下划线。 **但是应尽量避免使用全局变量**
7. 常量：常量名所有字母大写，由下划线连接各个单词如 `MAX_OVERFLOW` ， `TOTAL` 。 
8. 异常：必须以 `Error` 作为后缀。 
9. 文件名：全小写，若对阅读有帮助，可以使用下划线 。
10. 前导后缀下划线：
    1. 一个前导下划线：表示非公有。
    2.  一个后缀下划线：避免关键字冲突。 
    3. 两个前导下划线：当命名一个类属性引起名称冲突时使用。 
    4. 两个前导和后缀下划线：有特殊的用途的对象或者属性，例如 `__init__` 或者 `__file__` 。绝对不要造这样的名字。 
    5. **注意：关于下划线的使用存在一些争议，但是本项目以该要求为准** 。
11. 变量名注释标准：如果这个变量无法从名字得知其用途，那么必须添加对这个变量名解释的注释。
12. 方法注释标准：包括摘要，详细解释，参数注释，返回值注释。如下：

```
def fetch_bigtable_rows(big_table, keys, other_silly_variable=None):
    """Fetches rows from a Bigtable.

    Retrieves rows pertaining to the given keys from the Table instance
    represented by big_table.  Silly things may happen if
    other_silly_variable is not None.

    Args:
        big_table: An open Bigtable Table instance.
        keys: A sequence of strings representing the key of each table row
            to fetch.
        other_silly_variable: Another optional variable, that has a much
            longer name than the other args, and which does nothing.

    Returns:
        A dict mapping keys to the corresponding table row data
        fetched. Each row is represented as a tuple of strings. 
        
    """
    pass
```
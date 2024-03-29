+++
title = "Markdown简明教程"
date = "2021-09-12"
description = ""
featured = true
categories = [
    "编程开发"
]
tags = [
  "Markdown"
]
images = [
  "images/markdown.png"
]
toc = true
+++

## 1.标题
Markdown支持6种级别的标题，对应html标签 h1 ~ h6,注意符号“#”和“H”之间有空格
>
    # H1
    ## H2
    ### H3
    #### H4
    ##### H5
    ###### H6

效果：
# H1
## H2
### H3
#### H4
##### H5
###### H6

## 2.段落
段落没有特殊的格式，直接编写文字就可以，段落的换行是**使用两个以上空格加上回车**。  

也可以使用一个或多个空行。

### 2.1.字体
> 
    *斜体文本*
    _斜体文本_
    **粗体文本**
    __粗体文本__
    ***粗斜体文本***
    ___粗斜体文本___

效果如下：  

*斜体文本*  

_斜体文本_  

**粗体文本**  

__粗体文本__  

***粗斜体文本***  

### 2.2.分隔线
你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：
> 
    ***
    * * *
    *****
    - - -
    ----------

效果如下：
***

* * *

*****

- - -

----------

### 2.3.删除线
文字要添加删除线，只需要在文字的两端加上两个波浪线 ~~ 即可，实例如下：
```
~~DELETE WORD~~
```
效果如下：
~~DELETE WORD~~  

### 2.4.脚注
脚注是对文本的补充说明。

Markdown 脚注的格式如下:

> [^要注明的文本]

示例：
脚注示例[^EXAMPLE]  
[^EXAMPLE]:这是一个脚注示例

## 3.列表
Markdown 支持有序列表和无序列表。

### 3.1.无序列表
无序列表使用星号(*)、加号(+)或是减号(-)作为列表标记，这些标记后面要添加一个空格，然后再填写内容：

> 
    * 第一项
    * 第二项
    * 第三项
    
    + 第一项
    + 第二项
    + 第三项
    
    - 第一项
    - 第二项
    - 第三项

显示结果如下：  
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项

### 3.2.有序列表
有序列表使用数字并加上 . 号来表示，如：
> 
    1. 第一项
    2. 第二项
    3. 第三项

显示结果如下： 
1. 第一项
2. 第二项
3. 第三项
1. 
## 4.引用

引用是在段落开头使用 > 符号 ，然后后面紧跟一个空格符号：
```
> 引用内容
```
效果如下：

> 引用内容

## 5.代码

### 5.1行内代码
行内代码使用反引号（`）把代码包起来：
> \`echo "Hello world!"\`

显示效果：`echo "Hello world!"`

### 5.2代码块
代码块使用三个反引号（```）包裹一段代码：并指定一种语言（也可以不指定）：

> 
  ```golang
      fun Add(a,b int) int {
          return a+b
      }
  ```
显示效果：
```golang
    fun Add(a,b int) int {
        return a+b
    }
```

## 6.链接
链接使用方法如下：
> 
    [链接名称](链接地址)  
    或者  
    <链接地址>  

例如：
> 打开[百度]\(https://www.baidu.com/)

打开[百度](https://www.baidu.com/)

## 7.图片
Markdown 图片语法格式如下：

> 
    ![alt 属性文本](图片地址)
    ![alt 属性文本](图片地址 "可选标题")

## 8.表格
表格使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行。
语法格式如下：
> 
    |  表头   | 表头  |
    |  ----  | ----  |
    | 单元格  | 单元格 |
    | 单元格  | 单元格 |

|  表头   | 表头  |  
|  ----  | ----  |  
| 单元格  | 单元格 |  
| 单元格  | 单元格 |  

我们可以设置表格的对齐方式：

* -: 设置内容和标题栏居右对齐。
* :- 设置内容和标题栏居左对齐。
* :-: 设置内容和标题栏居中对齐。

实例如下：
> 
    | 左对齐 | 右对齐 | 居中对齐 |
    | :-----| ----: | :----: |
    | 单元格 | 单元格 | 单元格 |
    | 单元格 | 单元格 | 单元格 |

效果如下：
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
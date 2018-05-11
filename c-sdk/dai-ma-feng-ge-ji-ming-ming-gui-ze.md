代码风格及目录结构
===

## 目录结构

主要由以下几个文件夹组成：
* app： 用户程序文件夹
* demo：例示程序
* include: 头文件夹
* init：初始化代码，不建议改动
* platform：库文件相关

相关API都可以在`include`文件夹中找到，对应的实例都可以在`demo`文件夹中找到。

所有来自底层的事件均可以在`api_event.h`中找到，并且事件参数的含义都在对应事件后面的注释说明。

## 代码风格

统一的代码风格方便阅读，对于任何一份代码来说都十分重要，每个人的代码风格不尽相同，但是多人在开发同一份代码时一定要统一风格，一份简洁干净的代码会让编码更加顺利舒畅~

CSDK使用统一的代码风格，简要概括为以下几个点：

### 函数命名

模块API使用`大写功能模块_大驼峰命名`，比如`AUDIO_MicOpen`，`SSL_Init`；普通函数使用大驼峰命名，比如：`EventDispatch`

> 入口函数特殊，使用`文件夹名字_Main`，比如`imei_Main`

### 变量命名

小驼峰命名，比如：`int ballNumber;`

### 宏定义

大写+下划线，比如：`#define BUFFER_MAX_LENGTH 10`

### 文件编码格式

文件编码统一为`UTF-8`无BOM格式

### tab还是空格？

不使用<kbd>tab</kbd>，编辑器设置<kbd>tab</kbd>为4空格替换

### 单词缩写

* 对于一些业界熟知的单词可以尽量使用缩写，比如`src`、`tmp`等，

* 除了这些之外，为保证代码的可读性，务必使用全称，特别是一些专业术语，尽量让没有接触过这个单词的人通过搜索引擎能够搜到这个单词的含义。

比如： `NetworkLocation`，如果缩写成`NL`、`NetLo`，相信就算是对这个单词非常熟悉的人也得去看代码的上下文才能慢慢才到其中的含义！如果去网上搜索这几个缩写，也不可能得到`NetworkLocation`！

**所以，为了让代码更简洁清晰易读，不一定是要让代码单词缩写为更简单的形式，相反的是全称的单词往往更易读。**

* 另外，有些单词需要进行解释，需要适量进行注释


### 注释

* 注释可以使用`/**/`或者`//`进行注释，失效的代码尽量使用`/**/`注释

* 需要加入到自动生成文档的说明用

```
//////////////
///这里写注释
//////////////
```

或者

```
/**
  *这里写注释
  *
  */
```

* 文件注释或函数等注释可以适当加相关信息，比如文件：

```
/**
  *@file header.h
  *@author nick name
  */
```
或函数
```
/**
  *@brief 这里写简要说明，@brief可以省略,省略则将简要说明写在注释开头
  *@param a 求和参数1
  *@param b 求和参数2
  *@return  返回和
  */
```


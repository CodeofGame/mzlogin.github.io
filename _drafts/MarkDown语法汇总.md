## MarkDown语法大全

### 1、表格语法（表格不支持合并）

| 一级节点 | 二级节点 | 三级节点 |  表单  | 功能说明 |
| :--: | :--: | :--: | :--: | :--: |
|  张三  |  1   | 三年二班 |      |      |
|  王五  |  2   | 三年一班 |      |      |

### 2、分割线

```
***
```

***

### 3、无序列表

在 - 后接一个空格

- 我是
- 你是

### 4、无序列表

  1.后接空格

1. dad

2. mo

3. three

###5.强调

Markdown 使用星号（`*`）和底线（`_`）作为标记强调字词的符号，被 `*` 或 `_` 包围的字词会被转成用 `<em>` 标签包围，用两个 `*` 或 `_`包起来的话，则会被转成 `<strong>`

*小字体*

**粗体**

### 6.链接

```shell
//语法
文本链接<https://github.com/SeayXu>
[文本链接](https://github.com/SeayXu 鼠标停留提示)
```

文本链接<https://github.com/SeayXu>

[文本链接](https://github.com/SeayXu  鼠标停留提示)

我经常去的几个网站[Google][1]、[Leanote][2]以及[自己的博客][3]`
[Leanote 笔记][2]是一个不错的[网站][]。`
`
[1]:http://www.google.com "Google"`
[2]:http://www.leanote.com "Leanote"`
[3]:http://http://blog.leanote.com/freewalk "梵居闹市"`
[网站]:http://http://blog.leanote.com/freewalk`
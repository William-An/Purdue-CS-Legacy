# Markdown Cheatsheet

- [Markdown Cheatsheet](#markdown-cheatsheet)
  - [文本格式](#文本格式)
  - [列表](#列表)
  - [Link 与 图片](#link-与-图片)
  - [代码](#代码)
  - [表格](#表格)

## 文本格式

```Markdown
// 标题
# H1
## H2
### H3
#### H4
##### H5
###### H6

// 文本格式
**Bold**
*Italic*
~~strike through~~
> 引用

// 分割线
---

// 强制换行, 在行尾添加两个空格
这不是一个
换行

这是一个  
换行
```

**Bold**  
*Italic*  
~~strike through~~  
> 引用  

---

这不是一个
换行

这是一个  
换行

## 列表

```Markdown
1.  有序列表, ordered list
    1. item 1
    2. item 2
    3. item 3
2. Heading

- 无序列表, unordered list
    - item 1
    - item 2
    - item 3

1. [ ] 任务list
    1. [x] 这个任务被完成了
    2. [ ] 这个则还没有
```

1. 有序列表, ordered list
    1. item 1
    2. item 2
    3. item 3
2. Heading

- 无序列表, unordered list
  - item 1
  - item 2
  - item 3
  
1. [ ] 任务list
    1. [x] 这个任务被完成了
    2. [ ] 这个则还没有

## Link 与 图片

```Markdown
[Link Name](https URL)
![Image caption](Image http URL)

[Link Name](local path)
![Image caption](local image path)
[文档内链接](#link-与-图片)
```

[Blog Link](http://blog.thexyzlab.studio/)  
URL 图片:
![Blog image](https://blog.thexyzlab.studio/content/images/size/w2000/2021/06/Background.png)

[本地主页Link](/index.md)  
本地图片 (在 GitHub Pages 上无法正常展示):
![本地图片](/assets/WASDE%20CODE%20V3.jpg)  
[文档内链接](#link-与-图片)

## 代码

````Markdown
`行内代码`

// 代码块
```[Progarmming language]
Syntax highligh here
```

    4空格缩进
    这也是个代码块

````

`行内代码`

```Python
# 带有语法高亮的代码块, 适用于 GitHub
print("Hello World!")
```

    4空格缩进
    这也是个代码块

## 表格

```Markdown
| 第一列  | 第二列  | 第三列  |
| ------ | :----: | -----: |
| 左对齐  |  居中   | 右对齐  |
```

| 第一列  | 第二列  | 第三列  |
| ------ | :----: | -----: |
| 左对齐  |  居中   | 右对齐  |

# markdown 笔记

## 标题类

### 代码
```python
#       一级标题
##      二级标题
###     三级标题
####    四级标题
```
---

## 列表类

### 有序列表
1. 概述  
    1. 论文概述  
    2. 英文摘要  
2. 前言  
3. 正文

### 无序列表
- 概述  
    - 论文概述  
    - 英文摘要    
- 前言  
- 正文

---

## 文字、段落类

### 文字效果
`*font*  `*倾斜*  
`**加粗**`**加粗**  
`~~中划线~~`~~中划线~~

### 段落类
#### 换行效果  
例子：此处需要 [\n + 双空格] 换行
> 回车 + 行末连续两个空格    

#### 文字对齐：  
`<p align="center">这是一段右对齐的文字</p>`  
<p align="center">这是一段右对齐的文字</p>  

> 需要借助html 标签 并配合 align 标签完成

#### 文字大小、颜色
`<font size="6" color="orange">改变文字大小和颜色</font>`  
例子：<font color="orange" size="6">改变文字大小和颜色</font>

> 需要借助 font 标签来实现

---

## 引用块、代码块
### 引文
`> 大于号+空格来实现`
> 这是一段引文代码块

### 代码块
```
  连续的``` 代码块形成引用 ``` 
```

```javascript
    function(...args){
        args.forEach((item) => {
            return item*2;
        });
    }
```
---

## 链接

### 外部链接
`语法：[test](url){:target="_blank"}     [百度](http://www.baidu.com)`  
效果：[百度](http://www.baidu.com)

### 内部链接
`语法：[test](url)  [内部文件](file.html)`  
效果：[内部文件](file.html)

### 引用式链接
`语法：[test][引文地址]  [来自底部引文][baidu]`  
效果：[来自底部引文][baidu]

---

## 图片

### 引用图片
`语法：![test](url)  [百度](http://www.baidu.com)`   
效果：![](img/xxx.jpg "win10 桌面")

### 图片+链接
`[![](img_url "alt")](http_url)`  
效果：[![](img/xxx.jpg "win10 桌面")](http://www.badiu.com)

---

---

<font size=5 color=red>注意：以下代码有兼容性问题</font>

## 任务列表

`
    - [x] 完成项
    - [ ] 未完项
`

- [x] 完成项
- [ ] 未完项

## 表格
| 姓名 | 年龄 | 性别 |

<!-- 以下是引文链接 -->
[baidu]:http://www.baidu.com

[markdown 资料]:https://www.cnblogs.com/shawWey/p/8931697.html

<style>
    *{ font-family:微软雅黑; }
</style>





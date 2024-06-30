# _我的markdown学习笔记_

从标题开始讲起，第一个大标题的写法是：#空格+内容
第二个小标题的写法是：             ##空格_内容_
如果你在内容旁边添加了_ _修饰，他就会变为斜体

接下来看看一段正文内容怎么写

## 关于事件绕过的知识补充：
- 总述：适用于没办法愉快地输入<script><img/>标签的场合（多半是标签符号被强制过滤了）
那么这种情况，既不能直接输入脚本，又没办法利用找不到图片文件路径而执行代码的方法，此时需要找到新的触发方式。

这段文字前面加上了-开头，markdown都是要在修饰符后面加上一个空格的
顺带一提，添加一个空行来取消段落修饰符号

## 引用框
- 通过>来修饰
>So the time is come
>For you to learn your treasons
>The reason for bleeding
>
>You took me away
>Turned me into something
>The light wouldn't save

## 注释怎么写
- \[//]: # (至少在dillnger上这样行得通，在这个操作符前面加\转义字符好让他显示出来)
- 通用的方法是html的注释标签 &nbsp;&nbsp;<!-- 渲染之后就看不见了 -->

## 空格怎么输入
- 输入\&nbsp;记得加分号
- 此外，使用以下的标签组（）
<pre>
这是一段预格式化文本。
它会保留所有的空格和制表符。

</pre>
## 点击跳转
- wch连续前高视频[点我查看](https://ys-api.mihoyo.com/event/download_porter/link/ys_cn/official/pc_default)
- \[显示的内容](网址)

## 输入代码
\```python
print("hello")
## 图片插入
- 待完成


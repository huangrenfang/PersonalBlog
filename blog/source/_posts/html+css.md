---
layout: '[layout]'
title: html+css
date: 2018-11-30 20:58:58
tags: html+css
---

## html的语义化：
1.有利于程序员阅读和团队开发
2.有利于搜索引擎优化
行级元素不能设置宽高（不起作用）
spam,a,i,b
块级元素能设置宽高
div,p,ul,li,h1-h6
行块级元素既可以设置宽高又可以行级分布（水平）
## 选择器：
1.id选择器
2.class选择器
3.标签选择器
4.后代选择器 div p
5.子代选择器 div>p
6.伪类选择器 a:hover
7.伪对象选择器 div::after
8.属性选择器 divattr

## css中的position:
默认static
absolute (定位后空间释放，相对于最近已定位的祖先元素)
relative （定位后空间不释放，相对于自己初始位置）
fixed （固定定位 定位后空间释放 相对于浏览器）
sticky（吸顶效果 空间释放）

## display:
inline,block,inline-block,table,tabel-cell,cell

## float 清除浮动：
父元素overflow:hidden(溢出隐藏)
父元素加一个高度
clear：both（清除左浮和右浮，也可以单独设置）
.clearfix::after{
content:'';
dispaly:block;
clear:both
}
## css盒模型:
标准盒模型：width= 内容的长度
怪异盒模型：width=内容的长度+padding+border
标准盒模型<=>怪异盒模型 box-sizing
content-box     border-box

## 外边距合并:
父子：父元素和子元素同时设置外边距时，外边距合并，使用最大的值（父元素设置border可以取消合并和设置overflow:hidden,父元素或子元素设置浮动）
兄弟：同父子（外边距设置一个元素-子元素设置一个溢出隐藏的div）

## BFC:(Block formatting context)块级格式化上下文
是一个独立的渲染区域，只有Block-level box参与
它规定了内部的Block-level Box如何布局，并且与这个区域外部毫不相干
布局规则：
  ● 内部的Box会在垂直方向，一个接一个地放置。
  ● Box垂直方向的距离由margin决定。属于同一个BFC的两个相邻Box的margin会发生重叠
  ● 每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。
  ● BFC的区域不会与float box重叠。
  ● BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。
  ● 计算BFC的高度时，浮动元素也参与计算
哪些元素会生成BFC?
根元素 html
float属性不为none
position为absolute或fixed
display为inline-block,table-cell,table-caption,flex,inline-flex
overflow不为visible 

## 权重值：
!important>内嵌样式>ID>类>标签|伪类|属性选择>伪对象>继承>通配符
!important在对应的样式后添加如：
font-size:16px; !important

## 重绘：
就是在一个元素的外观被改变，但没有改变布局（宽高）的情况下发生，
如改变visibility,outline,背景颜色等等
## 重排：
就是DOM的变化影响到了元素的几何属性（宽和高），
浏览器会重新改变元素的几何属性，如：改变窗口大小，改变字体大小，内容，style属性，浏览器窗口变化等等
reflow(回流)：
当浏览器发现某个部分发生了点变化影响了布局，
需要倒回去重新渲染，内行称这个回退的过程叫reflow
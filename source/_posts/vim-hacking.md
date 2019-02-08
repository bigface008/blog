---
title: Vim Configuraion
date: 2019-01-30 22:09:52
tags:
- vim
- time-killer
categories:
- vim
---
老子不用Vim了！！！~~本文记录了折腾vim过程中遇到的种种问题，以及对于“最适合我的编辑器/Vim应该是什么样的”的见解（反正不会有人看就随便写了）。~~
<!--more-->
> Just for fun.
## 前言

首先，我希望能拥有这样一个“完美”编辑器：

1. 轻量、快速。
2. 高效、自定义性强的快捷键设置。
3. 完整的语言特性支持。
4. 现代的图形界面。
5. 使用者对其了如指掌。

尴尬的是，vim并不怎么符合以上的条件。尤其是在Windows上使用Vim，各种问题一言难尽。

比较项目|VScode|Vim|
---|---|---|
各类语言支持|相当完善。|即使折腾很长时间也有点蹩脚。|
启动速度|极少数情况下有点慢。|肯定还是比较快的。|
可配置性|不太好。|相对来说还过得去（不过配置起来很麻烦）。|
易用性|开箱即用。|必须折腾很长时间后才比较高效，所以易用性很低。|

相比之下，VScode的表现实际上已经满足了很多人对于编辑器甚至IDE的需求了。开箱即用的各种语言特性支持，可以接受的运行速度，适当的内存占用，不断升级的Vim模式插件......总得来说VScode没有太多可以挑剔的地方。

那么我为啥还要折腾Vim这个东西呢？我勉强拼凑出了下面的理由。

1. 极高的键盘操作速度。VScode即使是安装了Vim模式插件，想要完全比上Vim下的编辑体验还是差了一些距离。
2. 内存/硬盘空间洁癖症。这个我真的没有办法......
3. 兴趣使然。

实际上，从理性的角度考虑，可以归结为：

> 我知道我做的事情没有意义，但这不是有没有意义的问题，是我想去做才去做的！

Windows上的Vim配置文件[仓库](https://github.com/bigface008/winvimrc)。
Linux上的Vim配置文件[仓库](https://github.com/bigface008/linux-vimrc)。（我知道把两个分开很傻......但是我觉得合在一起对于我这种菜鸡来说问题更大）。

## 零碎的记录

### LeaderF & fzf.vim & ack/ag.vim

要让Vim成为“完美”的编辑器肯定离不开快速的搜索、跳转、替换功能。然而我试了半天，在Windows下Vim的搜索辅助插件都有点不大对——由于Vim大多数用户都是UNIX的忠实拥趸，Vim各种插件（包括其本身）对于Windows的支持一直都不咋地——ack/ag.vim在Windows下都会卡一下，fzf.vim在调用vimscript的时候就会出现奇怪的报错，于是我只能用LeaderF了——个人认为不过LeaderF本身也是各个插件中最好的，除了要自己配置颜色这一点有些蛋疼。注意下面设置中的配色部分是为了符合[papercolor-theme](https://github.com/NLKNguyen/papercolor-theme)的底栏配色而设计的（实际上就是白字蓝底）。

```vimscript
let g:Lf_StlSeparator = { 'left': '', 'right': '' }        " Change style of separators.
let g:Lf_Ctags = "D:\\program\\ctags\\ctags.exe"           " Set the path of ctags.
let g:Lf_ReverseOrder = 1                                  " Reverse order of searching results.
let g:Lf_WindowHeight = 0.30                               " Set max window height.
noremap <C-S-o> :LeaderfFunction<Enter>                    " Keybinding for search funtions.
let g:Lf_StlPalette = {
        \   'stlName': {
        ......
        \       'guifg': '#eeeeee',                        "
        \       'guibg': '#005f87',
        ......
        \   },
        \   'stlCategory': {
        ......
        \       'guifg': '#eeeeee',
        \       'guibg': '#005f87',
        ......
        \   },
        \   'stlFullPathMode': {
        ......
        \       'guifg': '#eeeeee',
        \       'guibg': '#005f87',
        ......
        \   },
        \   'stlCwd': {
        ......
        \       'guibg': '#005f87',
        ......
        \   },
        \   'stlBlank': {
        ......
        \       'guibg': '#005f87',
        ......
        \   },
        \   'stlLineInfo': {
        ......
        \       'guifg': '#eeeeee',
        \       'guibg': '#005f87',
        ......
        \   },
        \   'stlTotal': {
        ......
        \       'guifg': '#eeeeee',
        \       'guibg': '#005f87',
        ......
        \   }
        \ }
```


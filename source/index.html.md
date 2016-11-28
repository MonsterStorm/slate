---
title: LuaView API Reference

language_tabs:
  - lua

toc_footers:
  - <a href='https://github.com/alibaba/LuaViewSDK'>LuaView In GitHub</a>

includes:
  - design_principles
  - api_luaview
  - api_ui
  - api_nui
  - api_constants
  - extends_luaview
  - examples
  - changes_log

search: true
---

# Introduction

LuaView 是 **聚划算无线技术团队** 的开源项目，其初衷是为了提升移动端应用动态化能力，提供比H5更好的用户体验，同时做到Android、iOS业务代码共用，减少同一业务的人员重复投入。

目前LuaView已经在聚划算大范围使用，先后经历了聚划算 3.8、6.6、9.9大促，已经服务过千万用户。使用LuaView的客户端能够具备H5同样的动态化能力，做到bug随时修，业务随时上，且在硬件交互，动画等功能上提供比H5更好的体验。

LuaView 使用Lua语言进行代码编写，目前支持两个端：Android和iOS。Android
端使用LuaJ引擎,iOS端使用LuaC引擎。

# Design Principles

几乎所有API既可以作为get函数调用，也可以作为set函数调用

* 有参数的时候作为set函数调用，并返回对象本身（可供链式调用）
* 无参数的时候作为get函数调用，并返还调用返回值
* 时间单位是秒，毫秒通过小数来设置
* 所有尺寸单位为点（dot），而非真实像素（px）
* 容器类包含View的容器方法，非容器类没有View的容器方法

```
如：
 view.size(100, 100)  -- 设置view的大小为 w=100, h=100，返回view自身

 view.size()  -- 获取view的大小，返回 {w=100, h=100}
```

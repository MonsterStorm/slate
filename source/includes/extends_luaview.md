# Extends LuaView

## Scenarios

虽然LuaView包含了常用的大部分控件，但是开发者很可能有自己的定制需求，这些定制需求可以大致分为以下几种情况

### 1. 已经有native的UI组件，想让该native组件与lua进行交互。

如：开发者A在使用LuaView之前，已经开发了一个自定义的View，该自定义View能够完成某些功能，想在lua中使用该组件，实现native与lua互操作。

### 2. 有某些功能，需要与lua码进行交互。

如以下场景：

  * 需要在 native 中调用 lua 函数，执行某个功能，或者得到某个结果。
  * 需要在 lua 调用 native 函数，执行 native 中的某个功能，或者得到某个结果。


### 3. 需要使用自己的图片库。

如：开发者A使用自定义的图片库，而非Glide（LuaView默认图片库）。


### 4. 预定义组件无法满足需求，需要自己实现一套组件。

如以下场景：

  * 开发者A不想使用LuaView内置的Button，而是使用自己开发的Button组件。
  * 开发者想跟LuaView一样，在lua代码中使用完整的组件，并包含自己的API，如 VideoView



## 1. 已有 Native UI 组件

开发者A，在自己的项目中，有统一的Native错误UI，在 lua 中写的页面或UI组件中也需要使用该错误UI。为了避免重复开发已有功能，LuaView 支持将现有功能通过简单封装，桥接到 lua 层，赋予该 Native UI 与 lua 互操作的能力。既可以在 lua 中创建出该UI，也可以操作该UI，改变其状态或功能，也可以在在该 Native UI 中调用相应的 lua 代码。




## 2. 需要与 lua 交互


## 3. 使用自己的图片库

## 4. 扩展完整组件

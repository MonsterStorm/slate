# API-UI


## View

<aside class="notice" id="view">
所有UI组件基类，容器。
</aside>


> initParams

```
TableView().initParams({
})
```

> frame

```
view.frame(0, 0, 100, 100)
view.frame()
```

> padding

```
view.padding(5, 5, 5, 5)
```

> backgroundColor

```
view.backgroundColor(0xff0000, 0.5)
```

> align

```
view.align(Align.RIGHT, Align.BOTTOM)
```

> startAnimation

```
anim1 = Animation().alpha(1, 0).duration(1)
anim2 = Animation().scale(1, 0).duration(2).delay(0.2)
view.startAnimation(anim1, anim2)
```

> flexCss

```
view = View()
view.flexCss("margin-left: 10, sizetofit: 1, align-self: center")
```


> flxLayout

```
view = View()
view.flxLayout(true, function()
	print("do something")
end)
```



> effects

```
view.effects(ViewEffect.CLICK) -- 点击特效
view.effects(ViewEffect.CLICK, 0xff0000, 0.5) -- 点击特效，颜色红色，alpha=0.5
view.effects(ViewEffect.NONE) -- 无效果
```



|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|initParams|table: LuaTable|-|Android|初始化参数|
|invalidate|-|-|-|强制重绘|
|padding|left: Number<br/>top: Number<br/>right: Number<br/>bottom: Number<br/>|-|-|内边距|
|frame|x: Number<br/>y: Number<br/>width: Number<br/>height: Number|-|-|View尺寸|
|backgroundColor|color: Number<br/> alpha: Number<br/>|color, alpha|-|背景色&alpha|
|size|width: Number<br/> height: Number<br/>|width, height|-|尺寸|
|xy|x: Number<br/> y: Number<br/>|x,y|-|x、y坐标
|align|aligns[]: <a href="#align">Align</a> |-|-|设置自身在父容器的布局|
|alignLeft|-|-|-|设置自身位于父容器Left&Top|
|alignTop|-|-|-|设置自身位于父容器Left&Top|
|alignRight|-|-|-|设置自身位于父容器Right&Top|
|alignBottom|-|-|-|设置自身位于父容器Left&Bottom|
|alignLeftTop|-|-|-|设置自身位于父容器Left&Top|
|alignTopLeft|-|-|-|设置自身位于父容器Left&Top|
|alignCenterTop|-|-|-|设置自身位于父容器Center&Top|
|alignTopCenter|-|-|-|设置自身位于父容器Center&Top|
|alignRightTop|-|-|-|设置自身位于父容器Right&Top|
|alignTopRight|-|-|-|设置自身位于父容器Right&Top|
|alignLeftBottom|-|-|-|设置自身位于父容器Left&Bottom|
|alignBottomLeft|-|-|-|设置自身位于父容器Left&Bottom|
|alignCenterBottom|-|-|-|设置自身位于父容器Center&Bottom|
|alignBottomCenter|-|-|-|设置自身位于父容器Center&Bottom|
|alignRightBottom|-|-|-|设置自身位于父容器Right&Bottom|
|alignBottomRight|-|-|-|设置自身位于父容器Right&Bottom|
|alignCenter|-|-|-|设置自身位于父容器Center|
|alignLeftCenter|-|-|-|设置自身位于父容器Left&Center|
|alignCenterLeft|-|-|-|设置自身位于父容器Left&Center|
|alignRightCenter|-|-|-|设置自身位于父容器Right&Center|
|alignCenterRight|-|-|-|设置自身位于父容器Right&Center|
|alignCenterHorizontal|-|-|-|设置自身位于父容器center in horizontal|
|alignHorizontalCenter|-|-|-|设置自身位于父容器center in horizontal|
|alignCenterVertical|-|-|-|设置自身位于父容器center in vertical|
|alignVerticalCenter|-|-|-|设置自身位于父容器center in vertical|
|center|x: Number<br/> y: Number|x, y|-|中心点坐标|
|x|x: Number|x|-|x坐标|
|y|y: Number|y|-|y坐标|
|left|left: Number|left|-|距离父容器左侧边距|
|top|top: Number|top|-|距离父容器上侧边距|
|right|right: Number|right|-|距离父容器右侧边距|
|bottom|bottom: Number|bottom|-|距离父容器底部边距|
|width|width: Number|width|-|宽度|
|minWidth|width: Number|width|-|最小宽度|
|height|height: Number|height|-|高度|
|centerX|x: Number|x|-|中心点x坐标|
|centerY|y: Number|y|-|中心点y坐标|
|visible|v: Boolean|v|-|可见性|
|hidden|v: Boolean|v|-|可见性|
|show|-|-|-|显示|
|isShow|-|v: Boolean|-|是否可见|
|hide|-|-|-|隐藏|
|isHide|-|v: Boolean|-|是否隐藏|
|enabled|v: Boolean|v|-|是否可用|
|alpha|alpha: Number|alpha|-|透明度|
|borderWidth|width: Number|width|-|边框宽度|
|borderColor|color: Number|color|-|边框颜色|
|clipsToBounds|v: Boolean|v|iOS|View边框是否剪接|
|shadowPath|v: Boolean|v|iOS|只对边框外部加阴影|
|masksToBounds|v: Boolean|v|iOS|设置边框是否裁剪|
|shadowOffset|v: Number|v|iOS|设置View阴影偏移位置|
|shadowRadius|v: Number|v|iOS|设置View阴影高斯模糊半径|
|shadowOpacity|v: Number|v|iOS|设置View阴影透明度|
|shadowColor|v: Number|v|iOS|设置View阴影颜色|
|sizeToFit|-|-|-|适应View内容的大小|
|addGestureRecognizer|-|-|iOS|添加手势|
|removeGestureRecognizer|-|-|iOS|移除手势|
|transform3D|v: Number[]|-|iOS|设置3D变换矩阵|
|anchorPoint|x: Number<br/> y: Number|-|-|锚点|
|removeFromSuper|-|-|-|从父容器移除|
|removeFromParent|-|-|-|从父容器移除|
|hasFocus|-|v: Boolean|-|是否有焦点|
|requestFocus|-|-|-|请求焦点|
|clearFocus|-|-|-|取消焦点|
|rotation|v: Number|-|-|旋转角度|
|rotationXY|rx: Number<br/>ry: Number|rx, ry|-|根据x坐标和y坐标得到的旋转角度，pivot|
|scale|sx: Number<br/>sy: Number|sx, sy|-|x，y缩放|
|scaleX|sx: Number|sx|-|x坐标缩放|
|scaleY|sy: Number|sy|-|y坐标缩放|
|translation|tx: Number<br/> ty: Number|x, y|-|x、y位移|
|translationX|tx: Number|tx|-|x坐标位移|
|translationY|ty: Number|ty|-|y坐标位移|
|bringToFront|-|-|-|将view设置到前台|
|scrollTo|sx: Number<br/>sy: Number|-|-|滚动到某个位置|
|scrollBy|sx: Number<br/>sy: Number|-|-|移动一段距离|
|scrollX|sx: Number|sx|-|x方向滚动到某个位置|
|offsetX|sx: Number|sx|-|x方向滚动到某个位置|
|scrollY|sy: Number|sy|-|y方向滚动到某个位置|
|offsetY|sy: Number|sy|-|y方向滚动到某个位置|
|scrollXY|sx: Number<br/> sy: Number|sx, sy|-|x、y方向移动到某个位置|
|offsetXY|sx: Number<br/> sy: Number|sx, sy|-|x、y方向移动到某个位置|
|offset|sx: Number<br/> sy: Number|sx, sy|-|x、y方向移动到某个位置|
|showScrollIndicator|h: Boolean<br/> v: Boolean|h, v|-|设置滚动条是否显示（横向、纵向）
|callback|v: LuaTable|v|-|监听view的各种事件|
|onClick|v: LuaFunction|v|-|设置view的点击事件|
|onLongClick|v: LuaFunction|v|-|设置view的长按事件|
|adjustSize|-|-|-|调整大小以适应内容|
|cornerRadius|radius: Number|radius|-|设置边框圆角半径|
|startAnimation|anims: <a href="#animation">Animation[]</a>|-|-|开始播放动画|
|stopAnimation|-|-|-|停止动画播放|
|isAnimating|-|v: Boolean|-|是否正在播放动画|
|flexCss|v: String|v|-|设置flex属性|
|flxLayout|v: String|v|iOS|设置flex布局|
|effects|effect: <a href="#view_effect">ViewEffect</a><br/> color: Number<br/> alpha: Number|effect|-|设置view的特效|
|nativeView|-|v: Object|-|获取NativeView|

**作为容器的额外方法**

> onShow

```
view.onShow(function()
	print("i am show")
end)
```

> onHide

```
view.onHide(function()
	print("i am hide")
end)
```

> onBack

```
view.onBack(function()
	print("back pressed")
end)
```

> onLayout

```
view.onLayout(function()
	print("i am layouted")
end)
```

> addView

```
child = View()
parent = View()
parent.addView(child)
```

> removeView

```
child = View()
parent = View()
parent.addView(child)
parent.removeView(child)
```

> removeAllViews

```
child = View()
parent = View()
parent.addView(child)
parent.removeAllViews()
```


> children

```
parent.children(function(parent) -- 所有在函数里创建的View都会被自动添加到parent里
	view = View()
	...
end)
```

> flexChildren

```
child1 = View()
child2 = View()
parent = View()
parent.flexChildren(child1, child2)
```

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|onShow|v: LuaFunction|v|-|显示监听|
|onHide|v: LuaFunction|v|-|隐藏监听|
|onBack|v: LuaFunction|v|-|返回按钮监听|
|onLayout|v: LuaFunction|v|-|布局监听|
|addView|v: <a href="#view">View</a>|-|-|添加子View|
|removeView|v: <a href="#view">View</a>|-|-|移除子View|
|removeAllViews|-|-|-|移除所有子View|
|children|v: LuaFunction|-|-|子View构造函数|
|flexChildren|v: <a href="#view">View[]</a>|-|-|Flexbox 设置childViews|

## Label
<aside class="notice" id="label">
文本组件，非容器。
-> <a href="#view">View</a>
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|text|v: String/<a href="#styled_string">StyledString/<a href="#unicode">Unicode</a>|v|-|Label文本|
|textColor|color: Number|color|-|文本颜色|
|textSize|size: Number|size|-|文本字体大小|
|fontSize|size: Number|size|-|文本字体大小|
|fontName|name: String|name|-|文本字体|
|font|name: String<br/> size: Number|name, size|-|文本字体&大小|
|gravity|v: <a href="#gravity">Gravity</a>|v|-|文本对齐方式|
|textAlign|v: <a href="#text_align">TextAlign</a>|v|-|文本对齐方式|
|lines|v: Number|v|-|文字行数|
|maxLines|v: Number|v|-|文本最大行数|
|lineCount|v: Number|v|-|文本最大行数|
|minLines|v: Number|v|-|文本最小行数|
|ellipsize|v: <a href="#ellipsize">Ellipsize</a>|v|-|文本省略方式|
|adjustTextSize|-|-|-|字体大小适应宽度|
|adjustFontSize|-|-|-|字体大小适应宽度|


## Button

<aside class="notice" id="button">
按钮组件，非容器。
-> <a href="#label">Label</a>
-> <a href="#view">View</a>
</aside>


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|title|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|v|-|按钮文字|
|titleColor|color: Number|color|-|-|文本颜色|
|image|img1: String<br/> img2: String|img1, img2|-|-|按钮点按图片（正常，点击）|
|showsTouchWhenHighlighted|-|-|iOS|获取按钮点击是否高亮|

## Image

<aside class="notice" id="image">
图片组件，非容器。
-> <a href="#view">View</a>
</aside>


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|image|v: String, c: LuaFunction|v|-|设置图片url（本地、网络），回调|
|contentMode|type: <a href="#scale_type">ScaleType</a>|type|-|图片缩放模式|
|scaleType|type: <a href="#scale_type">ScaleType</a>|type|-|图片缩放模式|
|startAnimationImages|images: String[]|-|-|帧动画（本地图）|
|stopAnimationImages|-|-|-|停止播放帧动画|
|isAnimationImages|-|-|-|是否正在播放帧动画|


## TextField

<aside class="notice" id="text_field">
输入框组件，非容器。
-> <a href="#label">Label</a>
-> <a href="#view">View</a>
</aside>


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|hint|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|v|-|提示|
|placeholder|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|v|-|提示|

## TableView

<aside class="notice" id="table_view">
(Deprecated see <a href="#collection_view">CollectionView</a>)
<br/>
基础列表组件，容器。
-> <a href="#view">View</a>
</aside>


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|reload|section: Number<br/> row: Number<br/>|-|-|Android支持参数|重新加载列表|
|contentSize|-|-|iOS|设置内容区域大小|
|contentOffset|-|-|iOS|设置内容偏移|
|contentInset|-|-|iOS|设置ContentInset|
|showScrollIndicator|v: Boolean|v|-|是否显示滚动条信息|
|scrollToTop|offset: Number<br/> animate: Boolean|-|-|滚动到顶部(offset间隔，animate是否动画)|
|scrollToCell|section: Number<br/> rowInSection: Number<br/> offset: Number<br/> animate: Boolean|-|-|滚动到指定cell，offset间隔，animate是否动画|
|miniSpacing|space: Number|space|-|cell间隙|
|lazyLoad|v: Boolean|-|-|是否懒加载Cell|
|header|v: <a href="#view">View</a>|-|-|设置Header，nil的时候清空header|
|footer|v: <a href="#view">View</a>|-|-|设置Footer，nil的时候清空footer|
|dividerHeight|v: Number|height: Number|height|-|cell间隙，同miniSpacing|

## CollectionView

<aside class="notice" id="collection_view">
基础列表组件，容器。
-> <a href="#view">View</a>
</aside>


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|reload|section: Number<br/> row: Number<br/>|-|-|Android支持参数|重新加载列表|
|contentSize|-|-|iOS|设置内容区域大小|
|contentOffset|-|-|iOS|设置内容偏移|
|contentInset|-|-|iOS|设置ContentInset|
|showScrollIndicator|v: Boolean|v|-|是否显示滚动条信息|
|scrollToTop|offset: Number<br/> animate: Boolean|-|-|滚动到顶部(offset间隔，animate是否动画)|
|scrollToCell|section: Number<br/> rowInSection: Number<br/> offset: Number<br/> animate: Boolean|-|-|滚动到指定cell，offset间隔，animate是否动画|
|miniSpacing|space: Number|space|-|cell间隙|
|lazyLoad|v: Boolean|-|-|是否懒加载Cell|


## RefreshTableView
<aside class="notice" id="refresh_table_view">
(Deprecated see <a href="#refresh_collection_view">RefreshCollectionView</a>)
<br/>
可刷新列表组件，容器。
-> <a href="#table_view">TableView</a>
-> <a href="#view">View</a>
</aside>


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|refreshEnable|v: Boolean|-|-|-|是否可以刷新|
|initRefreshing|-|-|iOS|初始化刷新组件|
|isRefreshing|-|v: Boolean|-|是否正在刷新|
|startRefreshing|-|-|-|开始刷新|
|stopRefreshing|-|-|-|停止刷新|


## RefreshCollectionView

<aside class="notice" id="refresh_collection_view">
可刷新列表组件，容器。
-> <a href="#collection_view">CollectionView</a>
-> <a href="#view">View</a>
</aside>


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|refreshEnable|v: Boolean|-|-|-|是否可以刷新|
|initRefreshing|-|-|iOS|初始化刷新组件|
|isRefreshing|-|v: Boolean|-|是否正在刷新|
|startRefreshing|-|-|-|开始刷新|
|stopRefreshing|-|-|-|停止刷新|


## PagerView
<aside class="notice" id="pager_view">
页面组组件，容器。
-> <a href="#view">View</a>
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|reload|-|-|-|重新加载数据|
|indicator|v: <a href="#pager_indicator">PagerIndicator</a>|-|-|设置页面组指示器|
|currentPage|v: Number|v|-|设置/获取当前页|
|currentItem|v: Number|v|-|设置/获取当前页|
|autoScroll|duration: Number|-|-|自动轮播|
|looping|v: Boolean|v|-|自动轮播|



## PagerIndicator
<aside class="notice" id="pager_indicator">
页面组指示器组件，非容器。
-> <a href="#view">View</a>
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|unselectedColor|color: Number|color|-|未选中指示器颜色|
|selectedColor|color: Number|color|-|选中指示器颜色|
|fillColor|color: Number|color|-|未选中指示器颜色|
|pageColor|color: Number|color|-|选中指示器颜色|
|strokeWidth|width: Number|width|Android|线条宽度|
|strokeColor|color: Number|color|Android|线条颜色|
|radius|v: Number|v|Android|圆点半径|
|snap|v: Boolean|v|Android|是否有点移动动画|
|currentPage|v: Number|v|-|设置/获取当前页面|
|currentItem|v: Number|v|-|设置/获取当前页面|


## CustomPagerIndicator
<aside class="notice" id="custom_pager_indicator">
(Deprecated)
<br/>
自定义页面组指示器组件，非容器，Android特有。
-> <a href="#view">View</a>
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|currentPage|v: Number|v|Android|设置/获取当前页面|
|currentItem|v: Number|v|Android|设置/获取当前页面|

## CustomPanel
<aside class="notice" id="custom_pager_indicator">
自定义组件，容器。
-> <a href="#view">View</a>
</aside>

供第三方扩展用，不可直接创建。第三方通过扩展CustomPanel，实现已有的 Native UI 组件与 lua 互操作。

扩展后的CustomPanel，有所有View容器的API，如 frame、size、backgroundColor 等。

> CustomPanel 扩展 - Android

```
1. 扩展LVCustomPanel，创建Native UI，并将创建出来的View添加到CustomPanel里

public class CustomLoading extends LVCustomPanel {

    public CustomLoading(Globals globals, LuaValue metaTable, Varargs varargs) {
        super(globals, metaTable, varargs);
    }

    @Override
    public void initPanel() {
        final View customLoading = new NativeLoading(getContext());
        LayoutParams layoutParams = LuaViewUtil.createRelativeLayoutParamsWW();
        layoutParams.addRule(RelativeLayout.CENTER_IN_PARENT);
        customLoading.setVisibility(View.VISIBLE);
        addView(customLoading, layoutParams);
    }
}

2. 使用LuaView对象初始化的时候注册该 CustomPanel

luaview.registerPanel(CustomLoading.class)

或

luaview.registerPanel("CustomLoading", CustomLoading.class)

3. 在lua里使用该 CustomPanel，CustomPanel有所有View的api

local loading = CustomLoading()
loading.frame(0, 0, 100, 100)

```

## HScrollView
<aside class="notice" id="h_scroll_view">
横向滑动组件，容器。
-> <a href="#view">View</a>
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|offset|x: Number<br/> y: Number<br/> smooth: Boolean|x, y|-|滚动到x,y，smooth表示是否平滑滚动|
|scrollTo|x: Number<br/> y: Number<br/> smooth: Boolean|-|-|滚动到x,y，smooth表示是否平滑滚动|
|offsetBy|dx: Number<br/> dy: Number<br/> smooth: Boolean|x, y|-|滚动dx,dy，smooth表示是否平滑滚动|
|scrollBy|dx: Number<br/> dy: Number<br/> smooth: Boolean|-|-|滚动dx,dy，smooth表示是否平滑滚动|
|smoothScrollTo|x: Number<br/> y: Number|-|-|平滑滚动到x,y|
|smoothScrollBy|x: Number<br/> y: Number|-|-|滚动到x,y|
|pageScroll|direction: Number|-|Android|滚动一页(direction>0右滚，否则左滚)|
|fullScroll|direction: Number|-|Android|滚动到底(direction>0右滚，否则左滚)|
|contentSize|-|-|iOS|内容区域大小|


## WebView
<aside class="notice" id="web_view">
html组件，容器。
-> <a href="#view">View</a>
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|loadUrl|v: String|-|-|加载url|
|canGoBack|-|v: Boolean|-|是否可以回退|
|canGoForward|-|v: Boolean|-|是否可以前进|
|goBack|-|-|-|回退一页|
|goForward|-|-|-|前进一页|
|reload|-|-|-|重新加载|
|title|-|v: String|-|获取Title|
|isLoading|-|v: Boolean|-|是否正在加载|
|stopLoading|-|-|-|停止加载|
|url|-|v: String|-|获取url|
|pullRefreshEnable|v: Boolean|v|-|是否可以下拉刷新|

## LoadingIndicator
<aside class="notice" id="loading_indicator">
加载指示器组件，容器。
-> <a href="#view">View</a>
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|start|-|-|-|开始转动|
|isStart|-|v: Boolean|-|是否开始转动|
|startAnimating|-|-|-|开始转动|
|isAnimating|-|v: Boolean|-|是否在动画中|
|stop|-|-|-|停止动画|
|stopAnimating|-|-|-|停止动画|
|color|v: Number|v|-|颜色|


## LoadingDialog
<aside class="notice" id="loading_dialog">
加载对话框组件。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|show|-|-|-|开始转动|
|isShow|-|v: Boolean|-|是否开始转动|
|start|-|-|-|开始转动|
|isStart|-|v: Boolean|-|是否开始转动|
|startAnimating|-|-|-|开始转动|
|isAnimating|-|v: Boolean|-|是否开始转动|
|hide|-|-|-|停止动画|
|stop|-|-|-|停止动画|
|stopAnimating|-|-|-|停止动画|
|color|v: Number|v|-|颜色|


## Alert

> Alert

```
Alert("提示", "这是一个提示", "OK", function()
	print("OK clicked")
end)


Alert("提示", "这是一个提示", "OK", "Cancel", function()
	print("OK clicked")
end, function()
	print("Cancel clicked")
end)


local as1 = StyledString("一个按钮", { fontColor = 0xffff0000, backgroundColor = 0xff00ff00, fontSize = 30 })
local text = StyledString("文字", { fontColor = 0xffff0000, backgroundColor = 0xff00ff00, fontSize = 30 })
local ok = StyledString("确定", { fontColor = 0xffff0000, backgroundColor = 0xff00ff00, fontSize = 30 })
Alert(as1, text, ok, function()
    print("点击了")
end)
```

<aside class="notice" id="alert">
对话框组件。
</aside>

Alert(title, content, buttonTexts[], buttonCallbacks[])

* title: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>
* content: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>
* buttonTexts[]: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a> []
* buttonCallbacks[]: LuaFunction[]

## Toast

> Toast

```
Toast("测试")

Toast(StyledString("测试", {fontColor=0xffff0000, backgroundColor=0xff00ff00, fontSize=50}))
```


<aside class="notice" id="toast">
提示信息组件。
</aside>

Toast(message)

* message: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|show|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|-|-|显示提示|


## StyledString

> StyledString

```
StyledString("test", { fontColor = 0xff0000ff, fontSize = 14 })

StyledString(Unicode(0xe607), { fontColor = 0xff00aaff, fontStyle = "bold" })
```


<aside class="notice" id="styled_string">
富文本组件。
</aside>

StyledString(text, config)

* text: String/<a href="#unicode">Unicode</a>
* config: LuaTable
	* fontSize: Number, 文字大小
	* fontColor: Number, 文字颜色
	* fontName: String, 文字样式
	* fontWeight: Number/<a href="#font_weight">FontWeight</a>, 文字权重
	* fontStyle: String/<a href="#font_style">FontStyle</a>，文字样式
	* backgroundColor: Number, 文字背景色
	* strikethrough: Boolean，是否删除线
	* underline: Boolean，是否下划线

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|append|v: <a href="#styled_string">StyledString</a>|v|-|新增一段|


## Animation

> Animation

```
-- alpha动画
Animation().scale(2, 0.5).duration(2).delay(1)

-- 位移动画
view = View()
Animation().with(view).translation(100, -100).duration(3).interpolator(Interpolator.ACCELERATE_DECELERATE).callback({
    onStart = function()
        print("Running")
    end,
    onCancel = function()
        print("Canceled")
    end,
    onEnd = function()
        print("End")
    end,
    onPause = function()
        print("Paused")
    end,
    onResume = function()
        print("Running")
    end,
})
```


<aside class="notice" id="animation">
动画组件。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|with|v: <a href="#view">View</a>|-|-|设置动画target|
|start|-|-|-|开始动画|
|alpha|v0: Number<br/> v1: Number|-|-|设置alpha动画|
|rotation|v0: Number<br/> v1: Number|-|-|设置旋转动画|
|scale|x: Number<br/> y: Number|-|-|设置缩放动画(x轴缩放比、y轴缩放比)|
|scaleX|x: Number<br/>|-|-|设置x轴缩放动画|
|scaleY|y: Number<br/>|-|-|设置y轴缩放动画|
|translation|x: Number<br/> y: Number<br/>|-|-|设置x轴、y轴位移动画|
|translationX|x: Number|-|-|设置x轴位移动画|
|translationY|y: Number|-|-|设置y轴位移动画|
|duration|time: Number|-|-|设置动画时长|
|delay|time: Number|-|-|设置动画启动延时|
|repeatCount|count: Number|-|-|设置动画重复测试（<0表示一直重复）|
|interpolator|v: <a href="#interlator">Interplator<a/>|-|-|插值器|
|cancel|-|-|-|取消动画|
|pause|-|-|-|暂停动画|
|isPaused|-|v: Boolean|-|动画是否暂停|
|isRunning|-|v: Boolean|-|动画是否运行|
|resume|-|-|-|恢复动画|
|reverses|v: Boolean|-|-|动画重复播放时是否反转|
|values|v: Number[]|-|-|设置动画用到的参数|
|callback|v: LuaTable|-|-|设置动画的回调|
|onStart|v: LuaFunction|-|-|动画开始回调|
|onEnd|v: LuaFunction|-|-|动画结束回调|
|onRepeat|v: LuaFunction|-|-|动画重复回调|
|onCancel|v: LuaFunction|-|-|动画取消回调|
|onPause|v: LuaFunction|-|-|动画暂停回调|
|onUpdate|v: LuaFunction|-|Android|动画状态更新回调|
|onResume|v: LuaFunction|-|-|动画恢复回调|

## Navigation

> Navigation

```
Navigation.title("测试view")


img = Image();
img.image("http://gtms02.alicdn.com/tps/i2/TB1qmXnHpXXXXcuaXXXQG.m0FXX-640-128.jpg",function()
	Navigation.background(img)
end);
```

<aside class="notice" id="animation">
导航条组件，静态。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|title|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|v|-|导航条标题|
|background|v: String/<a href="#image">Image</a>|-|-|设置导航条背景|
|left|v: Boolean|v|-|显示左侧按钮|
|right|v: Boolean|v|-|显示右侧按钮|

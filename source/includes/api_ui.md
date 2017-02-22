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



|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|initParams|table: LuaTable|-|Android|初始化参数|
|2|invalidate|-|-|-|强制重绘|
|3|padding|left: Number<br/>top: Number<br/>right: Number<br/>bottom: Number<br/>|-|-|内边距|
|4|frame|x: Number<br/>y: Number<br/>width: Number<br/>height: Number|-|-|View尺寸|
|5|backgroundColor|color: Number<br/> alpha: Number<br/>|color, alpha|-|背景色&alpha|
|6|size|width: Number<br/> height: Number<br/>|width, height|-|尺寸|
|7|xy|x: Number<br/> y: Number<br/>|x,y|-|x、y坐标
|8|align|aligns[]: <a href="#align">Align</a> |-|-|设置自身在父容器的布局|
|9|alignLeft|-|-|-|设置自身位于父容器Left&Top|
|10|alignTop|-|-|-|设置自身位于父容器Left&Top|
|11|alignRight|-|-|-|设置自身位于父容器Right&Top|
|12|alignBottom|-|-|-|设置自身位于父容器Left&Bottom|
|13|alignLeftTop|-|-|-|设置自身位于父容器Left&Top|
|14|alignTopLeft|-|-|-|设置自身位于父容器Left&Top|
|15|alignCenterTop|-|-|-|设置自身位于父容器Center&Top|
|16|alignTopCenter|-|-|-|设置自身位于父容器Center&Top|
|17|alignRightTop|-|-|-|设置自身位于父容器Right&Top|
|18|alignTopRight|-|-|-|设置自身位于父容器Right&Top|
|19|alignLeftBottom|-|-|-|设置自身位于父容器Left&Bottom|
|20|alignBottomLeft|-|-|-|设置自身位于父容器Left&Bottom|
|21|alignCenterBottom|-|-|-|设置自身位于父容器Center&Bottom|
|22|alignBottomCenter|-|-|-|设置自身位于父容器Center&Bottom|
|23|alignRightBottom|-|-|-|设置自身位于父容器Right&Bottom|
|24|alignBottomRight|-|-|-|设置自身位于父容器Right&Bottom|
|25|alignCenter|-|-|-|设置自身位于父容器Center|
|26|alignLeftCenter|-|-|-|设置自身位于父容器Left&Center|
|27|alignCenterLeft|-|-|-|设置自身位于父容器Left&Center|
|28|alignRightCenter|-|-|-|设置自身位于父容器Right&Center|
|29|alignCenterRight|-|-|-|设置自身位于父容器Right&Center|
|30|alignCenterHorizontal|-|-|-|设置自身位于父容器center in horizontal|
|31|alignHorizontalCenter|-|-|-|设置自身位于父容器center in horizontal|
|32|alignCenterVertical|-|-|-|设置自身位于父容器center in vertical|
|33|alignVerticalCenter|-|-|-|设置自身位于父容器center in vertical|
|34|center|x: Number<br/> y: Number|x, y|-|中心点坐标|
|35|x|x: Number|x|-|x坐标|
|36|y|y: Number|y|-|y坐标|
|37|left|left: Number|left|-|距离父容器左侧边距|
|38|top|top: Number|top|-|距离父容器上侧边距|
|39|right|right: Number|right|-|距离父容器右侧边距|
|40|bottom|bottom: Number|bottom|-|距离父容器底部边距|
|41|width|width: Number|width|-|宽度|
|42|minWidth|width: Number|width|-|最小宽度|
|43|height|height: Number|height|-|高度|
|44|centerX|x: Number|x|-|中心点x坐标|
|45|centerY|y: Number|y|-|中心点y坐标|
|46|visible|v: Boolean|v|-|可见性|
|47|hidden|v: Boolean|v|-|可见性|
|48|show|-|-|-|显示|
|49|isShow|-|v: Boolean|-|是否可见|
|50|hide|-|-|-|隐藏|
|51|isHide|-|v: Boolean|-|是否隐藏|
|52|enabled|v: Boolean|v|-|是否可用|
|53|alpha|alpha: Number|alpha|-|透明度|
|54|borderWidth|width: Number|width|-|边框宽度|
|55|borderColor|color: Number|color|-|边框颜色|
|56|clipsToBounds|v: Boolean|v|iOS|View边框是否剪接|
|57|shadowPath|v: Boolean|v|iOS|只对边框外部加阴影|
|58|masksToBounds|v: Boolean|v|iOS|设置边框是否裁剪|
|59|shadowOffset|v: Number|v|iOS|设置View阴影偏移位置|
|60|shadowRadius|v: Number|v|iOS|设置View阴影高斯模糊半径|
|61|shadowOpacity|v: Number|v|iOS|设置View阴影透明度|
|62|shadowColor|v: Number|v|iOS|设置View阴影颜色|
|63|sizeToFit|-|-|-|适应View内容的大小|
|64|addGestureRecognizer|-|-|iOS|添加手势|
|65|removeGestureRecognizer|-|-|iOS|移除手势|
|66|transform3D|v: Number[]|-|iOS|设置3D变换矩阵|
|67|anchorPoint|x: Number<br/> y: Number|-|-|锚点|
|68|removeFromSuper|-|-|-|从父容器移除|
|69|removeFromParent|-|-|-|从父容器移除|
|70|hasFocus|-|v: Boolean|-|是否有焦点|
|71|requestFocus|-|-|-|请求焦点|
|72|clearFocus|-|-|-|取消焦点|
|73|rotation|v: Number|-|-|旋转角度|
|74|rotationXY|rx: Number<br/>ry: Number|rx, ry|-|根据x坐标和y坐标得到的旋转角度，pivot|
|75|scale|sx: Number<br/>sy: Number|sx, sy|-|x，y缩放|
|76|scaleX|sx: Number|sx|-|x坐标缩放|
|77|scaleY|sy: Number|sy|-|y坐标缩放|
|78|translation|tx: Number<br/> ty: Number|x, y|-|x、y位移|
|79|translationX|tx: Number|tx|-|x坐标位移|
|80|translationY|ty: Number|ty|-|y坐标位移|
|81|bringToFront|-|-|-|将view设置到前台|
|82|scrollTo|sx: Number<br/>sy: Number|-|-|滚动到某个位置|
|83|scrollBy|sx: Number<br/>sy: Number|-|-|移动一段距离|
|84|scrollX|sx: Number|sx|-|x方向滚动到某个位置|
|85|offsetX|sx: Number|sx|-|x方向滚动到某个位置|
|86|scrollY|sy: Number|sy|-|y方向滚动到某个位置|
|87|offsetY|sy: Number|sy|-|y方向滚动到某个位置|
|88|scrollXY|sx: Number<br/> sy: Number|sx, sy|-|x、y方向移动到某个位置|
|89|offsetXY|sx: Number<br/> sy: Number|sx, sy|-|x、y方向移动到某个位置|
|90|offset|sx: Number<br/> sy: Number|sx, sy|-|x、y方向移动到某个位置|
|91|showScrollIndicator|h: Boolean<br/> v: Boolean|h, v|-|设置滚动条是否显示（横向、纵向）
|92|callback|v: LuaTable|v|-|监听view的各种事件|
|93|onClick|v: LuaFunction|v|-|设置view的点击事件|
|94|onLongClick|v: LuaFunction|v|-|设置view的长按事件|
|95|adjustSize|-|-|-|调整大小以适应内容|
|96|cornerRadius|radius: Number|radius|-|设置边框圆角半径|
|97|startAnimation|anims: <a href="#animation">Animation[]</a>|-|-|开始播放动画|
|98|stopAnimation|-|-|-|停止动画播放|
|99|isAnimating|-|v: Boolean|-|是否正在播放动画|
|100|flexCss|v: String|v|-|设置flex属性|
|101|flxLayout|v: String|v|iOS|设置flex布局|
|102|effects|effect: <a href="#view_effect">ViewEffect</a><br/> color: Number<br/> alpha: Number|effect|-|设置view的特效|
|103|nativeView|-|v: Object|-|获取NativeView|
|104|borderDash|v: Number|-|-|设置边框虚线|
|105|margin|l: Number<br/> t: Number<br/> r: Number<br/> b: Number|l, t, r, b|边距|
|106|onTouch|v: LuaFunction|v|设置触摸事件|

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

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|onShow|v: LuaFunction|v|-|显示监听|
|2|onHide|v: LuaFunction|v|-|隐藏监听|
|3|onBack|v: LuaFunction|v|-|返回按钮监听|
|4|onLayout|v: LuaFunction|v|-|布局监听|
|5|addView|v: <a href="#view">View</a>|-|-|添加子View|
|6|removeView|v: <a href="#view">View</a>|-|-|移除子View|
|7|removeAllViews|-|-|-|移除所有子View|
|8|children|v: LuaFunction|-|-|子View构造函数|
|9|flexChildren|v: <a href="#view">View[]</a>|-|-|Flexbox 设置childViews|

## Label
<aside class="notice" id="label">
文本组件，非容器。
-> <a href="#view">View</a>
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|text|v: String/<a href="#styled_string">StyledString/<a href="#unicode">Unicode</a>|v|-|Label文本|
|2|textColor|color: Number|color|-|文本颜色|
|3|textSize|size: Number|size|-|文本字体大小|
|4|fontSize|size: Number|size|-|文本字体大小|
|5|fontName|name: String|name|-|文本字体|
|6|font|name: String<br/> size: Number|name, size|-|文本字体&大小|
|7|gravity|v: <a href="#gravity">Gravity</a>|v|-|文本对齐方式|
|8|textAlign|v: <a href="#text_align">TextAlign</a>|v|-|文本对齐方式|
|9|lines|v: Number|v|-|文字行数|
|10|maxLines|v: Number|v|-|文本最大行数|
|11|lineCount|v: Number|v|-|文本最大行数|
|12|minLines|v: Number|v|-|文本最小行数|
|13|ellipsize|v: <a href="#ellipsize">Ellipsize</a>|v|-|文本省略方式|
|14|adjustTextSize|-|-|-|字体大小适应宽度|
|15|adjustFontSize|-|-|-|字体大小适应宽度|


## Button

<aside class="notice" id="button">
按钮组件，非容器。
-> <a href="#label">Label</a>
-> <a href="#view">View</a>
</aside>


|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|title|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|v|-|按钮文字|
|2|titleColor|color: Number|color|-|-|文本颜色|
|3|image|img1: String<br/> img2: String|img1, img2|-|-|按钮点按图片（正常，点击）|
|4|showsTouchWhenHighlighted|-|-|iOS|获取按钮点击是否高亮|

## Image

<aside class="notice" id="image">
图片组件，非容器。
-> <a href="#view">View</a>
</aside>


|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|image|v: String, c: LuaFunction|v|-|设置图片url（本地、网络），回调|
|2|contentMode|type: <a href="#scale_type">ScaleType</a>|type|-|图片缩放模式|
|3|scaleType|type: <a href="#scale_type">ScaleType</a>|type|-|图片缩放模式|
|4|startAnimationImages|images: String[]|-|-|帧动画（本地图）|
|5|stopAnimationImages|-|-|-|停止播放帧动画|
|6|isAnimationImages|-|-|-|是否正在播放帧动画|


## TextField

<aside class="notice" id="text_field">
输入框组件，非容器。
-> <a href="#label">Label</a>
-> <a href="#view">View</a>
</aside>


|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|hint|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|v|-|提示|
|2|placeholder|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|v|-|提示|

## TableView

<aside class="notice" id="table_view">
(Deprecated see <a href="#collection_view">CollectionView</a>)
<br/>
基础列表组件，容器。
-> <a href="#view">View</a>
</aside>


|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|reload|section: Number<br/> row: Number<br/>|-|-|Android支持参数|重新加载列表|
|2|contentSize|-|-|iOS|设置内容区域大小|
|3|contentOffset|-|-|iOS|设置内容偏移|
|4|contentInset|-|-|iOS|设置ContentInset|
|5|showScrollIndicator|v: Boolean|v|-|是否显示滚动条信息|
|6|scrollToTop|offset: Number<br/> animate: Boolean|-|-|滚动到顶部(offset间隔，animate是否动画)|
|7|scrollToCell|section: Number<br/> rowInSection: Number<br/> offset: Number<br/> animate: Boolean|-|-|滚动到指定cell，offset间隔，animate是否动画|
|8|miniSpacing|space: Number|space|-|cell间隙|
|9|lazyLoad|v: Boolean|-|-|是否懒加载Cell|
|10|header|v: <a href="#view">View</a>|-|-|设置Header，nil的时候清空header|
|11|footer|v: <a href="#view">View</a>|-|-|设置Footer，nil的时候清空footer|
|12|dividerHeight|v: Number|height: Number|height|-|cell间隙，同miniSpacing|

## CollectionView

<aside class="notice" id="collection_view">
基础列表组件，容器。
-> <a href="#view">View</a>
</aside>


|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|reload|section: Number<br/> row: Number<br/>|-|-|Android支持参数|重新加载列表|
|2|contentSize|-|-|iOS|设置内容区域大小|
|3|contentOffset|-|-|iOS|设置内容偏移|
|4|contentInset|-|-|iOS|设置ContentInset|
|5|showScrollIndicator|v: Boolean|v|-|是否显示滚动条信息|
|6|scrollToTop|offset: Number<br/> animate: Boolean|-|-|滚动到顶部(offset间隔，animate是否动画)|
|7|scrollToCell|section: Number<br/> rowInSection: Number<br/> offset: Number<br/> animate: Boolean|-|-|滚动到指定cell，offset间隔，animate是否动画|
|8|miniSpacing|space: Number|space|-|cell间隙|
|9|lazyLoad|v: Boolean|-|-|是否懒加载Cell|


## RefreshTableView
<aside class="notice" id="refresh_table_view">
(Deprecated see <a href="#refresh_collection_view">RefreshCollectionView</a>)
<br/>
可刷新列表组件，容器。
-> <a href="#table_view">TableView</a>
-> <a href="#view">View</a>
</aside>


|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|refreshEnable|v: Boolean|-|-|-|是否可以刷新|
|2|initRefreshing|-|-|iOS|初始化刷新组件|
|3|isRefreshing|-|v: Boolean|-|是否正在刷新|
|4|startRefreshing|-|-|-|开始刷新|
|5|stopRefreshing|-|-|-|停止刷新|


## RefreshCollectionView

<aside class="notice" id="refresh_collection_view">
可刷新列表组件，容器。
-> <a href="#collection_view">CollectionView</a>
-> <a href="#view">View</a>
</aside>


|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|refreshEnable|v: Boolean|-|-|-|是否可以刷新|
|2|initRefreshing|-|-|iOS|初始化刷新组件|
|3|isRefreshing|-|v: Boolean|-|是否正在刷新|
|4|startRefreshing|-|-|-|开始刷新|
|5|stopRefreshing|-|-|-|停止刷新|


## PagerView
<aside class="notice" id="pager_view">
页面组组件，容器。
-> <a href="#view">View</a>
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|reload|-|-|-|重新加载数据|
|2|indicator|v: <a href="#pager_indicator">PagerIndicator</a>|-|-|设置页面组指示器|
|3|currentPage|v: Number|v|-|设置/获取当前页|
|4|currentItem|v: Number|v|-|设置/获取当前页|
|5|autoScroll|duration: Number|-|-|自动轮播|
|6|looping|v: Boolean|v|-|自动轮播|
|7|previewSide|l: Number, r: Number|-|-|支持左右透出预览|



## PagerIndicator
<aside class="notice" id="pager_indicator">
页面组指示器组件，非容器。
-> <a href="#view">View</a>
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|unselectedColor|color: Number|color|-|未选中指示器颜色|
|2|selectedColor|color: Number|color|-|选中指示器颜色|
|3|fillColor|color: Number|color|-|未选中指示器颜色|
|4|pageColor|color: Number|color|-|选中指示器颜色|
|5|strokeWidth|width: Number|width|Android|线条宽度|
|6|strokeColor|color: Number|color|Android|线条颜色|
|7|radius|v: Number|v|Android|圆点半径|
|8|snap|v: Boolean|v|Android|是否有点移动动画|
|9|currentPage|v: Number|v|-|设置/获取当前页面|
|10|currentItem|v: Number|v|-|设置/获取当前页面|


## CustomPagerIndicator
<aside class="notice" id="custom_pager_indicator">
(Deprecated)
<br/>
自定义页面组指示器组件，非容器，Android特有。
-> <a href="#view">View</a>
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|currentPage|v: Number|v|Android|设置/获取当前页面|
|2|currentItem|v: Number|v|Android|设置/获取当前页面|

## CustomPanel
<aside class="notice" id="custom_pager_indicator">
自定义组件，容器。
-> <a href="#view">View</a>
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|nativeView|-|-|-|获取NativeView|
|2|getNativeView|-|-|-|获取NativeView|


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

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|offset|x: Number<br/> y: Number<br/> smooth: Boolean|x, y|-|滚动到x,y，smooth表示是否平滑滚动|
|2|scrollTo|x: Number<br/> y: Number<br/> smooth: Boolean|-|-|滚动到x,y，smooth表示是否平滑滚动|
|3|offsetBy|dx: Number<br/> dy: Number<br/> smooth: Boolean|x, y|-|滚动dx,dy，smooth表示是否平滑滚动|
|4|scrollBy|dx: Number<br/> dy: Number<br/> smooth: Boolean|-|-|滚动dx,dy，smooth表示是否平滑滚动|
|5|smoothScrollTo|x: Number<br/> y: Number|-|-|平滑滚动到x,y|
|6|smoothScrollBy|x: Number<br/> y: Number|-|-|滚动到x,y|
|7|pageScroll|direction: Number|-|Android|滚动一页(direction>0右滚，否则左滚)|
|8|fullScroll|direction: Number|-|Android|滚动到底(direction>0右滚，否则左滚)|
|9|contentSize|-|-|iOS|内容区域大小|


## WebView
<aside class="notice" id="web_view">
html组件，容器。
-> <a href="#view">View</a>
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|loadUrl|v: String|-|-|加载url|
|2|canGoBack|-|v: Boolean|-|是否可以回退|
|3|canGoForward|-|v: Boolean|-|是否可以前进|
|4|goBack|-|-|-|回退一页|
|5|goForward|-|-|-|前进一页|
|6|reload|-|-|-|重新加载|
|7|title|-|v: String|-|获取Title|
|8|isLoading|-|v: Boolean|-|是否正在加载|
|9|stopLoading|-|-|-|停止加载|
|10|url|-|v: String|-|获取url|
|11|pullRefreshEnable|v: Boolean|v|-|是否可以下拉刷新|

## LoadingIndicator
<aside class="notice" id="loading_indicator">
加载指示器组件，容器。
-> <a href="#view">View</a>
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|start|-|-|-|开始转动|
|2|isStart|-|v: Boolean|-|是否开始转动|
|3|startAnimating|-|-|-|开始转动|
|4|isAnimating|-|v: Boolean|-|是否在动画中|
|5|stop|-|-|-|停止动画|
|6|stopAnimating|-|-|-|停止动画|
|7|color|v: Number|v|-|颜色|


## LoadingDialog
<aside class="notice" id="loading_dialog">
加载对话框组件。
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|show|-|-|-|开始转动|
|2|isShow|-|v: Boolean|-|是否开始转动|
|3|start|-|-|-|开始转动|
|4|isStart|-|v: Boolean|-|是否开始转动|
|5|startAnimating|-|-|-|开始转动|
|6|isAnimating|-|v: Boolean|-|是否开始转动|
|7|hide|-|-|-|停止动画|
|8|stop|-|-|-|停止动画|
|9|stopAnimating|-|-|-|停止动画|
|10|color|v: Number|v|-|颜色|


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


|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|show|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|-|-|显示提示|


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

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|append|v: <a href="#styled_string">StyledString</a>|v|-|新增一段|


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

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|with|v: <a href="#view">View</a>|-|-|设置动画target|
|2|start|-|-|-|开始动画|
|3|alpha|v0: Number<br/> v1: Number|-|-|设置alpha动画|
|4|rotation|v0: Number<br/> v1: Number|-|-|设置旋转动画|
|5|scale|x: Number<br/> y: Number|-|-|设置缩放动画(x轴缩放比、y轴缩放比)|
|6|scaleX|x: Number<br/>|-|-|设置x轴缩放动画|
|7|scaleY|y: Number<br/>|-|-|设置y轴缩放动画|
|8|translation|x: Number<br/> y: Number<br/>|-|-|设置x轴、y轴位移动画|
|9|translationX|x: Number|-|-|设置x轴位移动画|
|10|translationY|y: Number|-|-|设置y轴位移动画|
|11|duration|time: Number|-|-|设置动画时长|
|12|delay|time: Number|-|-|设置动画启动延时|
|13|repeatCount|count: Number|-|-|设置动画重复测试（<0表示一直重复）|
|14|interpolator|v: <a href="#interlator">Interplator<a/>|-|-|插值器|
|15|cancel|-|-|-|取消动画|
|16|pause|-|-|-|暂停动画|
|17|isPaused|-|v: Boolean|-|动画是否暂停|
|18|isRunning|-|v: Boolean|-|动画是否运行|
|19|resume|-|-|-|恢复动画|
|20|reverses|v: Boolean|-|-|动画重复播放时是否反转|
|21|values|v: Number[]|-|-|设置动画用到的参数|
|22|callback|v: LuaTable|-|-|设置动画的回调|
|23|onStart|v: LuaFunction|-|-|动画开始回调|
|24|onEnd|v: LuaFunction|-|-|动画结束回调|
|25|onRepeat|v: LuaFunction|-|-|动画重复回调|
|26|onCancel|v: LuaFunction|-|-|动画取消回调|
|27|onPause|v: LuaFunction|-|-|动画暂停回调|
|28|onUpdate|v: LuaFunction|-|Android|动画状态更新回调|
|29|onResume|v: LuaFunction|-|-|动画恢复回调|

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

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|title|v: String/<a href="#styled_string">StyledString</a>/<a href="#unicode">Unicode</a>|v|-|导航条标题|
|2|background|v: String/<a href="#image">Image</a>|-|-|设置导航条背景|
|3|left|v: Boolean|v|-|显示左侧按钮|
|4|right|v: Boolean|v|-|显示右侧按钮|

## Canvas

> Canvas

```
local view = CustomView() -- onDraw方法需要配合CustomView使用
view.onDraw(function(canvas)
	print(canvas)
	-- drawLine
	canvas.color(0xff0000)
	canvas.strokeWidth(2)
	canvas.drawLine(0, 50, 100, 50)
	canvas.drawLine(50, 0, 50, 100)

	canvas.resetPaint()
	canvas.color(0x00ff00)
	canvas.alpha(0.5)
	canvas.drawLine(0, 0, 100, 0)
	canvas.drawLine(100, 0, 100, 100)
	canvas.drawLine(100, 100, 0, 100)
	canvas.drawLine(0, 100, 0, 0)
	canvas.drawLine(0, 0, 100, 100)
	canvas.drawLine(100, 0, 0, 100)

	-- drawPoint
	canvas.color(0xff0000)
	canvas.strokeWidth(2)
	canvas.drawPoint(1, 5)
	canvas.drawPoint(99, 93)

	-- drawRect
	canvas.resetPaint()
	canvas.style(PaintStyle.STROKE)
	canvas.drawRect(5, 5, 5, 5)
	canvas.style(PaintStyle.FILL)
	canvas.drawRect(10, 10, 5, 5)

	-- drawRoundRects
	canvas.drawRoundRect(45, 1, 5, 5, 2, 2)
	canvas.drawRoundRect(45, 5, 10, 5, 2, 2)

	-- drawCircle
	canvas.drawCircle(80, 0, 5)
	canvas.drawCircle(80, 15, 5)

	-- drawText
	canvas.textSize(20)
	canvas.drawText("x", 20, 55)
	canvas.textSize(14)
	canvas.drawText("y", 20, 65)
	canvas.resetPaint()

	-- drawOval
	canvas.drawOval(45, 50, 25, 10)
	canvas.drawOval(45, 60, 25, 10)

	-- draw Arc
	canvas.drawArc(30, 30, 20, 20, 0, 90, true)

	-- drawBitmap
	canvas.save()
	canvas.rotate(-10, 100, 100)
	canvas.scale(1.2)
	canvas.translate(-10, -10)
	canvas.strokeWidth(10)
	canvas.textSize(15)
	canvas.bold(true)
	canvas.drawText("测试一下", 20, 150)
	canvas.alpha(0.5)
	canvas.drawImage("animate1", 0, 100, 100, 100)
	canvas.restore()
	canvas.resetPaint()

	print(img)
	if(img) then
			canvas.drawImage(img, 100, 0, 100, 100)
	end

	-- clipRect
	canvas.clipRect(100, 100, 35, 35)
	canvas.drawCircle(100, 100, 40)

	canvas.clipRect(150, 150, 30, 30)
	canvas.drawText("TestABCDEFGHEFGHIJKLMOPQRST", 150, 150)

	print(canvas.nativeObj())
end)



-- ps
1. Android所有绘制API支持同时多个参数，如：
canvas.drawLine({
        { 0, 0, 100, 0 },
        { 100, 0, 100, 100 },
        { 100, 100, 0, 100 },
        { 0, 100, 0, 0 },
        { 0, 0, 100, 100 },
        { 100, 0, 0, 100 }
    })
2. Android所有绘制API支持设置绘制参数，如：		
canvas.drawText({
        { "xx", 20, 75, { color = 0x0000ff, strikeThrough = true, textSize = 20, textSkewX = 1.5, bold = true } },
        { "yy", 20, 85 },
    }, { color = 0x0fff00, underline = true, textSize = 10, textScaleX = 3, letterSpacing = 0.2, linearText = true })
```

<aside class="notice" id="canvas">
自定义绘制组件。
</aside>

### a. 绘制API

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|drawLine|x1: Number<br/> y1: Number<br/> x2: Number<br/> y2: Number<br/>|-|-|绘制线条。(x1,y1), (x2, y2)分别为起点终点|
|2|drawPoint|x: Number<br/> y: Number<br/>|-|-|绘制点|
|3|drawRect|x: Number<br/> y: Number<br/> w: Number<br/> h: Number<br/>|-|-|绘制矩形。x起点x坐标，y起点y坐标，w宽度，h高度|
|4|drawRoundRect|x: Number<br/> y: Number<br/> w: Number<br/> h: Number<br/> rx: Number<br/> ry: Number<br/>|-|-|绘制圆角矩形。x起点x坐标，y起点y坐标，w宽度，h高度，rx为x轴圆角半径，ry为y轴圆角半径|
|5|drawCircle|x: Number<br/> y: Number<br/> r: Number|-|-|绘制圆。(x, y)为圆心坐标，r为半径|
|6|drawOval|x: Number<br/> y: Number<br/> rx: Number<br/> ry: Number|-|-|绘制椭圆。(x, y)为圆心坐标，rx, ry为椭圆半径|
|7|drawArc|x: Number<br/> y: Number<br/> w: Number<br/> h: Number<br/> startAngle: Number<br/> sweepAngle: Number<br/> useCenter: Boolean|-|-|绘制扇形。(x,y)为左上角坐标，(w,h)为扇形宽高，startAngle为开始角度，sweepAngle为覆盖角度, useCenter为是否覆盖完整扇形面积（默认为false）|
|8|drawText|text: String/<a href="#styled_string">StyledString<a/>/<a href="#unicode">Unicode<a/> <br/> x: Number<br/> y:Number|-|-|绘制文本|
|9|drawImage|image: String/<a href="#image">Image</a> <br/> x: Number<br/> y: Number<br/> w: Number<br/> h: Number|-|-|绘制图片，支持本地图和Image对象|


### b. 画笔属性API

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|----|
|1|color|color: Number|-|-|设置画笔颜色|
|2|alpha|alpha: Number|-|-|设置画笔透明度|
|3|strokeWidth|w: Number|-|-|设置画笔粗细|
|4|style|style: <a href="#paint_style">PaintStyle</a>|-|-|设置画笔填充样式|
|5|textSize|size: Number|-|-|设置文本字体大小|
|6|font|name: String|-|-|设置字体名称|
|7|bold|bold: Boolean|-|-|设置是否粗体|
|8|resetPaint|-|-|-|重置画笔所有属性|


### c. 画布变换API

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|translate|dx: Number<br/> dy: Number|-|-|位移变换，dx为x轴移动距离，dy为y轴移动距离|
|2|scale|sx: Number<br/> sy: Number|-|-|缩放变换，sx为x轴缩放比率，sy为y轴缩放比率|
|3|rotate|r: Number<br/> x: Number <br/> y: Number|-|-|旋转变换，r为角度；(x,y) 坐标（可选）|
|4|skew|x: Number<br/> y: Number<br/>|-|-|斜切变换，xy斜切比率|


### d. 其它API

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|nativeObj|-|native canvas|-|获取对应的native对象|
|2|save|-|-|-|保存当前画布状态|
|3|restore|-|-|-|恢复当前画布状态|
|4|clipRect|left: Number<br/> top: Number<br/> right: Number<br/> bottom: Number|-|-|裁剪矩形区域|
|5|size|-|w, h|-|获取画布尺寸|

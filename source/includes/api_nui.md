# API-NUI

## Http

> Http

```
Http({
	"method": "POST",
	"params": {
		"k1": "v1",
		"k2": "v2"
	}
}, function(response)
	print("called success")
end)


http = Http()
http.get("http://luaview.github.io", {
    query = 1
}, function(response)
	print("called success")
end)
```


<aside class="notice" id="nhttp">
网络请求组件。
</aside>


Http(initParams, callback)

* initParams: LuaTable，请求参数
	* method: String, 请求方法
	* params: LuaTable, 请求业务参数
* callback: LuaFunction, 回调
	* 返回参数response为LuaTable
	* response.data() 得到 Data数据

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|url|v: String|v|-|设置请求Url|
|method|v: String, get/post|v|-|设置请求方法|
|retryTimes|v: Number|v|-|重试次数|
|timeout|v: Number|v|-|超时时间|
|params|v: LuaTable|v|-|请求参数|
|callback|v: LuaFunction|v|请求回调|
|request|-|-|-|请求|
|cancel|-|-|-|中止|
|get|url: String<br/> params: LuaTable<br/> callback: LuaFunction|-|-|GET请求|
|post|url: String<br/> params: LuaTable<br/> callback: LuaFunction|-|-|POST请求|

## Timer

<aside class="notice" id="timer">
定时器组件。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|delay|v: Number|v|-|启动延时|
|repeat|v: Number|v|-|重复次数|
|repeatCount|v: Number|v|-|重复次数|
|interval|v: Number|v|-|重复间隔|
|start|v: Number|v|-|启动|
|callback|v: LuaFunction|v|-|回调|
|cancel|-|-|-|取消|

## System

<aside class="notice" id="system">
系统信息组件，静态。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|ios|-|v: Boolean|-|是否iOS平台|
|android|-|v: Boolean|-|是否Android平台|
|vmVersion|-|v: String|-|LuaView版本|
|osVersion|-|v: String|-|操作系统版本|
|platform|-|v: String|-|平台系统型号|
|scale|-|v: Number|-|屏幕缩放比|
|device|-|v: LuaTable|-|设备信息|
|screenSize|-|w: Number<br/> h: Number|-|屏幕尺寸|
|network|-|v: String|-|网络类型("none", "2g", "3g", "4g", "wifi", "unknown")|
|gc|-|-|-|执行内存回收|
|keepScreenOn|v: Boolean|-|-|是否保持屏幕常亮|

## AudioPlayer

<aside class="notice" id="audio_player">
音频播放器组件。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|play|name: String<br/> times: Number|-|-|播放（uri，重复次数）|
|pause|-|-|-|暂停播放|
|resume|-|-|-|恢复播放|
|stop|-|-|-|停止播放|
|seekTo|sec: Number|-|-|到某个位置|
|callback|v: LuaFunction|v|-|回调|
|playing|-|v: Boolean|-|是否播放|
|pausing|-|v: Boolean|-|是否暂停|
|looping|-|v: Boolean|-|是否循环播放|

## Vibrator

> Vibrator

```
local vibrator = Vibrator()

vibrator.vibrate() -- 默认震动

vibrator.vibrate(2) -- 震动两次

vibrator.vibrate({1, 2, 1, 0.3, 0.2, 0.1, 0.01, 1.1}, 4) -- 特殊震动模式
```


<aside class="notice" id="vibrator">
震动组件。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|hasVibrator|-|v: Boolean|-|是否有震动硬件|
|vibrate|mode: Number[], repeatTimes: Number|-|-|震动(模式，次数)|
|cancel|-|-|-|取消震动|


## Unicode

> Unicode

```
Unicode(0xe607)
```


<aside class="notice" id="unicode">
unicode组件。
</aside>

Unicode(char)

* char 为Unicode字符编码


## Data

> Data

```
Data("a")

Data(97, "abc", "def")

Data('{"a":"1"}')

Data('a').toString("latin-1")

Data('{"a":"1"}').toTable()

Data('{"a":"1"}').toJson()
```

<aside class="notice" id="data">
二进制数据组件。
</aside>

Data(str)

* str: String/JsonString

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|append|v: Data/byte[]|-|-|新增部分数据|
|toString|code: String|v: String|-|转成String(编码格式)|
|toJson|-|v: String|-|转成Json String|
|toTable|-|v: LuaTable|-|转成LuaTable|

## Json

<aside class="notice" id="json">
Json组件，静态。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|toTable|v: String/<a href="#data">Data</a>/LuaTable|r: LuaTable|-|给定内容转成LuaTable|
|isValid|v: String/<a href="#data">Data</a>|r: Boolean|-|是否有效JsonString|


## Downloader
<aside class="notice" id="downloader">
下载器组件，静态。
</aside>

|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|fetch|url: String<br/> name: String<br/> callback: LuaFunction|-|-|TODO|

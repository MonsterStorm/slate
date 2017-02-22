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

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|url|v: String|v|-|设置请求Url|
|2|method|v: String, get/post|v|-|设置请求方法|
|3|retryTimes|v: Number|v|-|重试次数|
|4|timeout|v: Number|v|-|超时时间|
|5|params|v: LuaTable|v|-|请求参数|
|6|callback|v: LuaFunction|v|请求回调|
|7|request|-|-|-|请求|
|8|cancel|-|-|-|中止|
|9|get|url: String<br/> params: LuaTable<br/> callback: LuaFunction|-|-|GET请求|
|10|post|url: String<br/> params: LuaTable<br/> callback: LuaFunction|-|-|POST请求|

## Timer

<aside class="notice" id="timer">
定时器组件。
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|delay|v: Number|v|-|启动延时|
|2|repeat|v: Number|v|-|重复次数|
|3|repeatCount|v: Number|v|-|重复次数|
|4|interval|v: Number|v|-|重复间隔|
|5|start|v: Number|v|-|启动|
|6|callback|v: LuaFunction|v|-|回调|
|7|cancel|-|-|-|取消|

## System

<aside class="notice" id="system">
系统信息组件，静态。
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|ios|-|v: Boolean|-|是否iOS平台|
|2|android|-|v: Boolean|-|是否Android平台|
|3|vmVersion|-|v: String|-|LuaView版本|
|4|osVersion|-|v: String|-|操作系统版本|
|5|platform|-|v: String|-|平台系统型号|
|6|scale|-|v: Number|-|屏幕缩放比|
|7|device|-|v: LuaTable|-|设备信息|
|8|screenSize|-|w: Number<br/> h: Number|-|屏幕尺寸|
|9|network|-|v: String|-|网络类型("none", "2g", "3g", "4g", "wifi", "unknown")|
|10|gc|-|-|-|执行内存回收|
|11|keepScreenOn|v: Boolean|-|-|是否保持屏幕常亮|

## AudioPlayer

<aside class="notice" id="audio_player">
音频播放器组件。
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|play|name: String<br/> times: Number|-|-|播放（uri，重复次数）|
|2|pause|-|-|-|暂停播放|
|3|resume|-|-|-|恢复播放|
|4|stop|-|-|-|停止播放|
|5|seekTo|sec: Number|-|-|到某个位置|
|6|callback|v: LuaFunction|v|-|回调|
|7|playing|-|v: Boolean|-|是否播放|
|8|pausing|-|v: Boolean|-|是否暂停|
|9|looping|-|v: Boolean|-|是否循环播放|

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

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|hasVibrator|-|v: Boolean|-|是否有震动硬件|
|2|vibrate|mode: Number[], repeatTimes: Number|-|-|震动(模式，次数)|
|3|cancel|-|-|-|取消震动|


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

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|append|v: Data/byte[]|-|-|新增部分数据|
|2|toString|code: String|v: String|-|转成String(编码格式)|
|3|toJson|-|v: String|-|转成Json String|
|4|toTable|-|v: LuaTable|-|转成LuaTable|

## Json

<aside class="notice" id="json">
Json组件，静态。
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|toTable|v: String/<a href="#data">Data</a>/LuaTable|r: LuaTable|-|给定内容转成LuaTable|
|2|isValid|v: String/<a href="#data">Data</a>|r: Boolean|-|是否有效JsonString|


## File

> File

```
http = Http()
http.get("http://luaview.github.io", {
    query = 1
}, function(response)
  local data = response:data()

	-- 保存
	File.save(data, "test.html") -- 同步存
	File.save(data, "test.html", function(status)
		-- 异步存
	end)

	-- 读取
	data = File.read("test.html") -- 同步读
	File.read("test.html", function(data)
		-- 异步读取
	end)

	-- 存在判断
	print(File.exists("test.html"))

	-- 文件路径
	print(File.path("test.html"))
end)
```

<aside class="notice" id="file">
文件操作组件，静态。
</aside>
|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|save|path: String<br/> data: <a href="#data">Data<a/> <br/> callback: LuaFunction or <br/> data: <a href="#data">Data<a/> <br/> path: String<br/> callback: LuaFunction|-|-|保存data内数据到path指定的文件内，文件名支持子目录或者上级目录|
|2|read|path: String<br/> callback: LuaFunction|<a href="#data">Data</a>|-|读取给定path的文件，并返回Data数据，支持异步读取，异步返回数据通过callback返回|
|3|exists|path: String|-|-|文件是否存在|
|4|path|name: filename|path:String|-|获取给定文件名的绝对存储路径|

## Downloader
<aside class="notice" id="downloader">
下载器组件，静态。
(Deprecated 所有功能可以通过<a href="#http">Http</a> and <a href="#file">File</a>完成)
</aside>

|ID|API|参数|返回值|平台|备注|
|----|----|----|----|----|----|
|1|fetch|url: String<br/> name: String<br/> callback: LuaFunction|-|-|TODO|

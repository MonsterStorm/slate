# API-LuaView

<aside class="notice" id="luaview">
LuaView是外部使用LuaView的唯一主入口
</aside>

> LuaView 使用 -Android

```
1. 创建LuaView
LuaView luaview = LuaView.create(getContext());

2. 注册扩展
luaview.registerPanel(CustomLoading.class);
luaview.register("bridge", new CustomBridge());

3. 加载资源
luaview.load("脚本uri");

如：
本地, luaview.load("main.lua"); //加载 assets下的main.lua
网络, luaview.load("http://luaview.github.com/test.zip"); //加载 网络资源test.zip，LuaView会自行下载并解压执行

```


|API|参数|返回值|平台|备注|
|----|----|----|----|----|
|create|context: Context|LuaView|Android|创建LuaView|
|createAsync|context: Context, callback: CreatedCallback|-|Android|异步创建LuaView|
|load|url: String|LuaView|Android|加载指定资源（asset、本地、网络）|
|load|url: String, callback: ScriptExecuteCallback|LuaView|Android|加载指定资源（asset、本地、网络），带回调|
|loadScript|script: String|LuaView|Android|加载指定脚本|
|loadScript|script: String, callback: ScriptExecuteCallback|LuaView|Android|加载指定脚本，带回调|
|loadScriptBundle|scriptBundle: ScriptBundle|LuaView|Android|加载指定脚本包|
|loadScriptBundle|scriptBundle: ScriptBundle, callback: ScriptExecuteCallback|LuaView|Android|加载指定脚本包，带回调|
|loadScriptBundle|scriptBundle: ScriptBundle, main_entry: String, callback: ScriptExecuteCallback|LuaView|Android|加载指定脚本包，执行main_entry入口文件，带回调|
|register|name: String, bridge: Object|LuaView|Android|注册一个名称为name的bridge对象|
|unregister|name: String|LuaView|Android|反注册一个名称为name的bridge对象|
|registerPanel|clazz: Class<? extends LVCustomPanel>|LuaView|Android|注册一个名称为clazz类名，类型为clazz的panel|
|registerPanel|name: String, clazz: Class<? extends LVCustomPanel>|LuaView|Android|注册一个名称为name，类型为clazz的panel|
|registerLibs|binders: LuaValue[]|LuaView|Android|注册自定义库|
|registerImageProvider|clazz: Class<? extends ImageProvider>|LuaView|Android|注册一个ImageProvider|
|getImageProvider|-|provider: ImageProvider|Android|获取ImageProvider|
|callLuaFunction|funName: String, params: Object[]|result: Object|Android|调用lua的某个全局函数|
|callWindowFunction|funName: String, params: Object[]|result: Varargs|Android|调用window.callback下的某个函数|
|getUri|-|uri: String|Android|获取当前LuaView加载的Uri|

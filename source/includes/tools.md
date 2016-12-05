# Tools for LuaView

## 1. LuaViewDegbugger
	LuaViewSDK 的lua代码调试器

## 2. LuaViewBytecodeCompiler


* LuaViewBytecodeCompiler用于将LuaView的源码预编译成Lua bytecode。加速LuaViewSDK for Android的执行
* 该工具编译出来的bytecode代码只能用于Android端，暂时不能用于iOS端


### Usage

1. 创建项目普通Java项目ProjA
2. 引入jar包
3. 使用jar包提供的函数对lua代码进行打包(LuaViewBytecodeCompiler类)
	* A：public static byte[] compile(byte[] source, String filename) throws Exception
		* 将一个源码的二进制流编译成lua bytecode二进制流
	* B：public static void compile(String filePath) throws Exception
		* 将给定代码地址的代码编译成lua bytecode并保存在同目录下，文件名为*.luap
4. 在Android项目直接使用编译好的bytecode，功能同load函数
	* luaView.loadPrototype(final InputStream inputStream, final String name, final LuaScriptLoader.ScriptExecuteCallback callback)

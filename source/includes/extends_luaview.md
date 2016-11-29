# Extends LuaView

## Scenarios

虽然LuaView包含了常用的大部分控件，但是开发者有自己的定制需求，这些定制需求可以大致分为以下几种情况

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

开发者A，在自己的项目中，有统一的Native Loading UI，在 lua 中写的页面或UI组件中也需要使用该Loading UI。为了避免重复开发已有功能，LuaView 支持将现有功能通过简单封装，桥接到 lua 层，赋予该 Native UI 与 lua 互操作的能力。既可以在 lua 中创建出该UI，也可以操作该UI，改变其状态或功能，也可以在在该 Native UI 中调用相应的 lua 代码。

<br/>
`扩展方式大概分为以下几步：`


> CustomPanel - Android

```
1. 继承LVCustomPanel

public class CustomLoading extends LVCustomPanel {

    public CustomLoading(Globals globals, LuaValue metaTable, Varargs varargs) {
        super(globals, metaTable, varargs);
    }

    @Override
    public void initPanel() {
        //TODO 在这里创建Native UI
    }
}

2. 实现initPanel方法，创建Native UI，并添加的CustomPanel里

@Override
public void initPanel() {
    //创建Native UI
    final View customLoading = new NativeLoading(getContext());
    LayoutParams layoutParams = LuaViewUtil.createRelativeLayoutParamsWW();
    layoutParams.addRule(RelativeLayout.CENTER_IN_PARENT);
    customLoading.setVisibility(View.VISIBLE);

    //添加到CustomPanel里
    addView(customLoading, layoutParams);
}

3. Native调用Lua

@Override
public void initPanel() {
    //创建Native UI
    final View customLoading = new NativeLoading(getContext());

    //添加View...

    //绑定事件
    customLoading.setOnClickListener(new View.OnClickListener(){
      @Override
      public void onClick(View v) {
        //1. 调用该View的回调，params为函数参数，类型为Object...
        callLuaCallback(params);

        //2. 调用脚本的全局方法，params为函数参数，类型为Object...
        callLuaFunction("globalFun", params);
      }
    });
}

4. LuaView注册CustomPanel

luaview.registerPanel(CustomLoading.class)

或者

luaview.registerPanel("新名称(默认是类名称)", CustomLoading.class)

5. Lua代码

-- 在Lua代码中直接创建CustomPanel对象
local loading = CustomLoading()
loading.frame(0, 0, 100, 100)

loading.callback(function()
  -- Native UI调用该函数
end)

function globalFun(param1, param2)
  -- Native UI调用该函数
end

```

### a. 扩展CustomPanel

  在LuaView中有一个CustomPanel组件，用于将已有的Native UI组件进行包装。开发者可以通过扩展CustomPanel来实现现有组件复用。

### b. 实现initPanel()方法

  在initPanel里面创建Native UI组件，并添加到CustomPanel中。
  CustomPanel本身实际上是一个Android的ViewGroup, 所创建的Native UI是该ViewGroup的子View

### c. Native UI 中绑定事件，以便调用 Lua 代码

  在Native UI中事件发生时，通过调用对应脚本的Lua函数，来实现相互通信。目前有两种调用方式
  * 一种是调用脚本的全局方法
  * 一种是调用CustomPanel的Callback方法

### d. 注册CustomPanel到LuaView

  写好CustomPanel以后，就可以在LuaView启动的时候注册对应的CustomPanel。使用函数registerPanel()

### e. 在Lua中使用CustomPanel

  注册好的CustomPanel，可以在Lua脚本中直接使用，且有View的所有方法，包含容器方法









## 2. native-lua 互操作

开发者A有部分功能需要在Lua中使用，如判断是否登陆，页面跳转等逻辑。

<br/>
`扩展方式大概分为以下几步：`

> Bridge - Android

```
1. 书写Bridge函数

public class LuaViewBridge {
    private Activity mActivity;

    public LuaViewBridge(Activity activity) {
        this.mActivity = activity;
    }

    //页面跳转
    public void openPage(String pageUri){
        Intent intent = new Intent();
        intent.setData(Uri.parse(pageUri));
        mActivity.startActivity(intent);
    }

    //判断是否登陆
    public boolean isLogin(){
        return true;
    }
}

2. 注册Bridge

luaview.register("bridge", new LuaViewBridge())

3. Lua中使用

-- open page
bridge.openPage("http://luaview.github.io")

-- 判断是否login
local isLogin = bridge.isLogin()

```

### a. 创建Bridge
  在Android中，LuaView的Bridge就是一个简单的Object，任何Object都可以，创建出该Object，注册到LuaView即可实现lua操作Native。

### b. 注册Bridge
  使用LuaView.register("bridge", new LuaViewBridge())注册一个bridge对象。

### c. Lua中使用
  创建出来的bridge可以在lua中直接使用，支持所有基本类型互传。









## 3. 使用自己的图片库
  默认LuaViewSDK使用Glide图片库，第三方可以通过实现ImageProvider来自接入自定义的图片库

  <br/>
  `扩展方式大概分为以下几步：`

> 自定义图片库 - Android

```
1. 实现ImageProvider接口
public class CustomImageProvider implements ImageProvider {
  /**
   * 下载图片
   * @param imageView
   * @param url
   * @param callback
   */
  void load(final Context context, final WeakReference<BaseImageView> imageView, final String url, final WeakReference<BaseImageView.LoadCallback> callback);

  /**
   * 预下载图片
   * @param context
   * @param url
   * @param callback
   */
  void preload(final Context context, final String url, final BaseImageView.LoadCallback callback);

  /**
   * pause all requests
   * @param context
   */
  void pauseRequests(final ViewGroup view, final Context context);

  /**
   * resume all requests
   * @param context
   */
  void resumeRequests(final ViewGroup view, final Context context);
}

2. 注册ImageProvider

luaview.registerImageProvider(CustomImageProvider.class)
```

### a. 自定义CustomImageProvider，实现ImageProvider接口
  自定义一个ImageProvider，实现对应的方法。

### b. 注册ImageProvider
  使用LuaView.registerImageProvider()注册Provider。






## 4. 扩展完整组件
  某些情况下，开发者想要自己实现一整套组件，然后在lua中使用，或者想要覆盖SDK里的内置组件。如，开发者A想要开发一个组件CustomButton组件，在lua中直接使用；或A想要使用自定义的native Button，而非SDK里的Button组件。

  <br/>
  `扩展方式大概分为以下几步：`

> 扩展完整组件 - Android

```
1. 创建Binder

public class CustomButtonBinder extends BaseFunctionBinder {

    public CustomButtonBinder() {
      //在这里指定名称
    }

    @Override
    public Class<? extends LibFunction> getMapperClass() {
      //TODO 在这里指定方法列表 return CustomButtonMethodMapper.class;
    }

    @Override
    public LuaValue createCreator(LuaValue env, LuaValue metaTable) {
      // Userdata 对象        
    }
}

2. 指定名称、方法映射表、Lua userdata

  a. 指定名称：
  public CustomButtonBinder() {
    super("CustomButton"); //名称为CustomButton
  }

  b. 指定方法列表
  @Override
  public Class<? extends LibFunction> getMapperClass() {
    return CustomButtonMethodMapper.class; //方法列表为CustomButtonMethodMapper类对应的所有方法
  }

  c. Lua userdata
  @Override
  public LuaValue createCreator(LuaValue env, LuaValue metaTable) {
      return new BaseVarArgUICreator(env.checkglobals(), metaTable, getMapperClass()) {//这里使用的UICreator，对应的有BaseVarArgCreator、BaseVarArgUICreator
          @Override
          public ILVView createView(Globals globals, LuaValue metaTable, Varargs varargs) {
              return new CustomButton(globals, metaTable, varargs);
          }
      };
  }


3. 实现 CustomButton，实现 ILVView接口，如果是ViewGroup的话，实现ILVViewGroup接口

public class CustomButton extends Button implements ILVView {
    private UDView mLuaUserdata;

    public CustomButton(Globals globals, LuaValue metaTable, Varargs varargs) {
        super(globals.getContext());
        this.mLuaUserdata = new UDCustomButton(this, globals, metaTable, varargs);
    }

    @Override
    public UDView getUserdata() {
        return mLuaUserdata;
    }
}

4. 实现UDCustomButton，继承自UDView，如果是ViewGroup的话，继承UDViewGroup

public class UDCustomButton extends UDTextView<Button> {
    public UDButton(Button view, Globals globals, LuaValue metatable, Varargs initParams) {
        super(view, globals, metatable, initParams);
    }
}

5. 实现CustomButtonMethodMapper，通过继承不同的MethodMapper来复用已经定义好的方法

@LuaViewLib
public class CustomButtonMethodMapper<U extends UDCustomButton> extends UITextViewMethodMapper<U> {

    private static final String TAG = CustomButtonMethodMapper.class.getSimpleName();
    private static final String[] sMethods = new String[]{
            "customMethod"
    };

    @Override
    public List<String> getAllFunctionNames() {
        return mergeFunctionNames(TAG, super.getAllFunctionNames(), sMethods);
    }

    @Override
    public Varargs invoke(int code, U target, Varargs varargs) {
        final int optcode = code - super.getAllFunctionNames().size();
        switch (optcode) {
            case 0:
                return customMethod(target, varargs);
        }
        return super.invoke(code, target, varargs);
    }

    public LuaValue customMethod(U view, Varargs varargs) {
        //获取参数 varargs.arg(2), 参数从2开始，1的位置是self。具体使用参见SDK实现
        //set方法返回view本身，用于链式调用，get方法返回函数调用值
    }
}

6. 注册CustomButton

luaview.registerLibs(new CustomButtonBinder()))

7. lua调用

local btn = CustomButton()
btn.frame(0, 0, 100, 100)
btn.text("自定义按钮")
btn.customMethod()

```

### a. 创建Binder

  binder用于将native功能绑定到lua中，定义了在lua中的名称、方法映射表、对象。
  通过继承BaseFunctionBinder可以创建一个Binder

### b. 指定名称、方法映射表、Lua userdata

  * 名称：是在Lua中使用的直接名称，如Button
  * 方法映射表：是该lua对象拥有的native-lua方法列表，是该组件的完整api列表
  * lua实体：是lua中对象的实体，是一个Userdata

### c. 实现CustomButton
  CustomButton是自定义的Button组件，为了跟Lua进行交互，需要在其内部绑定一个Lua对象。可以通过实现ILVView或者ILVViewGroup接口，实现对应接口来完成。

### d. 实现UDCustomButton
  UDXXX是Lua中的Userdata对象，自定义的Userdata可以继承UDView或者UDViewGroup来扩展功能

### e. 实现CustomButtonMethodMapper
  MethodMapper是Native-Lua方法的映射表，如果想要复用以后的方法表，可以通过继承对应的MethodMapper来实现，如View的话继承LVViewMethodMapper，ViewGroup的话继承LVViewGroupMethodMapper。

### f. 注册CustomButton
  使用luaview.registerLibs()来实现

### g. lua调用
  注册好后，可以直接在lua代码中使用自定义的库

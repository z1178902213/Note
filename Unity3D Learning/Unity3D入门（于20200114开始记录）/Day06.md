# 延时调用

* 使用invoke()方法实现延时调用，传入方法名称和延时时间。
* invoke非并发，应该是有一个计时器，每次刷新帧的时候都会检查计时器是否到达相应的值，到达后才会触发。invoke详细可以查看官网文档monobehaviour。

# 脚本间传递参数

### 对象传递

1. GameObject.Find()找到游戏对象

2. 用getcomponent()找到游戏对象的脚本组件

3. 调用脚本组件的方法

### 消息调用

1. 找到游戏对象
2. 对象.SendMessage("方法", 参数)；

* sendmessage方法原理：
  1. 遍历该对象上的所有monoBehaviour组件
  2. 检查该组件有没有对应方法
  3. 若有则执行

# User Interface

### Canvas画布，其他UI都建立在画布下即可

# UI事件处理

* 添加OnClick组件，然后将主控脚本添加进去，并选择相应方法，方法要求public且void且无参数。
* 如果想取得其他控件的内容，可以在脚本中定义相应控件，并在inspector中选择相应的控件。

# UI布局

防止比例放缩的时候产生的不兼容形变，rect transform中可以调整，没必要自己写代码。。。so easy

panel组件可以盛放其他组件。
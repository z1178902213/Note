# 坐标（续）

1. 空间坐标
   * transform.position就是对象的空间坐标
2. 屏幕坐标

* 屏幕像素高度：Screen.height

* 屏幕像素宽度：Screen.width

* 注：像素高度、宽度主要是看屏幕的实际大小，而不是分辨率。

* 屏幕坐标横轴X轴，纵轴是Y轴。坐标原点在屏幕左下方。**屏幕坐标单位是像素**。

  可以用过使用API调用屏幕坐标，具体代码如下所示：

  ```
  Vector3 worldPosition = transform.position;
  Vector3 screenPositon = Camara.main.WorldToScreen(worldPosition); //Camara.main表示主摄像机。
  ```

  

# 鼠标事件处理

unity3D中，对于鼠标事件的处理有3、4种方式，这里先介绍一种最常用的。

UP主没讲。

# 事件函数

事件函数执行时的详细顺序：https://docs.unity.cn/cn/2019.4/Manual/ExecutionOrder.html

笼统来讲，事件函数执行顺序：Awake() -> OnEnable() -> Start()。

* 当脚本组件被禁用的时候，Awake()还是会被调用，但Start()不会被调用
* Start()只会被调用一次
* OnEnable()在每次启动时调用
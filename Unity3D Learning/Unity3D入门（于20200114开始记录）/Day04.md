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

``` C#
Input.GetMouseButtonDown(0);//检测鼠标是否有按下。
```



# 脚本事件函数

事件函数执行时的详细顺序：https://docs.unity.cn/cn/2019.4/Manual/ExecutionOrder.html

笼统来讲，事件函数执行顺序：Awake() -> OnEnable() -> Start()。

* 当脚本组件被禁用的时候，Awake()还是会被调用，但Start()不会被调用
* Start()只会被调用一次
* OnEnable()在每次启动时调用

# 脚本执行顺序

* 脚本执行顺序和hierarchy层级顺序无关
* 在脚本的inspector中，可以找到execution Order...，在里面可以调整脚本执行的顺序。
* 也可以在菜单栏edit -> project setting -> script execution order
* 在此处可以设置脚本执行顺序

# 预制件Prefab

定义：Unity 的**预制件**系统允许创建、配置和存储游戏对象及其所有组件、属性值和子游戏对象作为可重用资源。

作用：预制件资源充当模板，在此模板的基础之上可以在场景中创建新的预制件实例。

使用场景：如果要在场景中的多个位置或项目中的多个场景之间重用以特定方式配置的游戏对象，比如非玩家角色 (NPC)、道具或景物，则应将此游戏对象转换为预制件。这种方式比简单复制和粘贴游戏对象更好，因为预制件系统可以自动保持所有副本同步。

* 将已经创建好的在hierarchy中的游戏对象拖动到project中，就会生成一个预制体。

# 预制件动态创建与销毁

1. 首先应该设置好将要被创建的预制件的属性，包括脚本。
2. 使用方法Instantiate(GameObject prefab);来创建一个预制件，该方法会返回一个GameObject实例。
3. 可以使用GameObject.Desttoy(this.gameObeject);来销毁一个游戏对象，该游戏对象可以是一个预制件。

# 定时器

* 可以使用Time.deltaTime，对每次update的时间间隔进行累计，当达到某一个时间的时候触发一个定时事件，并清空计时器。

# 键盘事件

* Input.GetKeyDown(key) 键盘按下事件
* Input.GetKeyUp(key) 键盘抬起事件
* Input.GetKey(key) 检查某键是否被按下。
* key可以用 变量KeyCode.xxx

# 物理系统

* 为对象添加一个刚体组件可以产生物理系统。2D游戏添加2D的刚体组件RigidBody2D。
* 刚体有三种类型：
  1. Dynamic 动态刚体，有质量，有速度
  2. Static 静态刚体，质量无穷大，无速度（适用于建筑物、地面等不动的物体）
  3. Kinematic 运动学刚体，无质量（忽略物理规律，常用于碰撞检测）
* 在加入collider组件（Box Collider 2D）之后，对象之间才会产生碰撞的效果。在点击了Edit Collider之后，可以对碰撞体的碰撞范围形状进行约束，常见碰撞形状有：
  1. 方形 Box Collider 2D
  2. 圆形 Circle Colliser 2D
  3. 不规则边缘 Edge Collier 2D
  4. 胶囊形状 Capsule Collier 2D
* 刚体反弹：为了让刚体能够反弹，需要添加一个物理材质(Physical Material 2D)，物理材质上面可以修改弹性系数。

# 参考文献：

1. Unity2020入门教程 2D/3D游戏开发课程_90集视频：https://www.bilibili.com/video/BV1WK411V7dn
2. unity3D官方手册：https://docs.unity.cn/cn/2019.4/Manual/Prefabs.html
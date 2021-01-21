# 2D下摄像机的几个参数

1. Z坐标默认为-10。
2. background为背景色。
3. size为摄像机宽度的一半。当size为5时，摄像机的宽度应该为10个单位。

# 游戏对象的操作

1. 在inspector里可以勾选active复选框
2. 可以将Game的长宽比设置成16:9。
3. Additional Settings. Order In Layer 属性可以设置对象的显示层级，也可以直接设置Z坐标。
4. pivot是图片旋转的轴心，点击对象的sprite editor可以对轴心进行修改。

# 2D图片素材

1. 背景图片：一般为JPG
2. 人物、道具等其他图片一般为PNG，背景透明
3. 如果图片素材中有多个图形，可以在素材的sprite mode选项中将其设置成multiple并执行sprite editor，执行slice可以将图片分割成多个。

# 组件

1. **sprite renderer** **图片渲染器**：可以用于显示一个sprite
2. **transform组件**（基本组件，无法删除）：形状变化的组件

# C#脚本

1. 可以使用debug.log("");用于输出文字等信息。

2. 所有unity脚本都继承monobehavior这个类

3. 创建脚本后悔自动创建start和update方法。update方法会在每一帧调用一次。

4. time.deltatime获取上一帧到现在的时间

5. 可以通过设置Application.tarfetFrameRate来调节程序运行时的帧率。

6. this.transform.translate()方法，可以设置XYZ的值，让对象产生相对位移。

   > 当上述方法在update()中调用时，由于每次的帧间隔时间不同，因此可能导致移动不匀速，因此可以用一个变量对帧间隔进行相乘控制移动保持匀速。如：
   >
   > float step = 0.8f * time.DeltaTime;

7. 可以使用this.gameObject.GetComponent<>();获取当前对象的某个组件。不写this.gameObject也行。

8. 可以使用GameObject的find方法来找到其他对象。

   如：GameObject obj = GameObject.Find("/aaa");

9. 在脚本中，定义一个public的变量，可以显示在unity界面的脚本窗口里。

# 脚本调试方法

1. VS中设置断点
2. VS中附加到unity
3. unity中play，随后便可以在断点开始调试。

# 坐标

1. 节点的坐标、旋转都是vector3表示的。
   * 世界坐标 position
   * 相对坐标 localposition
2. 节点的位置用position表示，节点的旋转角度用eulerAngles表示
   * 绝对旋转 eulerangles
   * 相对旋转 localeulerangles
   * 也可以用rotate旋转
3. 当调用位移方法transform.translate()时的第四个参数Space.self（默认）表示对象朝着自己的坐标方向前进。当要沿着世界坐标轴方向前进时，需要将第四个参数修改成Space.World。
4. 移动到达边界可以通过判断transform的position和摄像机的摄像范围进行比较从而进行调头。


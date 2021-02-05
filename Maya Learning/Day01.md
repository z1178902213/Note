* 空格键进行三视图和透视图的切换
* alt加鼠标进行旋转、平移、放缩
* 选择的时候按住shift键可以多选
* Ctrl + D可以直接复制一个对象出来，将新对象移动后按shift + D可以批量等距离复制。
* w选择物体之后，按下D键可以对物体的中心进行拖拽，按住X可以吸附网格。
* shift再框选可以进行反选。
* 可以将摄像机之外的面移除进行场景优化。

# 特殊复制

### 旋转复制

可以对物体进行批量的可调整角度地复制。例如，让物体围绕一个中心，等间距或等角度地复制多个相同的物体出来。要用到特殊复制。

要复制出下图样式，具体操作如下：

![image-20210123102401330](C:\Users\Cheung\AppData\Roaming\Typora\typora-user-images\image-20210123102401330.png)

1. 创建一个正方体，利用“移动工具”将正方体移动到离原点5格外的位置（可以按住X键就行吸附网格拖拽）。
2. 按下D键，可以对物体的中心进行移动，将物体的中心移动到原点位置（同样的按住X键可以吸附网格）。要想让物体中心还原，就到菜单栏中的“修改”中选择“居中枢轴“。
3. 在编辑（edit）中选择特殊复制右侧的□可以打开“特殊复制选项”。在“特殊复制选项”中，“几何体类型”选择“复制”，“下方分组”选择“父对象”，在旋转中，将Y轴设置为60，因为我们要的这个图形是绕Y轴旋转复制得到的。复制的数量选择5。
4. 点击应用就可以得到图示图形。

### 关联复制

可以用于得到对称的物体，其步骤是：切割，删除，对称复制，其核心思想在于镜像复制，复制以后可以只设置一侧，另一侧也会跟着动。样例图如下，以下为具体操作：

![image-20210123103945633](C:\Users\Cheung\AppData\Roaming\Typora\typora-user-images\image-20210123103945633.png)

1. 创建一个正方形，现要对正方形进行对称设计，首先将正方形切割成两个部分。长按右键选择线，找到相应的线之后，按住Ctrl再按住鼠标右键，选择“环形边工具” -> “到环形边再分割”，此时可以将正方形分割成两个部分。
2. 右键选择面，切换到选择工具选中一侧将其删除。
3. 然后在“特殊复制选项”中，“几何体类型”中选择“实例”，“规模“中在对应的轴设置成-1，然后应用，就能得到对称的物体。**对一侧进行操作，另一侧也会跟着动，这就是所谓的”关联“。**
4. （实践发现，在右键选择了点、线、面后对物体进行操作才会关联操作，若是对象模式，就不会对物体进行关联操作）

# 几何对象的显示模式

显示模式包含在菜单栏中的“显示”、”着色”等中。

1. 快捷键1表示，显示为粗糙纹理的几何体。
2. 快捷键2表示，显示为中等几何体，包括了粗糙纹理和平滑几何体。
3. 快捷键3表示，显示为平滑纹理的几何体。
4. 快捷键4可以对几何对象进行“线框”显示。
5. 快捷键5可以对几何对象进行“着色”显示。
6. 快捷键6可以对几何对象进行“硬件渲染”显示，可以显示所选择的纹理材质。
7. 快捷键7可以进行灯光显示。

# 场景编组

按Ctrl + G可以对几何体进行编组。

# 让顶点吸附几何体的边移动

切换到“移动工具”，按住C和鼠标滚轮，进行拖拽就可以在几何体的边上移动。

切换到“移动工具”，按住V键，可以让几何体一个顶点和另一个顶点合并。

切换到“移动工具”，选择一个顶点并选中一个轴，按住V键再按下滚轮选择另一个顶点并朝所选坐标轴正方向拖动，可以让该点在同一个坐标轴上对齐。

# 添加快捷键

在菜单栏中找到要添加的，按住Ctrl+shift再单击可以添加快捷键。
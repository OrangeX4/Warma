# 介绍  
走过路过千万不要错过啊！  
这里是Warma！APP的**源 ~~玛~~ 码**。  
鬼知道我为了弄这东西解决了多少莫名其妙bugs...

# 反馈  
各位可以向[我的B站私信](https://space.bilibili.com/15329464)~~骚扰~~反馈！  

# 皮肤图片  
* [被窝玛](./app/src/main/res/drawable-xhdpi)![被窝玛](/app/src/main/res/drawable-xhdpi/awake.png)
- [蜘蛛](./aNekoSampleSkin/src/main/res/drawable)  ![蜘蛛](/aNekoSampleSkin/src/main/res/drawable/icon.png)
- [馒头](./aMantou/src/main/res/drawable)  ![馒头](/aMantou/src/main/res/drawable/y.png)
* [雪人](./aSnow/src/main/res/drawable)  ![雪人](/aSnow/src/main/res/drawable/sy1_5.png)  

**想要更多有趣的皮肤？看看下面的内容，然后提意见吧！欢迎Star + Fork + Pull Request 三连！！！**

# 新皮肤指南！ 
编辑皮肤数据  
皮肤数据由Activity的<meta-data>标签指示，该标签处理文件中的org.tamanegi.aneko.action.GET_SKIN的intend "AndroidManifest.xml".    
android:resource是对皮肤数据文件的引用。   
在示例项目中，res/xml/skin.xml是皮肤数据文件。[示例](/app/src/main/res/xml/neko.xml)   
图像存储在res/drawable*目录中。  
有关drawable的更多详细信息，请参见Android开发指南。  
皮肤数据文件如下所述以XML编写。  
皮肤数据XML格式：  
<motion-params>  
定义皮肤数据。  
这必须是根元素。包含一个或多个<motion>元素。  
acceleration  
整数。[dp / sec 2 ]  
从停止状态移动或更改移动方向的加速度。  
maxVelocity  
整数。[dp / sec]  
移动状态的最大速度。  
deaccelerationDistance  
整数。[dp]  
移动目的地和当前位置之间的阈值距离，以降低速度。当距离小于此值时，最大速度将与距离成比例地降低。  
proximityDistance  
整数。[dp]  
停止移动的目标位置与当前位置之间的阈值距离。当距离小于该值时，运动将停止。  
initialState  
字符串。  
初始状态和停止状态的名称。第一次停止移动时使用此状态。  
awakeState  
字符串。  
从停止状态开始移动状态的名称。当用户触摸处于停止状态的显示器时，将使用此状态。  
moveStatePrefix  
字符串。  
移动状态名称的前缀。状态名称将通过附加方向从该值生成。  
方向是如下的一个：Up，Down，Left，Right，UpLeft，UpRight，DownLeft，DownRight  
wallStatePrefix  
字符串。（可选）  
左边缘和右边缘状态名称的前缀。当停在显示的左边缘或右边缘时，将使用这些状态。状态名称将通过附加方向从该值生成。  
方向是如下的一个：Left，Right  
<motion>  
定义描述动画的状态。  
必须是<motion-params>element 的子元素。包含<item>和/或<repeat-item>元素。  
state  
字符串。  
此状态的名称。各状态以该名称区分和引用。  
duration  
整数。[millisec]（可选）  
此状态的持续时间。当持续时间过去时，当前状态转换为下一个状态。如果忽略此属性或设置了负值，则持续时间等于内部动画的总持续时间。  
nextState  
字符串。（可选）  
下一个状态的名称。当持续时间过去时，当前状态转换为指定状态。  
如果checkMoveand / or checkWall是trueand满足条件，则将不使用该属性值。  
checkMove  
布尔值。（可选）  
如果设置为true且需要移动时，则下一个状态为移动状态。  
详见：moveStatePrefix  
checkWall  
布尔值。（可选）  
如果设置为true并且当前位置是显示的左边缘或右边缘，则下一个状态是显示边缘状态。  
详见：wallStatePrefix  
<item>  
定义动画帧。  
必须是<motion>或的子<repeat-item>元素。  
drawable  
引用可绘制资源。  
框架的图像。  
duration  
整数。[millisec]（可选）  
此帧的持续时间。如果省略此属性或设置负值，则持续时间等于无穷大。  
<repeat-item>  
定义一帧或多帧。这些帧可以重复一次或多次。  
必须是<motion>或的子<repeat-item>元素。包含<item>和/或<repeat-item>元素。  
duration  
整数。[millisec]（可选）  
帧的持续时间。如果忽略此属性或设置了负值，则持续时间等于内部动画的总持续时间。  
repeatCount  
整数。（可选）  
重复次数。如果忽略此属性或设置了负值，则动画将重复无穷大。  

# 程序员向新皮肤指南！  
下面内容的是给想自己修改的**程序员**看的：  
```
1.下载[sample project](https://www.tamanegi.org/prog/android-apps/p/ANeko-SampleSkin-0.1.1.zip)  
2.在Android Studio里File->New->Import Module引入sample  
3.照着它说的Refactor   
4.在APP中的build.gradle中android节点加入 dependencies {implementation project(':模块名')}   
5.在模块中的build.gradle中把apply plugin: 'com.android.application'换成apply plugin: 'com.android.library'  
6.在模块中的build.gradle中把各种version与app中的保持一致  
7.在模块中的build.gradle中把applicationId "com.example.aneko.sample"删去或者注销掉  
8.修改res中的图像文件，然后build+run即可！    
```

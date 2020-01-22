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

# 大众向新皮肤指南！


# 程序员向新皮肤指南！  
下面内容的是给想自己修改的**程序员**看的：  
1.下载[sample project](https://www.tamanegi.org/prog/android-apps/p/ANeko-SampleSkin-0.1.1.zip)  
2.在Android Studio里File->New->Import Module引入sample  
3.照着它说的Refactor   
4.在APP中的build.gradle中android节点加入 dependencies {implementation project(':模块名')}   
5.在模块中的build.gradle中把apply plugin: 'com.android.application'换成apply plugin: 'com.android.library'  
6.在模块中的build.gradle中把各种version与app中的保持一致  
7.在模块中的build.gradle中把applicationId "com.example.aneko.sample"删去或者注销掉  
8.修改res中的图像文件，然后build+run即可！    

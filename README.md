# Render Blender in google colab

<a href='https://gitee.com/bilibiliboombooom/blender-render-in-google-colab/stargazers'><img src='https://img.shields.io/badge/follow-1-yellow' alt='star'></img></a> <a href='https://gitee.com/bilibiliboombooom/dashboard/projects'><img src='https://img.shields.io/badge/MY-GIT-green' alt='star'></img></a>

Render Blender in google colab.ipynb

👇👇👇👇👇👇👇here👇👇👇👇👇👇👇👇

[Render Blender in google colab.ipynb](https://drive.google.com/file/d/1sgJP_0hn773xsi3O0t8u6Rwl13q95NOu/view?usp=sharing)

 👉[b站视频教程](https://www.bilibili.com/video/BV1BF41137rU?share_source=copy_web)👈

* [google colab](https://colab.research.google.com)
* [google drive](https://drive.google.com/)

---
``` 
更新：更新了云端英伟达驱动的更新失败的问题（2） 2022-8-4
更新：更新了云端英伟达驱动的更新失败的问题 2022-8-4
更新：更新了blender应用程序无法正常解压的问题 2022-7-14
⚠更新：更新了无法在t4环境下渲染blender 2022-5-31
更新：更新blender应用程序 2022-4-21
更新：更新了k80的渲染方法 2022-4-14
```
## 点击此处👉[跳转](#更新)到更新
---
## 声明

### 1.先说明方案无法百分百第一时间进行渲染 要看Google colab有没有第一时间分配给你 tesla t4 后端 ，``解决方法``：1.换个时间再尝试，避开高峰期。2.开colab pro。

#### 这个方案最大的缺点是无法确定每次都能百分百被分配到t4的后端gpu，简单解释就是colab有冗余gpu就分配给免费用户，没有就不分配，一般在#1刷新后端gpu10次左右发现还刷不出来，不要继续刷下去，建议去做其他事情先，等个十几分钟,二十几分钟，三十几分钟，再尝试，最后怎么样都能被分配到的，除非colab哪一天把这个免费用户可体验t4的策略换了。这个问题是被动的，免费避免不了麻烦，百分百被分配到是pro用户，参考官方文档有说明免费用户和pro的区别，你可以根据自己实际情况考虑需不需要开pro。方案不完美，只是一种途径。急用免费云渲染，这里推荐渲染农场，你帮助别人的同时别人也在帮助你。

### 2.目前不支持Eevee渲染器

### 注：方案需全程在✈的环境下进行！

### 先说缺点：
### 1.这里的白嫖并不是无穷无尽的，而是看colab的空闲后端gpu情况，具体可查看colab官方文档，要是有能力可以去colab开colab pro，能得到一个更强大的云端训练环境。（一般都能用）

#### 2.blender插件产生的外置缓存无法上传到云进行渲染，例如：flip fluids 的流体缓存。（有能力自行魔改）

* [google colab官方说明文档](https://research.google.com/colaboratory/faq.html)

### 介绍
简单的方式借用（嫖）google colab 的免费gpu来渲染自己的blender文件！
**从此解放自己的gpu！**

### 创库原由
作为blender兴趣爱好者，苦于电脑配置低渲染慢而烦恼，在网上冲浪看到了YouTube上有许多blender云渲染的方法，例如：[Micro Singularity](https://youtu.be/A8FiCPUEv9Q)的教程，本方案就是在此基础上修改优化的。除了这个方法国内也有人在b站等平台发布过教程，也可以选择其他方案，适合自己的方案才是最好的。

### 方案原理
借用[google colab](https://colab.research.google.com)的免费GPU来在线渲染。

### colab介绍
什么是 Colab？
借助 Colaboratory（简称 Colab），您可在浏览器中编写和执行 Python 代码，并且：
* 无需任何配置
* 免费使用 GPU
* 轻松共享
它尤其适合机器学习、数据分析和教育目的。 从技术上来说，Colab 是一种托管式Jupyter 笔记本服务。

### 使用前准备环境
* 1，谷歌云盘
* 2，浏览器
* 3，你的打包好的blender工程文件
* 4，渲染调用脚本

### 使用步骤

<details>
  <summary>👈使用步骤在这里打开噢</summary>

##### 1. **打包**blender工程文件。
***
![打包工程文件](readme.assets/1.png)
***
##### 2. 浏览器(我用的是edge，理论上chrome等都可运行)登录自己的谷歌云盘并用Google colab打开脚本。

![](/readme.assets/25.png)
***
1. 先确认已经登录了自己的**Google云盘**
2. 下拉打开方式**三角**
3. **连接更多应用程序**
![](/readme.assets/26.png)
***
搜索**Colaboratory**并进行**安装**
![](/readme.assets/5.png)
***
用Colaborator的打开方式打开脚本
![](/readme.assets/27.png)
***
!!!!1 Next 👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇
***
##### 3.  打开脚本后第一步直**接执行第一框代码``#1``**，看被分配后端gpu的型号，如果是和图一样是**k80**，则继续跟着教程走就好，如果与图不符而显示是**t4**，则可直接**跳过这一步**，后续会解释为什么不用k80。

![](/readme.assets/7.png)
***
![](/readme.assets/8.png)
***
![](/readme.assets/9.png)
***
可以看到已经终止了后端，状态已经变成重新连接，这时候只需要重新执行第一框代码``#1``即可，反复步骤得到t4即可

![](/readme.assets/10.png)
***
看到获取到**t4**，就证明你成功了！如果获取不到，可以过一段时间再试，一般试了10次获取不到，就是colab没有被你嫖得t4-gpu了，可以先去做些其他事情，5分钟后再试试

![](/readme.assets/11.png)
***
##### 4. 如果你到这一步了，**恭喜你**! 已经前路无阻了，下面只需要依次执行代码就行了！

执行第二框代``#2``，提示连接你的Google云盘到colab，等待代码执行完成
![](/readme.assets/12.png)

执行第三框代码``#3``，等待代码执行完成即可执行下一框代码
![](/readme.assets/13.png)

执行第四框代码``#4``，等待代码执行完成

此时回到Google云盘，**刷新**，即可看到一个文件夹"in_blender",打开此文件夹，将你的blender工程文件上传进去。

![](/readme.assets/15.png)

我这里上传得blender工程文件名叫 **myhouse.blend** -------记住自己的blender工程文件名（带后缀）。

执行第五代码框``#5``，看到让我们输入自己刚刚上传得blender工程文件名，我这里输入**myhouse.blend**，输入后记得**回车**！！！！！！！
***
**注：blender工程文件如果带有特殊符号如：" . _ "等特殊符号就得在工程文件名外加上双引号**``"####.blend"``，否则无法进行渲染。
***经过实测blender工程文件名带空格`space`的都会影响后续渲染，blender工程文件名最好是无符号的纯英文和数字名。***
***

![](/readme.assets/28.png)
![](./readme.assets/16.png)

##### 5.渲染！

代码框``#6``、``#7``分别是渲染**单帧图片**和**多帧动画**，执行代码时**输入帧位**就开始执行了！！

下图是我渲染第一帧的例子
![](/readme.assets/17.png)
可以看到开始渲染了！！！！耐心等待即可！！！！
![](/readme.assets/18.png)
下图是我渲染第一帧到第二帧的例子
![](/readme.assets/21.png)
![](/readme.assets/22.png)
![](/readme.assets/23.png)

##### 6.渲染完成后查看渲染完成的文件**out_blender**
看到渲染代码显示blender quit 证明已经渲染完成！
在Google云盘根目录里看到有文件夹**out_blender**，渲染完成的文件就在里面，快去看看自己的成果吧！！
![](/readme.assets/19.png)
![](/readme.assets/20.png)

##### 7.渲染完成后操作
注意！！！！！！！！！！！！！！！！！！！！！！！
渲染完成后需要自行关闭后端gpu，白嫖用户是**不允许**一直挂着后台的，不运行gpu时会检测，**一直无人使用gpu**但是**占用资源**会可能被**封禁**。

</details>

## 更新
<details>

  <summary>👈更新在此处打开噢</summary>

### 使用k80后端渲染的方法 ```updata 2022-4-14```

#### 
很简单只需要解除与添加渲染#6#7的注释。
**注：k80真的很慢很慢，算力很低，很浪费时间，不迫不得已不用，自行斟酌。**
##### 1.先给原代码添加注释
![](/readme.assets/29.png)

![](/readme.assets/30.png)
***

### 更新blender应用程序 ```updata 2022-4-21```

#### 1.先搭建好环境。

* 1.获取后端GPU
* 2.连接到自己的Google云盘

#### 2.修改 ```#3```的代码
* 1.用```#```符号注释！mkdir。
* 2.去blender官网找到最新的blender—Linux 压缩包下载地址。
* 3.去Google云盘删除blender的应用程序文件夹。
* 3.运行```#3```

![](/readme.assets/31.png)

***

### 更新了t4无法渲染blender的问题！！```updata 2022-5-31```

#### 1.执行```#2.5```来更新英伟达最新驱动

![](/readme.assets/32.png)

### issues：https://github.com/googlecolab/colabtools/issues/2827

***

### 修复了blender应用程序无法正常解压到谷歌云盘的问题

![](/readme.assets/33.png)
![](/readme.assets/34.png)

***

### 修复了```#2.5```驱动更新失败的问题
![](/readme.assets/35.png)
![](/readme.assets/36.png)

***

### 再次修复了```#2.5```驱动更新失败的问题
完成时的提示如下图

![](/readme.assets/37.png)

*** 

</details>

***

#### 5.Q&A

Q：
能一直挂着一直渲染吗？不能的话最多可以渲染多久呢？万一渲染动画中断了怎么办？

A：
不能无限的一直挂着。目前我测试最多是挂4个小时左右，4小时左右就会弹窗检验是否是机器人。渲染完一帧图是完全足够的，如果在渲染动画时中断了，可在out_blender文件夹中查看渲染到了第几帧，重新执行代码框#7，选定帧来渲染就好，比如我渲染到12帧中断，再次执行是选择起始帧12，结束帧**。

***

Q: 
每个代码框是每次都要执行吗？不是又是怎么样的？

A: 
1. ``#1`` 每次重新打开脚本时就要运行此代码获取后端gpu，不然无法运行下列一系列渲染代码
2. ``#2`` 每次重新打开脚本时就要运行此代码来连接自己的Google云盘账户，只要输出显示为**Mounted at /content/drive**就行。
![](/readme.assets/24.png)
3. 代码框``#3``只需要执行一次，``#3``的目的是下载blender应用程序到Google云盘，在Google云盘里的名叫**blenderFile_Linux**的文件夹就是blender应用程序，如果出现错误，可将此文件夹整个删除，再次执行代码框``#3``即可。
4. ``#4`` 每次重新打开脚本时就要运行此代码,此代码解决not found问题。
5. ``#5`` 更换需要渲染的blender工程文件时需执行，此代码影响下面``#6#7``的渲染代码。
6. ``#6`` 渲染代码，渲染时执行。
7. ``#7`` 渲染代码，渲染时执行。

***
Q:
支持渲染cycles渲染器，那支持eevee渲染器吗？
A:
目前是不支持eevee,只支持cycles。

***
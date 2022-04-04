# Render Blender in google colab

* [google colab](https://colab.research.google.com)
* [google drive](https://drive.google.com/)

### 注：方案需全程在!的✈fanqiang的环境下进行！
### 先说缺点：这里的白嫖并不是无穷无尽的，而是看colab的空闲后端gpu情况，具体可查看colab官方文档，要是用能力可以去colab开pro，能得到一个更强大的云端训练环境。（一般都能用）
* [google colab官方说明文档](https://research.google.com/colaboratory/faq.html)

#### 介绍
简单的方式借用（嫖）google colab 的免费gpu来渲染自己的blender文件！
从此解放自己的gpu！

#### 创库原由
作为blender兴趣爱好者，苦于电脑配置低渲染慢而烦恼，在网上冲浪看到了YouTube上有许多blender云渲染的方法，例如：[Micro Singularity](https://youtu.be/A8FiCPUEv9Q)的教程，本方案就是在此基础上修改优化的。除了这个方法国内也有人在b站等平台发布过教程，也可以选择其他方案，适合自己的方案才是最好的。

#### 方案原理
借用[google colab](https://colab.research.google.com)的免费GPU来在线渲染。

#### colab介绍
什么是 Colab？
借助 Colaboratory（简称 Colab），您可在浏览器中编写和执行 Python 代码，并且：
* 无需任何配置
* 免费使用 GPU
* 轻松共享
它尤其适合机器学习、数据分析和教育目的。 从技术上来说，Colab 是一种托管式Jupyter 笔记本服务。

#### 使用前准备环境
* 1，谷歌云盘
* 2，浏览器
* 3，你的打包好的blender工程文件
* 4，渲染调用脚本

#### 使用步骤
1. **打包**blender工程文件。
***
![打包工程文件](readme.assets/1.png)
***
2. 浏览器(我用的是edge，理论上chrome等都可运行)**登录自己的谷歌云盘**并**上传渲染脚本**并**用Google colab打开脚本**。

![上传脚本](/readme.assets/2.png)
***
![](/readme.assets/3.png)
***
![](/readme.assets/4.png)
***
![](/readme.assets/5.png)
***
![](/readme.assets/6.png)
***
3.  打开脚本后第一步直**接执行第一框代码**，看被分配后端gpu的型号，如果是和图一样是**k80**，则继续跟着教程走就好，如果与图不符而显示是**t4**，则可直接**跳过这一步**，后续会解释为什么不用k80。

![](/readme.assets/7.png)
***
![](/readme.assets/8.png)
***
![](/readme.assets/9.png)
***
可以看到已经终止了后端，状态已经变成重新连接，这时候只需要重新执行第一框代码即可，反复步骤得到t4即可

![](/readme.assets/10.png)
***
看到获取到**t4**，就证明你成功了！如果获取不到，可以过一段时间再试，一般试了10次获取不到，就是colab没有被你嫖得t4-gpu了，可以先去做些其他事情，5分钟后再试试

![](/readme.assets/11.png)
***
4. 如果你到这一步了，**恭喜你**! 已经前路无阻了，下面只需要依次执行代码就行了！

执行第二框代码，提示连接你的Google云盘到colab，等待代码执行完成
![](/readme.assets/12.png)

执行第三框代码，等待代码执行完成即可执行下一框代码
![](/readme.assets/13.png)
行第四框代码，等待代码执行完成

此时回到Google云盘，**刷新**，即可看到一个文件夹"in_blender",打开此文件夹，将你得blender工程文件上传进去。


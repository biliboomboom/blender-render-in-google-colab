# Render Blender in google colab

* [google colab](https://colab.research.google.com)
* [google drive](https://drive.google.com/)

### 注：方案需全程在fanqiang的环境下进行！
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
1. 打包blender工程文件。
![打包工程文件](readme.assets/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202022-04-04%20114311.png)

2. 浏览器(我用的是edge，理论上chrome等都可运行)登录自己的谷歌云盘并上传渲染脚本。
![上传脚本](/readme.assets/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20220404190322.png)

3. 



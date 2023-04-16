# THE-MPS-GOD

**在阅读之前，请各位：感恩🙏🙏🙏🙏**

**墨门🙏🙏🙏🙏**

**🙏🙏🙏🙏🙏🙏🙏🙏 蘑菇蓝先生维护好几个服务端还负债累累，依然夜以继日精益求精废寝忘食的给我们带来全球首款多线程重写版高并发服务端：MPS 🙏🙏🙏🙏🙏🙏🙏🙏**

**墨老如此努力工作，你怎么能诋毁他！！！没有他，你怎么开得了服务器！！！！**

**让我们再次感恩：墨门🙏🙏🙏🙏**

**本人不是也不打算成为国内 Minecraft 服务器圈子的成员。我只是做为一个围观者，发表我合理的批判。**

**关于作者：Minecraft 修改版服务器软件 KeYiMC 开发者。(由于我实在无法忍受国内服务器圈子的恶臭环境，KeYiMC 已经弃坑。)**

**本文不做任何排版，若您感到不舒服请停止阅读。**

**本文含有大体积图片，请确保您连接到 GitHub 的网络通畅无阻，否则会影响您的阅读体验。**

## 前情提要

本文中出现的所有人名均指代以下人士。为了对方的隐私安全，故不放出 QQ 号与昵称。

### 莫老

![image](https://user-images.githubusercontent.com/53771072/232274527-27858c4c-4d40-406f-b2ae-860ed14b8d82.png)

## Sakura 女士

![image](https://user-images.githubusercontent.com/53771072/232274401-e8af3c99-07a2-4a75-8935-1f3b222f67cc.png)

## 收银员

![image](https://user-images.githubusercontent.com/53771072/232274411-ded156bf-d0f0-497d-8f52-24618d906ccb.png)

## 起因

2023 年 3 月, Mohist 开发组宣布了全球首款重写版多线程高并发核心：MPS。

*以下为当时 "核心文档页" 的截图归档，该页面在 MPS 真正发布的时候已经被修改去除了造假图片，后文会提到。*

![QQ图片20230416123746](https://user-images.githubusercontent.com/53771072/232273118-18bfc820-8044-4cdd-9cb4-32d471647616.jpg)

在本页面中，我们可以清楚的看到 MPS-Dev-0748 与 Paper 的对比：

![image](https://user-images.githubusercontent.com/53771072/232273239-f1662eca-e46f-493a-96ef-635c2edffe43.png)

![image](https://user-images.githubusercontent.com/53771072/232273247-e8ca07b1-3641-4aa5-97bd-5e3c3fd59523.png)

如果您仔细观察，您可以发现所谓 MPS 截图中，村民的位置很明显不对劲：

![image](https://user-images.githubusercontent.com/53771072/232273265-bc9fdec7-51fc-4302-8d41-b577028e055f.png)

他们通通朝向一个方向。

并且：

![image](https://user-images.githubusercontent.com/53771072/232273272-0eeb9b20-bf3e-49e8-b8c8-cea63e728fc6.png)

究竟是什么黑魔法，能让一个区域里塞入 6k+ 村民还不被挤压分散开？

实现方法很简单，在 Minecraft 服务端中有一个 `entityList` 变量来存储所有的实体。

我们只需要：

```java
entityList.forEach(entity -> {
    entity.setAI(false);
});
```

即可实现该效果。

您可能已经意识到了这端代码的作用：关闭生物 AI。

在 MPS 开发组宣布该项目成立后，本着怀疑的态度，我加入了 Mohist 交流群询问有无视频性能展示。

但开发组成员 Sakura 女士却回应到：视频录制好了正在剪辑。

我们曾叫她不要剪辑直接发出，她却一拖再拖。

此时 Mohist 群内的 "收银员" 开始找我们麻烦了。

"预售为什么有一个预字呢？"

我想，他可能没有使用过诸如 京东、淘宝 这样的电商平台。

电商平台预售都有完整的商品介绍，您的产品只放出来了一个虚假的截图，还有理由来质问我？

而且，"预售" 一词为什么有一个 "售" 字呢？

这位 "收银员" 的智商我们不得而知，也不知道他是在什么精神状态下发出了如此无脑的话语来保护他的 Mohist 开发组大爹。

我不想在别人的地盘惹麻烦，因此我打算到了他们发布的日子再次询问。

Sakura 女士是否真的了解 Minecraft 服务器，我们不得而知：

![Screenshot_2023_0416_141048](https://user-images.githubusercontent.com/53771072/232275324-0acd93e8-d3a3-4681-91fa-aa029a3370bd.jpg)

"收银员" 辩护 Mohist 大爹的截图：

![{X$L)BO78Q5 A%SO0_BWGLR](https://user-images.githubusercontent.com/53771072/232275255-1de7d699-8602-4caa-b3d0-2c0668ab616f.jpg)

## 发酵

在这途中，有许多人购买了 MPS。

以下为 MPS 发布时的价格截图：

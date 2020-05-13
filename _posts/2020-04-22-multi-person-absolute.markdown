---
title: "单视角多人绝对位置姿态估计相关工作整理"
layout: post
date: 2020-04-22 20:48
image: /assets/images/multi-person/title.jpg
headerImage: true
tag:
- pose estimation
category: blog
author: Buzhen Huang
excerpt: 多人绝对位置姿态估计相关工作整理
description: 多人绝对位置姿态估计相关工作整理
---

**<font face="微软雅黑">本文为博主原创文章，转载请注明出处。</font>**

二维人体姿态估计的工作已经有很多，如openpose、alphapose等工作已经能够在绝大多数场景下实现较好的效果。在具有颠覆性的解决方案之前，除却遮挡等特定条件，目前二维的准确率已经很难再提升。在近年的各大视觉顶会中，人们也纷纷将目光投向三维，然而单视角情况下深度方向的视觉歧义性始终是一个难以解决的难点。在单人三维姿态估计中，由于只需要估计相对根节点的深度，深度神经网络通过一些先验的推理能够大致估计出相对深度。当把场景拓展到全局，在统一的相机坐标或者世界坐标下，三维姿态的准确率骤然下降。由于无法在相机坐标系下获得准确深度，这也导致了当前许多多人姿态估计的任务都披着多人的外衣，做着单人的事情。但多人的姿态估计由于更加接近现实场景，因此仍然是一个值得研究的问题。在这篇文章中整理了当前单视角多人绝对位置姿态估计任务的相关工作。

## 相关工作
![表格]({{ site.url }}/assets/images/multi-person/table.jpg)

### 一、ICCV2019
文章：Camera Distance-aware Top-down Approach for 3D Multi-person Pose Estimation from a Single RGB Image<br>
人体绝对深度获取方式：粗略计算+CNN校正参数<br>
准确度相对较低<br>
![ICCV2019]({{ site.url }}/assets/images/multi-person/ICCV2019.jpg#pic_center)

### 二、CVPR2019
文章：XNect: Real-time Multi-person 3D Human Pose Estimation with a Single RGB Camera<br>
人体绝对深度获取方式：相机参数+地平面高度计算<br>
要求实验前标定相机参数与地平面，存在条件限制，实现参考[地平面高度计算](/human-height-3d/ "temp") <br>
![CVPR2019]({{ site.url }}/assets/images/multi-person/CVPR19.jpg#pic_center)

### 三、NIPS2018
文章：Deep Network for the Integrated 3D Sensing of Multiple People in Natural Images<br>
人体绝对深度获取方式：因为SMPL跟米制空间（mm）变换的scale为1000，优化二维关节点与3D关节的欧氏距离<br>
第一个多人单目带mesh的工作，使用网络回归相对pose<br>
![NIPS18]({{ site.url }}/assets/images/multi-person/NIPS18.jpg#pic_center)


### 四、CVPR2018
文章：Monocular 3D Pose and Shape Estimation of Multiple People in Natural Scenes<br>
人体绝对深度获取方式：因为SMPL跟米制空间（mm）变换的scale为1000，优化二维关节点与3D关节的欧氏距离<br>
与上文同一个作者，使用优化的方式<br>
![CVPR18]({{ site.url }}/assets/images/multi-person/CVPR18.jpg#pic_center)


### 五、IJCNN2019
文章：Absolute Human Pose Estimation with Depth Prediction Network<br>
人体绝对深度获取方式：结合深度图的网络估计<br>
绝对深度准确度跟（一）相近<br>
![IJCNN19]({{ site.url }}/assets/images/multi-person/IJCNN19.jpg#pic_center)


### 六、arXiv2020
文章：Multi-Person Absolute 3D Human Pose Estimation with Weak Depth Supervision<br>
人体绝对深度获取方式：结合深度图的网络估计<br>
上文同一作者，只是加了一步后面的联合深度网络，给人水文章的感觉<br>
![arxiv20]({{ site.url }}/assets/images/multi-person/arxiv20.jpg#pic_center)



---

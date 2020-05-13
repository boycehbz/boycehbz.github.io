---
title: "通过三维地平面计算虚拟人物身高（深度）的方法——XNect部分复现"
layout: post
date: 2020-04-25 20:48
image: /assets/images/multi-person/CVPR19.jpg
headerImage: true
tag:
- pose estimation
category: blog
author: Buzhen Huang
excerpt: 根据地平面计算人体高度
description: 根据地平面计算人体高度
---

**<font face="微软雅黑">本文为博主原创文章，转载请注明出处。</font>**

本文参考CVPR2019-XNect: Real-time Multi-person 3D Human Pose Estimation with a Single RGB Camera，对其所述的利用三维地平面计算人体高度，进而计算人体在场景中绝对位置的方法进行分析和复现。

从二维图像中恢复对象的绝对高度是计算机视觉、数字测量领域的一个重要问题。对于相机参数已知的二维图像，对象的绝对高度和其所在的绝对位置可以相互转换，因此具有重要的应用价值。在此首先总结一下从二维图像估计人体身高的几种方法。

## 单目图像人体高度估计相关方法
**从三维几何获取人体高度**<br>
&nbsp;&nbsp;&nbsp;&nbsp;1)通过三维空间中的地平面、相机参数、人体与地面接触点计算，即本文之后介绍的方法。<br>
&nbsp;&nbsp;&nbsp;&nbsp;2)根据场景中已知高度物体作为参考。<br>
&nbsp;&nbsp;&nbsp;&nbsp;该方法对已知条件具有苛刻的要求。<br>
**从相机几何获取人体高度**<br>
&nbsp;&nbsp;&nbsp;&nbsp;使用shape-from-defocus的方法。该方法需要多张图像进行焦扫描或使用专业相机。<br>
**从图像特征获取人体高度**<br>
&nbsp;&nbsp;&nbsp;&nbsp;主要为使用machine learning或者deap learning来对图像直接估计。<br>
**从图像测量获取人体高度**<br>
&nbsp;&nbsp;&nbsp;&nbsp;根据医学的相关研究，人体各部分肢体的比例和身高有一定相关性，可由此推算。（涨知识了）<br>

## 基于三维地平面的人体绝对身高估计
由于XNect没有提供该部分的源码和测试数据，因此需要自己来获得三维地平面。地平面即三维空间中虚拟人物所在的地面。
![plane]({{ site.url }}/assets/images/human-height/plane.jpg#pic_center)
准确的三维地平面很难通过单个视角来获取，因此本文使用了9个视角进行点采样，利用相机参数反算出三维点，然后用平面进行拟合。
![points]({{ site.url }}/assets/images/human-height/points.jpg#pic_center)
图中红点即为两个视角中的采样点，通过其二维坐标和相机参数能够对三维点进行解算。<br>
利用求得的三维点进行平面拟合，获得平面经过点采样后使用meshlab可视化，可见这样的采样还是能够基本满足实验要求的。
<!-- ![rec]({{ site.url }}/assets/images/human-height/rec.jpg#pic_center) -->
<div  align="center"> 
<img src="/assets/images/human-height/rec.jpg" width = "400" height = "300"/>
</div>
在获得地平面后，我们需要图像中目标人体与地平面接触的二维点和头顶的二维点坐标，这里我们以人体脚踝关节点和头顶关键点近似替代，2D关节点通过openpose等2D pose检测工具获取。
<div  align="center"> 
<img src="/assets/images/human-height/ankle.png" width = "128" height = "162"/>
</div>
我们以图示的脚踝关节点作为地面接触点，在相机坐标下由相机光心向图像关节点打一条射线，获取射线与地平面的交点。
<div  align="center"> 
<img src="/assets/images/human-height/ground.png" width = "458" height = "304"/>
</div>
再以交点作垂直地平面，正对相机的平面，即平面的法向方向为射线方向与地平面法向作两次叉乘。
<div  align="center"> 
<img src="/assets/images/human-height/plane.png" width = "250" height = "260"/>
</div>
由于脚踝并不是准确的地面接触点，因此所作平面会在人体的后方，此处存在一定误差。此时，我们用同样的方法向人体头顶作射线，射线会与刚刚所作平面形成一个交点，改点到地平面的距离即为三维人体高度。
<div  align="center"> 
<img src="/assets/images/human-height/height.png" width = "400" height = "250"/>
</div>
至此，利用高中数学的知识，我们计算得到了三维人体的高度。通过相机参数，我们能够换算到现实的米制空间，并能够轻松得到人体的绝对位置。

## References
\[1\] XNect: Real-time Multi-person 3D Human Pose Estimation with a Single RGB Camera, In CVPR, 2019.<br>
\[2\] What Face and Body Shapes Can Tell About Height, In ICCV Workshop, 2019.<br>


---

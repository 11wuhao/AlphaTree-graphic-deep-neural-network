
# The Single Shot Detector（SSD）
SSD是一种直接预测bounding box的坐标和类别的object detection算法，没有生成proposal的过程。它使用object classification的模型作为base network，如VGG16网络，

在特征图的每个位置预测K个box。对于每个box，预测C个类别得分，以及相对于default bounding box的4个偏移值，在m×n的特征图上将产生(C+4)×k×m×n 个预测值。在caffe代码中，C=21，因此输出的类别维度是8732×21 = 183372 ，boundingbox偏移值维度是8732×4 = 34928


paper： Wei Liu, et al. “SSD: Single Shot MultiBox Detector.” . [pdf](https://arxiv.org/pdf/1512.02325.pdf)  

SSD 结构如图：

![ssd](https://github.com/weslynn/graphic-deep-neural-network/blob/master/otherpic/detectpic/ssd.jpg)




用不同节点表示如图，


![ssd](https://github.com/weslynn/graphic-deep-neural-network/blob/master/modelpic/objdetection/ssd.png)



<p align="right">[大图](https://raw.githubusercontent.com/weslynn/graphic-deep-neural-network/master/modelpic/objdetection/ssd.png)</p>



预测的类别 和偏移值 计算如图

![ssdcal](https://github.com/weslynn/graphic-deep-neural-network/blob/master/modelpic/objdetection/ssd_cal.png)


整个SSD完整对应如图


![ssd_total](https://github.com/weslynn/graphic-deep-neural-network/blob/master/modelpic/objdetection/ssd_total.png)



<p align="right">[大图](https://raw.githubusercontent.com/weslynn/graphic-deep-neural-network/master/modelpic/objdetection/ssd_total.png)</p>




源码：

tensorflow 源码 https://github.com/balancap/SSD-Tensorflow/blob/master/nets/ssd_vgg_300.py

caffe ：https://github.com/weiliu89/caffe/tree/ssd

可参考的ppt : https://docs.google.com/presentation/d/1rtfeV_VmdGdZD5ObVVpPDPIODSDxKnFSU0bsN_rgZXc/edit#slide=id.g179f601b72_0_51

# [返回首页](https://github.com/weslynn/graphic-deep-neural-network/)
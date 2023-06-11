# HW3-基于RTMDet的气球检测

## 作业任务

**作业**：基于 RTMDet 的气球检测

**背景**：熟悉目标检测和 MMDetection 常用自定义流程。

**任务**：

1. 基于提供的 notebook，将 cat 数据集换成气球数据集;
2. 按照视频中 notebook 步骤，可视化数据集和标签;
3. 使用MMDetection算法库，训练 RTMDet 气球目标检测算法，可以适当调参，提交测试集评估指标;
4. 用网上下载的任意包括气球的图片进行预测，将预测结果发到群里;
5. 按照视频中 notebook 步骤，对 demo 图片进行特征图可视化和 Box AM 可视化，将结果发到群里
6. 需提交的测试集评估指标（不能低于baseline指标的50%）

- 目标检测 RTMDet-tiny 模型性能 不低于65 mAP。

## 解答

**1.可视化数据集和标签**

数据集

![下载](https://s2.loli.net/2023/06/11/OhL7Xk6toYAvzBu.png)

便签

![下载 (1)](https://s2.loli.net/2023/06/11/ZunxCYeRNw8yEU5.png)

**2.测试集评估：**

```python
Evaluate annotation type *bbox*
DONE (t=0.11s).
Accumulating evaluation results...
DONE (t=0.01s).
 Average Precision  (AP) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.734
 Average Precision  (AP) @[ IoU=0.50      | area=   all | maxDets=100 ] = 0.843
 Average Precision  (AP) @[ IoU=0.75      | area=   all | maxDets=100 ] = 0.829
 Average Precision  (AP) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.000
 Average Precision  (AP) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.373
 Average Precision  (AP) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.872
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=  1 ] = 0.240
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets= 10 ] = 0.770
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.822
 Average Recall     (AR) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.000
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.683
 Average Recall     (AR) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.914
06/11 07:53:36 - mmengine - INFO - bbox_mAP_copypaste: 0.734 0.843 0.829 0.000 0.373 0.872
06/11 07:53:36 - mmengine - INFO - Epoch(test) [13/13]  coco/bbox_mAP: 0.7340  coco/bbox_mAP_50: 0.8430  coco/bbox_mAP_75: 0.8290  coco/bbox_mAP_s: 0.0000  coco/bbox_mAP_m: 0.3730  coco/bbox_mAP_l: 0.8720  data_time: 0.0152  time: 0.0754

```



![image-20230611155501328](https://s2.loli.net/2023/06/11/q73XZsPeRwm215S.png)

**3.网络气球图像预测：**

![image-20230611160308197](https://s2.loli.net/2023/06/11/JZkQLrvUF31cKmH.png)



**4.可视化分析**

可视化 backbone 输出的 3 个通道

![1686471065252](https://s2.loli.net/2023/06/11/QBaxUtJZMKiRXYc.png)

可视化 neck 输出的 3 个通道

![1686471281178](https://s2.loli.net/2023/06/11/QBaxUtJZMKiRXYc.png)

查看 neck 输出的最小输出特征图的 Grad CAM

![1686471488021](https://s2.loli.net/2023/06/11/MCwSvnOKHlNtgA2.png)

查看 neck 输出的最大输出特征图的 Grad CAM

![1686471439133](https://s2.loli.net/2023/06/11/DGeFfjJw5r3chi9.png)

5.Log&Checkpoint

见  [log](/HW3/log)与 [checkpoint](/HW3/checkpoint) 文件夹

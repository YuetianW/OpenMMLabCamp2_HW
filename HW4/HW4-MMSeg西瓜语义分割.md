# HW4-MMSeg西瓜语义分割

## 作业任务

**作业：MMSeg 语义分割**

**背景：西瓜瓤、西瓜皮、西瓜籽像素级语义分割**

**TO DO LIST**：

1. Labelme 标注语义分割数据集（子豪兄已经帮你完成了）
2. 划分训练集和测试集（子豪兄已经帮你完成了）
3. Labelme 标注转 Mask 灰度图格式（子豪兄已经帮你完成了）
4. 使用 MMSegmentation 算法库，撰写 config 配置文件，训练 PSPNet 语义分割算法
5. 提交测试集评估指标
6. 自己拍摄西瓜图片和视频，将预测结果发到群里
7. （选做）训练 Segformer 语义分割算法，提交测试集评估指标

**西瓜瓤、西瓜籽数据集:**

- 标注：同济子豪兄

> [![image](https://user-images.githubusercontent.com/129837368/245073269-598d8e55-62b0-438b-87c5-15fc6df9a365.png)](https://user-images.githubusercontent.com/129837368/245073269-598d8e55-62b0-438b-87c5-15fc6df9a365.png)
> [![image](https://user-images.githubusercontent.com/129837368/245073289-6d50954b-8b87-4a47-a54a-a55a720e30ac.png)](https://user-images.githubusercontent.com/129837368/245073289-6d50954b-8b87-4a47-a54a-a55a720e30ac.png)

| 类别名称   | 类别语义 | 标注类别          | 灰度图像素值 |
| ---------- | -------- | ----------------- | ------------ |
| /          | 背景     | /                 | 0            |
| red        | 西瓜红瓤 | 多段线（polygon） | 1            |
| green      | 西瓜外壳 | 多段线（polygon） | 2            |
| white      | 西瓜白皮 | 多段线（polygon） | 3            |
| seed-black | 西瓜黑籽 | 多段线（polygon） | 4            |
| seed-white | 西瓜白籽 | 多段线（polygon） | 5            |

**数据集下载链接：**

- Labelme标注格式（没有划分训练集和测试集）: https://zihao-openmmlab.obs.cn-east-3.myhuaweicloud.com/20230130-mmseg/dataset/watermelon/Watermelon87_Semantic_Seg_Labelme.zip
- Mask标注格式（已划分训练集和测试集）：https://zihao-openmmlab.obs.cn-east-3.myhuaweicloud.com/20230130-mmseg/dataset/watermelon/Watermelon87_Semantic_Seg_Mask.zip

**需提交的测试集评估指标：（不能低于 baseline 指标的 50% ）**

-  aAcc: 60.6200
-  mIoU: 21.1400
-  mAcc: 28.4600

## 解答

1.数据集可视化

![image-20230614160858870](https://s2.loli.net/2023/06/14/TrkFu2iUGMANzfX.png)



2.测试集评估指标

```
+------------+-------+-------+
|   Class    |  IoU  |  Acc  |
+------------+-------+-------+
|    red     | 76.88 | 98.17 |
|   green    | 63.78 | 65.71 |
|   white    | 31.54 |  33.1 |
| seed-black | 54.56 |  58.2 |
| seed-white | 55.36 | 64.26 |
+------------+-------+-------+
06/14 13:17:03 - mmengine - INFO - Iter(test) [11/11]    aAcc: 82.1300  mIoU: 56.4200  mAcc: 63.8900  data_time: 0.0213  time: 4.8992
```

![image-20230614211728128](https://s2.loli.net/2023/06/15/5iEh3gyo1BsTzMQ.png)

3.网络西瓜图片预测

原图：

![testWM](https://s2.loli.net/2023/06/14/HhJKi4MIA1sQrjw.jpg)



预测：（感觉这张网图后面的西瓜虚化了，效果不是很好）

![image-20230614212750883](https://s2.loli.net/2023/06/14/dPcDQ2178wz6iKn.png)

叠加：

![image-20230614212815759](https://s2.loli.net/2023/06/14/SgHt8Vx5lNREJbP.png)

4.Log&Checkpoint&config

见  [log](/HW4/log)、[config](/HW4/config) [checkpoint](/HW4/checkpoint) 文件夹


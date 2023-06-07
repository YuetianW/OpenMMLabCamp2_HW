# HW2-基于 ResNet50 的水果分类

## 作业任务

**题目**：基于 ResNet50 的水果分类

**背景**：使用基于卷积的深度神经网络 ResNet50 对 30 种水果进行分类

**任务**

1. 划分训练集和验证集
2. 按照 MMPreTrain CustomDataset 格式组织训练集和验证集
3. 使用 MMPreTrain 算法库，编写配置文件，正确加载预训练模型
4. 在水果数据集上进行微调训练
5. 使用 MMPreTrain 的 ImageClassificationInferencer 接口，对网络水果图像，或自己拍摄的水果图像，使用训练好的模型进行分类
6. 需提交的验证集评估指标（不能低于 60%）

- ResNet-50
  [![Resnet-50](https://user-images.githubusercontent.com/94358981/243633153-f76b4aa5-e4d6-4c02-bff9-09d974268bfa.png)](https://user-images.githubusercontent.com/94358981/243633153-f76b4aa5-e4d6-4c02-bff9-09d974268bfa.png)

## 解答

1.验证集评估：

![image-20230607200504322](https://s2.loli.net/2023/06/07/sALOdu3EDWZXNzF.png)

2.网络水果图像分类：

![test](https://s2.loli.net/2023/06/07/iKE8tDyLQCPGarT.png)

预测结果：

![image-20230607210453862](https://s2.loli.net/2023/06/07/8gcSrhKjvtIxa6A.png)

3.Log&Checkpoint

见  [log](/HW2/log)与 [checkpoint](/HW2/checkpoint) 文件夹

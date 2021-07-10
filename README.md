# Empirical Studies on Test Input Selection Methods for Deep Neural Network Testing

This is the implementation repository of our incoming APSEC 2021 paper: **Empirical Studies on Test Input Selection Methodsfor Deep Neural Network Testing**

## Description

In this paper, we propose an empirical study on Test Input Selection Methods for Deep Neural Network Testing. In our empirical study, we first select 18 pairs of DNN models and the corresponding test sets from seven popular DNN datasets as our experimental subjects. Then we consider four state-of-the-art TIS-DNN methods, including CSS, CES, DeepReduce and PACE. Moreover, we also consider a simple random sampling method SRS as a reference method. Based on these experimental subjects and TIS-DNN methods, we aim to answer the following three research questions (RQs):

1. **RQ1**: Can these TIS-DNN methods guarantee the accurate performance estimation on each class?
2. **RQ2**: Whether the accurate performance estimation on each class can help to improve the test adequacy based on DNN-based coverage criteria?
3. **RQ3**: How much perform improvement room for the current TIS-DNN methods? 

## Experiment Results

We have release out results for the experiments in this paper, which have been put in directories from RQ1 to RQ3.

* **RQ1**

  In RQ1, we analyze the accuracy estimation error for five test input selection methods on 18 models. The five test input selection methods and the models are presented as follows, along with the corresponding datasets:

  Five test input selection methods:

  * Simple Random Selection (SRS)
  * Confidence-based Stratified Sampling (CSS)
  * Confidence-based Stratified Sampling (CES)
  * DeepReduce (DR)
  * Practical ACcuracy Estimation (PACE)

  18 models with the corresponding datasets:

  | ID   |    测试集名称    |    模型    | 数据集大小（KB） | 样本数量 | 整体准确率（%） | 类别数量 | 测试数据类型 |
  | ---- | :--------------: | :--------: | :--------------: | :------: | :-------------: | :------: | :----------: |
  | 1    |      MNIST       |  LeNet-1   |       113        |  10,000  |      94.86      |    10    |   original   |
  | 2    |      MNIST       |  LeNet-4   |       947        |  10,000  |      96.79      |    10    |   original   |
  | 3    |      MNIST       |  LeNet-5   |       1093       |  10,000  |      98.68      |    10    |   original   |
  | 4    |      MNIST       | LeNet-5-M1 |       1093       |  10,000  |      79.53      |    10    |   original   |
  | 5    |      MNIST       | LeNet-5-M2 |       1093       |  10,000  |      77.27      |    10    |   original   |
  | 6    |      MNIST       | LeNet-5-M3 |       1093       |  10,000  |      79.14      |    10    |   original   |
  | 7    |     CIFAR-10     |   VGG-16   |      21814       |  10,000  |      78.71      |    10    |   original   |
  | 8    |     CIFAR-11     | ResNet-20  |       3507       |  10,000  |      91.45      |    10    |   original   |
  | 9    |    CIFAR-100     | ResNet-20  |      10615       |  10,000  |      71.42      |   100    |   original   |
  | 10   |       SVHN       |  LeNet-5   |       522        |  26,032  |      87.9       |    10    |   original   |
  | 11   |  Fashion-MNIST   |  LeNet-5   |       385        |  10,000  |      89.88      |    10    |   original   |
  | 12   |  Autogen-MNIST   |  LeNet-5   |       1093       |  10,000  |      49.35      |    10    |  generated   |
  | 13   | Autogen-CIFAR-10 | ResNet-20  |       3507       |  10,000  |      42.92      |    10    |  generated   |
  | 14   |   Autogen-SVHN   |  LeNet-5   |       522        |  10,000  |      43.69      |    10    |  generated   |
  | 15   | Autogen-Fashion  |  LeNet-5   |       385        |  10,000  |      45.31      |    10    |  generated   |
  | 16   |     ImageNet     |   VGG-19   |      562176      |  50,000  |      64.73      |   1000   |   original   |
  | 17   |     ImageNet     | ResNet-50  |      100352      |  50,000  |      68.27      |   1000   |   original   |
  | 18   | Speech-Commands  | DeepSpeech |       6734       |  6,471   |      94.53      |    30    |   original   |

  In this directory, we presents the results for the previous mentioned experiment, and draw figures for precisely presentation. The results for 18 models are put in the 18 folders separately. We will show some figures for detailed explanation. As we can see from the figure, each of the figures contains two curves, in which the blue curve means the total accuracy estimation error of the model, while the orange curve denotes the average accuracy estimation error of each single class.

  

  <center class = "half"><img src="RQ1/MNIST-LeNet-1/MNIST-LeNet-1_CES.png" width="300" height="200" alt="MNIST-LeNet-1_SRS" align=center /><img src="RQ1/MNIST-LeNet-1/MNIST-LeNet-1_CES.png" width="300" height="200" alt="MNIST-LeNet-1_CSS" align=center /><img src="RQ1/MNIST-LeNet-1/MNIST-LeNet-1_CES.png" width="300" height="200" alt="MNIST-LeNet-1_CES" align=center /><img src="RQ1/MNIST-LeNet-1/MNIST-LeNet-1_CES.png" width="300" height="200" alt="MNIST-LeNet-1_DeepReduce" align=center /><img src="RQ1/MNIST-LeNet-1/MNIST-LeNet-1_CES.png" width="300" height="200" alt="MNIST-LeNet-1_PACE" align=center /></center>

* **RQ2**

  


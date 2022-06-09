# Can Test Input Selection Methods for Deep Neural Network Guarantee Test Diversity? A Large-scale Empirical Study

This is the implementation repository of our incoming IST 2021 paper: **Can Test Input Selection Methods for Deep Neural Network Guarantee Test Diversity? A Large-scale Empirical Study**

## Description

In this paper, we propose an empirical study on Test Input Selection Methods for Deep Neural Network Testing. In our empirical study, we first select 18 pairs of DNN models and the corresponding test sets from seven popular DNN datasets as our experimental subjects. Then we consider four state-of-the-art TIS-DNN methods, including CSS, CES, DeepReduce and PACE. Moreover, we also consider a simple random sampling method SRS as a reference method. Based on these experimental subjects and TIS-DNN methods, we aim to answer the following three research questions (RQs):

1. **RQ1**: Can previous TIS-DNN methods guarantee the accurate performance estimation on each class?
2. **RQ2**: Can the accurate performance estimation on each class help to achieve accurate test adequacy estimation
(i.e., coverage estimation based on DNN-based coverage criteria)?
3. **RQ3**: Can current TIS-DNN methods be improved in terms of performance?

## Experiment Results

We have release out results for the experiments in this paper, which have been put in directories from RQ1 to RQ3.

* **RQ1**

  In RQ1, we first want to verify whether the previous TIS-DNN methods can guarantee accurate performance estimation on all the classes. 
Then, we want to  further investigate whether the previous TIS-DNN methods can ensure the accurate performance estimation on each class.

  To answer this RQ, we first analyze the overall accuracy on all the classes $AccEE_{all}$ and the accuracy on each class $AccEE_{avg}$ by controlling the size of the selected subset. 
<!--   Five test input selection methods:

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
  | 18   | Speech-Commands  | DeepSpeech |       6734       |  6,471   |      94.53      |    30    |   original   | -->
  
  The subset size setting method used in result analysis for RQ1:

  | \# class | Minimum size | Maximum Size | Step Size |
  | :------: | :----------: | :----------: | :-------: |
  |    10    |       5      |      205     |    10     |
  |    30    |      22      |     1590     |    64     |
  |    100   |      50      |     2050     |    100    |
  |   1000   |     500      |    20500     |    1000   |


<!--   In this directory, we presents the results for the previous mentioned experiment, and draw figures for precisely presentation. The results for 18 models are put in the 18 folders separately. We will show some figures for detailed explanation. As we can see from the figure, each of the figures contains two curves, in which the blue curve means the total accuracy estimation error of the model, while the orange curve denotes the average accuracy estimation error of each single class. -->

In this RQ, we show the results on four DNN models：

  <center class = "half"><img src="RQ1/F2.png" width="380" height="175" alt="Accuracy estimation error on ResNet-20 model for the CIFAR-100 dataset when considering different subset size" align=center /><img src="RQ1/F3.png" width="380" height="175" alt="Accuracy estimation error on VGG-19 model for the ImageNet dataset when considering different subset size" align=center /><img src="RQ1/F4.png" width="380" height="175" alt="Accuracy estimation error on LeNet-5 model for the SVHN dataset when considering different subset size" align=center /><img src="RQ1/F5.png" width="380" height="175" alt="Accuracy estimation error on LeNet-5 model for the Autogen-MNIST dataset when considering different subset size" align=center /></center>

  For each subfigure,  the $x$-axis denotes the size of the selected subset, the $y$-axis denotes the accuracy estimation error on all the classes and each class.



* **RQ2**

  In RQ2, we aim to investigate whether accurate performance estimation on each class can help to achieve accurate coverage estimation for the test adequacy of the original inputs based on DNN-based coverage criteria. 

<!--   To investigate RQ2, we first aim to construct subsets, which can cover different classes. For each model, we will generate five different test subsets from the original set with different random seeds when given the fixed number of the covered classes. For each generated subset, we will run TIS-DNN methods to compute the accuracy estimation error $AccEE_{avg}$ for each class. -->

  To investigate RQ2, we first aim to construct subsets, which can cover different classes and the scale is fixed. We extract the same number of test inputs each time according to the specified number of classes to build a test subset.

  Then we consider the five popular deep neuron network-based coverage criteria (i.e., NC, NBC, SNAC, TKNC, and KMNC) to calculate the test adequacy of deep learning testing. 

  Finally, we will compute the correlation coefficient between the accuracy estimation error for each class $AccEE_{avg}$ and the coverage difference $CovDiff$ when given a DNN-based coverage criterion.

  In our study, we utilize the Pearson correlation coefficient and the Pearson correlation coefficient can be computed as follows:

  $$r(X,Y)=\frac{Cov(X,Y)}{\sqrt{Var[X]\cdot Var[Y]}}$$

  where $X$ and $Y$ are one-dimensional vectors, $Cov(X, Y)$ means the covariance of $X$ and $Y$, and $Var[Y]$ denotes the variance of the vector $Y$.

  The final results are shown in the following table:

  | ID   | NC    | NBC    | SNAC   | TKNC   | KMNC   |
  | ---- | ----- | ------ | ------ | ------ | ------ |
  | 1    | 0.965 | N/A    | 0.838  | 0.745  | 0.77   |
  | 2    | 0.867 | -0.054 | 0.807  | 0.732  | -0.258 |
  | 3    | 0.935 | -0.202 | 0.876  | 0.865  | 0.032  |
  | 4    | 0.845 | 0.411  | 0.838  | 0.786  | 0.005  |
  | 5    | 0.919 | 0.05   | 0.906  | 0.947  | -0.147 |
  | 6    | 0.922 | 0.032  | 0.925  | 0.949  | -0.347 |
  | 7    | 0.99  | 0.765  | 0.778  | 0.904  | 0.237  |
  | 8    | 0.754 | -0.412 | -0.093 | 0.917  | 0.883  |
  | 9    | 0.961 | -0.043 | 0.378  | 0.885  | 0.049  |
  | 10   | 0.945 | 0.929  | 0.934  | 0.969  | 0.542  |
  | 11   | 0.932 | 0.759  | 0.762  | 0.909  | 0.588  |
  | 12   | 0.535 | -0.669 | -0.489 | -0.852 | 0.099  |
  | 13   | 0.574 | 0.478  | 0.024  | 0.883  | 0.372  |
  | 14   | 0.861 | 0.345  | 0.313  | 0.828  | -0.901 |
  | 15   | 0.941 | -0.393 | 0.894  | 0.983  | 0.753  |
  | 16   | 0.956 | 0.949  | 0.956  | 0.948  | 0.757  |
  | Sum  | 13/16 | 2/16   | 9/16   | 13/16  | 2/16   |

* **RQ3**

  After comparing the optimal subsets, we can compute the performance improvement room of the current TIS-DNN methods in this RQ.

  In this RQ, we design a simple method Best.
  Specifically, given the size of the subset, this method first determines the sampling number $sampNum[i]$ for $i$-th class according to the proportion of each class in the original test inputs.

  Then for the $i$-th class, it computes the sampling number  of test inputs $sampNum_{c}[i]$ which are predicted correctly and the sampling number of test inputs $sampNum_{w}[i]$ which are predicted wrongly based on the accuracy of the $i$-th class of the original test inputs.

  Later, for the $i$-th class, it samples $sampNum_{c}[i]$ test inputs with the correct predictions, and  $sampNum_{w}[i]$ test inputs with the wrong predictions from the original inputs in the $i$-th class.

  Finally, after iterating all the classes, it can determine the optimal subset.

  In this RQ, we first show the performance improvement room  after comparing the method Best and the method PACE. Final results (i.e., average value and standard deviation) can be found in the following table:

  |  ID  | Room for $AccEE_{all}$ | Room for $AccEE_{avg}$ |
  | :--: | :--------------------: | :---------------------: |
  |  1   |    (2.121%, 1.910%)    |    (3.728%, 4.367%)     |
  |  2   |    (0.870%, 0.693%)    |    (1.190%, 0.615%)     |
  |  3   |    (0.103%, 0.311%)    |    (1.218%, 2.040%)     |
  |  4   |    (1.139%, 4.024%)    |    (1.815%, 4.043%)     |
  |  5   |    (3.117%, 7.125%)    |    (2.153%, 6.220%)     |
  |  6   |    (0.126%, 0.514%)    |    (1.519%, 4.099%)     |
  |  7   |    (2.780%, 4.142%)    |    (9.633%, 3.072%)     |
  |  8   |    (1.124%, 1.664%)    |    (7.939%, 2.847%)     |
  |  9   |    (1.349%, 0.608%)    |    (10.963%, 6.071%)    |
  |  10  |    (3.997%, 4.527%)    |    (7.230%, 4.466%)     |
  |  11  |    (0.514%, 1.029%)    |    (3.490%, 7.854%)     |
  |  12  |    (0.282%, 0.978%)    |    (3.540%, 2.639%)     |
  |  13  |    (0.479%, 0.959%)    |    (9.713%, 4.710%)     |
  |  14  |    (0.719%, 0.549%)    |    (9.408%, 4.591%)     |
  |  15  |    (3.189%, 5.018%)    |    (12.833%, 2.832%)    |
  |  16  |    (7.673%, 8.416%)    |    (10.971%, 6.765%)    |
  |  17  |    (1.005%, 1.134%)    |    (11.423%, 4.756%)    |
  |  18  |    (1.660%, 1.696%)    |    (7.214%, 4.632%)     |
   

<!--   | Measure | Subject ID | Improvement Room(Average, Standard Deviation) |
  | :-----: | :--------: | :-------------------------------------------: |
  |   Room for $AccEE_{all}$   |    1-6    |  (2.121%, 1.910%)  (0.870%, 0.693%)  (0.103%, 0.311%)  (1.139%, 4.024%)  (3.117%, 7.125%)  (0.126%, 0.514%) |
  |   Room for $AccEE_{all}$   |   7-12    |    (1.349%,0.608%)          |
  |   Room for $AccEE_{all}$   |   13-18   |    (0.599%,0.654%)          |
  |   Room for $AccEE_{avg}$   |    1-6    |    (2.085%,1.819%)          |
  |   Room for $AccEE_{avg}$   |   7-12    |    (1.349%,0.608%)          |
  |   Room for $AccEE_{avg}$   |   13-18   |    (0.599%,0.654%)          |
 -->

  Then we analyze the effect of the class number on the performance improvement room.
  We compute the average value and the standard deviation grouped by the class number when considering different data types and the results can be found in the following table. 

  In this table, we can find with the increase of the class number, the performance improvement room for $AccEE_{all}$ increases, while the performance improvement room for $AccEE_{avg}$ decreases.

  | Data Type | \# class | Room for $AccEE_{all}$ | Room for $AccEE_{avg}$ |
  | :-------: | :------: | :--------------------: | :---------------------: |
  |   Image   |    10    |    (2.085%,1.819%)     |     (5.886%,2.333%)     |
  |   Image   |   100    |    (1.349%,0.608%)     |    (10.963%,6.071%)     |
  |   Image   |   1000   |    (0.599%,0.654%)     |     (9.561%,4.624%)     |
  |   Audio   |    30    |    (0.514%,1.029%)     |     (3.490%,7.854%)     |


# DeepDOA
基于深度神经网络的稀疏降噪自编码器SDAE在小型无人机的测向实现。与子空间分解类算法ESPRIT和MUSIC算法进行比较。

由于相位同步机制、天线校准机制和天线辐射模式的分析模型都不是必要的，所以所提出的DF方案是实用且低复杂度的。此外，所提出的DF方法频偏分析方法可使用单通道射频接收机来实现。

For more details, please see our [Arxiv paper](https://arxiv.org/pdf/1712.01154.pdf).

### Whole Architecture:

<img src="images/Whole_Architecture.PNG" width="500">

### Architecture training phase:

<img src="images/Training.PNG" width="500">


### Dependencies

- Tensorflow (recommended below 1.5)
- Numpy 1.14.4

### Dataset数据集

提供部分数据演示所提出的方法
训练数据: Dround_Data_New/Normalized
测试数据 : Dround_Data_New/Normalized_test

数据以45度进行区域划分，总计有8个区域。
例如：deg_0_normalize.csv数据文件代表从第一个区域收集到的训练文件。


### File description 文件描述

- DNN_Ground_data_8sectors.py : Implementation without SDAE
- DenoisingAE.py :实现稀疏降噪自编码进行单独训练，学习降噪特征
   Implementation of SDAE for training it separately to learn denoising features.
- get_csv_data.py : Data handler
- main.py : 结合稀疏降噪自编码SDAE和DNN实现DOA估计
   combining SDAE with a neural network to perform DOA estimations


### Citation引证

If this is useful for your work, please cite our [Arxiv paper](https://arxiv.org/pdf/1712.01154.pdf):

```bibtex
@article{abeywickrama2017rf,
  title={RF-Based Direction Finding of UAVs Using DNN},
  author={Abeywickrama, Samith and Jayasinghe, Lahiru and Fu, Hua and Yuen, Chau},
  journal={arXiv preprint arXiv:1712.01154},
  year={2017}
}
```
### License
This is released under the MIT license. For more details, please refer
[LICENSE](https://github.com/LahiruJayasinghe/DeepDOA/blob/master/LICENSE).

"Copyright (c) 2018 Lahiru Jayasinghe"

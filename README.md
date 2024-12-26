# CA-Transformer RUL预测项目

## 项目简介

本项目旨在使用结合注意力机制和Transformer结构的混合模型（CA-Transformer）对轴承的剩余使用寿命（RUL）进行预测。通过域自适应方法（DAN），模型能够在源域和目标域之间进行知识迁移，提高预测的准确性和泛化能力。项目中使用了PRONOSTIA和XJTU-SY两个实验数据集，并结合了CBAM注意力机制和门控单元来增强特征提取能力。

## 目录

- [项目简介](#项目简介)
- [安装与运行](#安装与运行)
- [数据集说明](#数据集说明)
- [使用方法](#使用方法)
- [模型架构](#模型架构)
- [训练与测试](#训练与测试)
- [结果展示](#结果展示)
- [贡献者](#贡献者)
- [许可证](#许可证)

## 安装与运行

### 环境依赖

确保已安装以下依赖库：

- Python 3.7+
- NumPy
- Pandas
- PyTorch
- matplotlib
- torchstat
- scipy

可以使用以下命令安装必要的Python库：

```bash
pip install numpy pandas torch matplotlib torchstat scipy

#运行项目
配置数据路径

在代码中，将数据集路径修改为实际存放位置。例如：

python

data0 = np.load(r"C:\路径\到\PRONOSTIA-bearing dataset\ts_1.npy")
运行训练脚本

确保所有依赖库已安装，然后运行主训练脚本：

bash

python src/main.py


#数据集说明
PRONOSTIA Bearing Dataset
来源: PRONOSTIA
内容: 包含多个轴承的振动信号数据，适用于RUL预测任务。
路径: data/PRONOSTIA-bearing dataset/resized file/
XJTU-SY Bearing Dataset
来源: 西安交通大学实验室
内容: 包含不同工况下轴承的振动信号数据。
路径: data/XJTU-SY-bearing dataset/condition1/


#使用方法
使用方法
数据预处理

代码中已包含数据加载和预处理步骤，包括最大-最小归一化和标签生成。

python

def max_min_normalization(raw_features, whole_data):
    # 归一化代码
数据加载

使用自定义的数据加载器生成源域和目标域的训练集。

python

source_train_loader = Source_Train_Loader(...)
target_train_loader = Target_Train_Loader(...)
模型训练

调用train函数进行模型训练。

train(model)
模型测试

加载最优模型后，进行多次测试以估计模型的贝叶斯不确定性。

model.load_state_dict(torch.load('model_bearing1_3.pth'))
test(model)





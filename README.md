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

你可以使用以下命令安装必要的Python库：

```bash
pip install -r requirements.txt
[requirements.txt](https://github.com/user-attachments/files/18249182/requirements.txt)

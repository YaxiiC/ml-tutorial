# Machine Learning Tutorial（机器学习入门教程）

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YaxiiC/ml-tutorial/blob/main/ML-tutorial.ipynb)

面向**机械工程、材料工程、生物医学工程**研究生的机器学习入门教程。一个 Jupyter 笔记本，三个由浅入深的例子，**每一行关键代码都有中文注释**。

A hands-on introduction to machine learning for engineering graduate students: one notebook, three worked examples, with line-by-line comments in Chinese.

---

## 内容

| # | 例子 | 任务类型 | 数据 | 模型 |
|---|---|---|---|---|
| 1 | **乳腺癌分类** | 二分类 | 569 名患者，30 个细胞核测量特征 | 逻辑回归、随机森林 |
| 2 | **糖尿病病情进展预测** | 回归 | 442 名患者，10 个基线指标 | Ridge 回归、随机森林 |
| 3 | **磁瓦表面缺陷检测** | 图像分类（深度学习） | 1344 张工业零件灰度图 | 卷积神经网络（CNN，PyTorch） |

每个例子都按同一个流程组织：

```
加载数据 → 可视化特征相关性 → 切分训练/测试集 + 标准化 → 训练模型 → 测试集评估 → 交叉验证比较模型 → 可视化结果
```

### 学完能理解的概念

- 训练集 / 测试集、`fit` 与 `transform` 的区别、**数据泄漏**以及如何用 `pipeline` 避免
- 分类指标：precision、recall、混淆矩阵、ROC 曲线、AUC；回归指标：MAE、RMSE、R²
- **基线模型**的重要性；交叉验证；正则化（Ridge）
- 深度学习训练循环：前向传播 → 反向传播 → 参数更新；学习率与学习率调度；数据增强
- 为什么在医学诊断和工业质检里，**漏检**比误报更危险

---

## 怎么运行

### 方法一：Google Colab（推荐，不用安装任何东西）

1. 点上面的 **Open in Colab** 按钮
2. 登录 Google 账号，点 **File → Save a copy in Drive**，在自己的副本里运行和修改
3. 点 **Runtime → Run all**

> 深度学习部分在 Colab 免费 CPU 上训练约 4 分钟。可以在 **Runtime → Change runtime type** 里换成 GPU，会快很多。

### 方法二：本地运行

```bash
git clone https://github.com/YaxiiC/ml-tutorial.git
cd ml-tutorial
pip install -r requirements.txt
jupyter notebook ML-tutorial.ipynb
```

> 深度学习部分用到 `git` 和 `ls` 命令下载并查看数据集；在 Windows 上建议用 Git Bash 或 WSL 运行。

---

## 数据来源

- **乳腺癌数据集**：Breast Cancer Wisconsin (Diagnostic)，通过 `sklearn.datasets.load_breast_cancer` 加载，原始数据来自 [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)。
- **糖尿病数据集**：Efron et al., *Least Angle Regression* (2004) 使用的糖尿病数据，通过 `sklearn.datasets.load_diabetes` 加载。
- **磁瓦缺陷数据集**：[Magnetic Tile Defect Datasets](https://github.com/abin24/Magnetic-tile-defect-datasets.)，来自论文 *Saliency of magnetic tile surface defects*（Huang et al.）。运行时由笔记本自动从 GitHub 下载，本仓库不包含图片。使用该数据集请引用原作者的论文。

# Deepening Neural Networks Implicitly and Locally via Recurrent Attention Strategy

![GitHub](https://img.shields.io/github/license/gbup-group/DIANet.svg)
![GitHub](https://img.shields.io/badge/Qrange%20-group-orange)

This repository is the implementation of "Deepening Neural Networks Implicitly and Locally via Recurrent Attention Strategy" [[paper]](https://arxiv.org/abs/2210.15676) on CIFAR-100, CIFAR-10, and STL10 datasets. 

## Introduction

More and more empirical and theoretical evidence shows that deepening neural networks can effectively improve their performance under suitable training settings. However, deepening the backbone of neural networks will inevitably and significantly increase computation and parameter size. To mitigate these problems, we propose a simple-yet-effective Recurrent Attention Strategy (RAS), which implicitly increases the depth of neural networks with lightweight attention modules by local parameter sharing. The extensive experiments on three widely-used benchmark datasets demonstrate that RAS can improve the performance of neural networks at a slight addition of parameter size and computation, performing favorably against other existing well-known attention modules.

<p align="center">
  <img src="https://github.com/Qrange-group/RAS/blob/main/images/arch.png" width="600" height="300">
</p>


## Requirement
Python and [PyTorch](http://pytorch.org/).
```
pip install -r requirements.txt
```


## Usage
```sh
# run ResNet164-RAS on cifar10, 1 GPU
CUDA_VISIBLE_DEVICES=0 python run.py --arch ras --dataset cifar10 --block-name bottleneck --depth 164 --epochs 164 --schedule 81 122 --gamma 0.1 --wd 1e-4
```

## Results
| Dataset | ResNet164   |  ResNet164-RAS   |
|:------:|:--------:|:------:|
|CIFAR10 |   93.45 ± 0.20 | 94.84 ± 0.14 |
|CIFAR100|   74.40 ± 0.34 | 76.74 ± 0.24 |
|STL10   |   83.78 ± 1.25 | 86.15 ± 0.81 |



## Citation

```
@article{Zhong2022DeepeningNN,
  title={Deepening Neural Networks Implicitly and Locally via Recurrent Attention Strategy},
  author={Shan Zhong and Wushao Wen and Jinghui Qin and Zhongzhan Huang},
  journal={ArXiv},
  year={2022},
  volume={abs/2210.15676}
}
```

## Acknowledgments
Many thanks to [bearpaw](https://github.com/bearpaw) for his simple and clean [Pytorch framework](https://github.com/bearpaw/pytorch-classification) for image classification task.

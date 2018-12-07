# torchvision-datasets-mnist
处理好的torchvision.datasets中的`mnist(MNIST, FashionMNIST, EMNIST)`数据集，下载下来可直接使用，方便国内同学。

* [MNIST](http://yann.lecun.com/exdb/mnist/)

* [FashionMNIST](https://github.com/zalandoresearch/fashion-mnist)

* [EMNIST](http://www.itl.nist.gov/iaui/vip/cs_links/EMNIST/)

## 目的
* 众所周知国内的网络的问题；

* `mnist(MNIST, FashionMNIST, EMNIST)`数据集很常用，作为新手可以让你专注搭建模型；

* `pytorch`中的`torchvision.datasets`中的`mnist(MNIST, FashionMNIST, EMNIST)`数据集必须在`torchvision`中做相应处理，生成`pt`文件才能被`torchvision`识别，这就导致即使翻墙下载下来的数据文件，`torchvision`也不识别。

## 使用

1. 下载模型: [百度云](https://pan.baidu.com/s/1d6yS2wrJQcmskzu-O-Zc9Q)

2. 这里面有3个文件夹，分别是`MNIST`, `FashionMNIST`, `EMNIST`。其中包含很多`processed.zip`文件，`processed.zip`解压都有两个文件: `train.pt`和`test.pt`。需要使用哪个数据集就将哪个数据集的`processed.zip`解压并存放在任意路径下例如`/Users/xxx/datasets/MNIST`，注意把`processed`文件夹保留，此时`train.pt`和`test.pt`在`/Users/xxx/datasets/MNIST/processed/`路径下。

3. 例如我们使用MNIST数据集，此时可以导入数据集：

```python
import torchvision
train_dataset = torchvision.datasets.MNIST(root='/Users/xxx/datasets/MNIST/',
                                             train=True, 
                                             transform=transforms.ToTensor(),
                                             download=False)
test_dataset = torchvision.datasets.MNIST(root='/Users/xxx/datasets/MNIST/', 
                                          train=False, 
                                          transform=transforms.ToTensor(),
                                          download=False)
```

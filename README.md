# ECCV4120
The search and train code for `DADA: Dierentiable Automatic Data Augmentation`. The corresponding Paper ID is #4120 in ECCV 2020.

# Environment
The requirements.txt is included in the repository.

For searching:
1. python3.6
2. pytorch1.2
3. numpy
4. scipy

For training:
cd fast-autoaugment and follow the corresponding README.

# Search
The searching script is provided, including CIFAR10, CIFAR100, SVHN, and ImageNet.
```
cd search_relax
sh train_paper.sh

# you can change the hyper-parameters as below:
# GPU=0
# DATASET=reduced_cifar10
# MODEL=wresnet40_2
# EPOCH=20
# BATCH=128
# LR=0.1
# WD=0.0002
# AWD=0.0
# ALR=0.005
# CUTOUT=16
# TEMPERATE=0.5
# SAVE=CIFAR10
```

# Train
The training script is provided, including most experiments of our paper.
```
cd fast-autoaugment
sh train.sh
```

# Genotype
You can find the genotype used by our paper as below:
```
vim fast-autoaugment/FastAutoAugment/genotype.py
```

# Data
You should put the data in ./data as below:
```
./data/cifar-100-python
./data/cifar-10-batches-py
./data/train_32x32.mat
./data/extra_32x32.mat
./data/test_32x32.mat
./data/imagenet-pytorch/
./data/imagenet-pytorch/meta.bin
./data/imagenet-pytorch/train
./data/imagenet-pytorch/val
```

# Model
We will upload the training model in the near future.

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
./data/cifar-100-python.tar.gz
./data/cifar-10-python.tar.gz
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

# Found Policy
## CIFAR10
| Opeartion 1 | Opeartion 2|
-|-|-
sub-policy 0 | (TranslateX, 0.52, 0.58) | (Rotate, 0.57, 0.53)
sub-policy 1 | (ShearX, 0.50, 0.46) | (Sharpness, 0.50, 0.54)
sub-policy 2 | (Brightness, 0.56, 0.56) | (Sharpness, 0.52, 0.47)
sub-policy 3 | (ShearY, 0.62, 0.48) | (Brightness, 0.47, 0.46)
sub-policy 4 | (ShearX, 0.44, 0.58) | (TranslateY, 0.40, 0.51)
sub-policy 5 | (Rotate, 0.40, 0.52) | (Equalize, 0.38, 0.36)
sub-policy 6 | (AutoContrast, 0.44, 0.48) | (Cutout, 0.49, 0.50)
sub-policy 7 | (AutoContrast, 0.56, 0.48) | (Color, 0.45, 0.61)
sub-policy 8 | (Rotate, 0.42, 0.64) | (AutoContrast, 0.60, 0.58)
sub-policy 9 | (Invert, 0.40, 0.50) | (Color, 0.50, 0.44)
sub-policy 10 | (Posterize, 0.56, 0.50) | (Brightness, 0.53, 0.48)
sub-policy 11 | (TranslateY, 0.42, 0.51) | (AutoContrast, 0.38, 0.57)
sub-policy 12 | (ShearX, 0.38, 0.50) | (Contrast, 0.49, 0.52)
sub-policy 13 | (ShearY, 0.54, 0.60) | (Rotate, 0.31, 0.56)
sub-policy 14 | (Posterize, 0.42, 0.50) | (Color, 0.45, 0.56)
sub-policy 15 | (TranslateX, 0.41, 0.45) | (TranslateY, 0.36, 0.48)
sub-policy 16 | (TranslateX, 0.57, 0.50) | (Brightness, 0.54, 0.48)
sub-policy 17 | (TranslateX, 0.53, 0.51) | (Cutout, 0.69, 0.49)
sub-policy 18 | (ShearX, 0.46, 0.44) | (Invert, 0.42, 0.40)
sub-policy 19 | (Rotate, 0.50, 0.42) | (Contrast, 0.49, 0.42)
sub-policy 20 | (Rotate, 0.43, 0.47) | (Solarize, 0.50, 0.42)
sub-policy 21 | (TranslateY, 0.74, 0.51) | (Color, 0.39, 0.57)
sub-policy 22 | (Equalize, 0.42, 0.53) | (Sharpness, 0.40, 0.43)
sub-policy 23 | (Solarize, 0.73, 0.42) | (Cutout, 0.51, 0.46)
sub-policy 24 | (ShearX, 0.58, 0.56) | (TranslateX, 0.48, 0.49)

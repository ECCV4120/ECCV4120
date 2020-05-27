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
Sub-policy | Opeartion 1 | Opeartion 2|
---|---|---
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

## CIFAR100
Sub-policy | Opeartion 1 | Opeartion 2|
---|---|---
sub-policy 0 | (ShearY, 0.56, 0.28) | (Sharpness, 0.49, 0.22)
sub-policy 1 | (Rotate, 0.36, 0.19) | (Contrast, 0.56, 0.31)
sub-policy 2 | (TranslateY, 0.00, 0.41) | (Brightness, 0.47, 0.52)
sub-policy 3 | (AutoContrast, 0.80, 0.44) | (Color, 0.44, 0.37)
sub-policy 4 | (Color, 0.94, 0.25) | (Brightness, 0.68, 0.45)
sub-policy 5 | (TranslateY, 0.63, 0.40) | (Equalize, 0.82, 0.30)
sub-policy 6 | (Equalize, 0.46, 0.71) | (Posterize, 0.50, 0.72)
sub-policy 7 | (Color, 0.52, 0.48) | (Sharpness, 0.19, 0.40)
sub-policy 8 | (Sharpness, 0.42, 0.38) | (Cutout, 0.55, 0.24)
sub-policy 9 | (ShearX, 0.74, 0.56) | (TranslateX, 0.48, 0.67)
sub-policy 10 | (Invert, 0.36, 0.59) | (Brightness, 0.50, 0.23)
sub-policy 11 | (TranslateX, 0.36, 0.36) | (Posterize, 0.80, 0.32)
sub-policy 12 | (TranslateX, 0.48, 0.36) | (Cutout, 0.64, 0.67)
sub-policy 13 | (Posterize, 0.31, 0.04) | (Contrast, 1.00, 0.08)
sub-policy 14 | (Contrast, 0.42, 0.26) | (Cutout, 0.00, 0.44)
sub-policy 15 | (Equalize, 0.16, 0.69) | (Brightness, 0.73, 0.18)
sub-policy 16 | (Contrast, 0.45, 0.34) | (Sharpness, 0.59, 0.28)
sub-policy 17 | (TranslateX, 0.13, 0.54) | (Invert, 0.33, 0.48)
sub-policy 18 | (Rotate, 0.50, 0.58) | (Posterize, 1.00, 0.74)
sub-policy 19 | (TranslateX, 0.51, 0.43) | (Rotate, 0.46, 0.48)
sub-policy 20 | (ShearX, 0.58, 0.46) | (TranslateY, 0.33, 0.31)
sub-policy 21 | (Rotate, 1.00, 0.00) | (Equalize, 0.51, 0.37)
sub-policy 22 | (AutoContrast, 0.26, 0.57) | (Cutout, 0.34, 0.35)
sub-policy 23 | (ShearX, 0.56, 0.55) | (Color, 0.50, 0.50)
sub-policy 24 | (ShearY, 0.46, 0.09) | (Posterize, 0.55, 0.34)

## SVHN
Sub-policy | Opeartion 1 | Opeartion 2|
---|---|---
sub-policy 0 | (Solarize, 0.61, 0.53) | (Brightness, 0.64, 0.50)
sub-policy 1 | (ShearY, 0.56, 0.54) | (Sharpness, 0.67, 0.50)
sub-policy 2 | (AutoContrast, 0.64, 0.50) | (Posterize, 0.49, 0.42)
sub-policy 3 | (Invert, 0.43, 0.62) | (Equalize, 0.30, 0.53)
sub-policy 4 | (Contrast, 0.49, 0.55) | (Color, 0.51, 0.58)
sub-policy 5 | (ShearX, 0.58, 0.50) | (Brightness, 0.56, 0.54)
sub-policy 6 | (Rotate, 0.43, 0.50) | (Contrast, 0.47, 0.42)
sub-policy 7 | (Brightness, 0.51, 0.57) | (Cutout, 0.48, 0.50)
sub-policy 8 | (TranslateY, 0.65, 0.46) | (Rotate, 0.43, 0.46)
sub-policy 9 | (ShearY, 0.41, 0.43) | (Contrast, 0.48, 0.49)
sub-policy 10 | (ShearY, 0.52, 0.37) | (Brightness, 0.43, 0.37)
sub-policy 11 | (ShearY, 0.26, 0.49) | (Posterize, 0.52, 0.56)
sub-policy 12 | (TranslateX, 0.67, 0.38) | (TranslateY, 0.45, 0.42)
sub-policy 13 | (Posterize, 0.64, 0.43) | (Sharpness, 0.63, 0.54)
sub-policy 14 | (Rotate, 0.47, 0.50) | (Sharpness, 0.40, 0.45)
sub-policy 15 | (ShearX, 0.47, 0.46) | (Cutout, 0.58, 0.50)
sub-policy 16 | (Rotate, 0.58, 0.53) | (Solarize, 0.41, 0.43)
sub-policy 17 | (Color, 0.37, 0.44) | (Brightness, 0.52, 0.41)
sub-policy 18 | (TranslateX, 0.49, 0.47) | (Posterize, 0.49, 0.52)
sub-policy 19 | (TranslateY, 0.50, 0.49) | (Solarize, 0.50, 0.42)
sub-policy 20 | (TranslateY, 0.27, 0.50) | (Invert, 0.56, 0.29)
sub-policy 21 | (ShearY, 0.64, 0.57) | (Rotate, 0.49, 0.57)
sub-policy 22 | (Invert, 0.49, 0.55) | (Contrast, 0.41, 0.50)
sub-policy 23 | (ShearX, 0.57, 0.49) | (Color, 0.60, 0.50)
sub-policy 24 | (Rotate, 0.54, 0.53) | (Equalize, 0.52, 0.50)

## ImageNet
Sub-policy | Opeartion 1 | Opeartion 2|
---|---|---
sub-policy 0 | (TranslateY, 0.85, 0.64) | (Contrast, 0.70, 0.47)
sub-policy 1 | (ShearX, 0.69, 0.64) | (Brightness, 0.58, 0.46)
sub-policy 2 | (Solarize, 0.33, 0.53) | (Contrast, 0.36, 0.40)
sub-policy 3 | (ShearY, 0.54, 0.81) | (Color, 0.65, 0.67)
sub-policy 4 | (Rotate, 0.52, 0.28) | (Invert, 0.55, 0.46)
sub-policy 5 | (ShearY, 0.76, 0.55) | (AutoContrast, 0.64, 0.46)
sub-policy 6 | (TranslateX, 0.32, 0.67) | (Sharpness, 0.45, 0.61)
sub-policy 7 | (Brightness, 0.28, 0.54) | (Cutout, 0.29, 0.53)
sub-policy 8 | (TranslateY, 0.26, 0.39) | (Brightness, 0.30, 0.57)
sub-policy 9 | (ShearX, 0.46, 0.62) | (Rotate, 0.51, 0.59)
sub-policy 10 | (TranslateY, 0.63, 0.38) | (Invert, 0.40, 0.33)
sub-policy 11 | (TranslateY, 0.49, 0.32) | (Equalize, 0.43, 0.26)
sub-policy 12 | (TranslateX, 0.31, 0.46) | (AutoContrast, 0.40, 0.00)
sub-policy 13 | (ShearY, 0.57, 0.35) | (Equalize, 0.45, 0.16)
sub-policy 14 | (Solarize, 0.78, 0.61) | (Brightness, 0.57, 0.80)
sub-policy 15 | (Color, 0.75, 0.40) | (Cutout, 0.54, 0.47)
sub-policy 16 | (ShearX, 0.51, 0.67) | (Cutout, 0.37, 0.45)
sub-policy 17 | (TranslateX, 0.68, 0.39) | (Rotate, 0.47, 0.16)
sub-policy 18 | (Rotate, 0.64, 0.55) | (Sharpness, 0.66, 0.80)
sub-policy 19 | (TranslateY, 0.47, 0.75) | (Sharpness, 0.64, 0.52)
sub-policy 20 | (AutoContrast, 0.29, 0.54) | (Posterize, 0.35, 0.70)
sub-policy 21 | (Invert, 0.55, 0.49) | (Equalize, 0.44, 0.76)
sub-policy 22 | (TranslateX, 0.86, 0.29) | (Contrast, 0.41, 0.60)
sub-policy 23 | (Invert, 0.28, 0.45) | (Posterize, 0.42, 0.34)
sub-policy 24 | (Posterize, 0.15, 0.33) | (Color, 0.50, 0.59)


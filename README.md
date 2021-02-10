# Introduction
Greetings to you, stranger! In this repository, you can find exceptionally simple neural multigrid architecture that runs on GPU and does not depend on the matrix of a linear operator. It is concise and allows you to run tons of experiments with simple model problems.

If, by any chance, you are reviewing my paper for IJCNN 2021, you can reproduce all results effortlessly. For the model of interest, use the link to collab below and run on GPU. Otherwise, the training is slow.

In all our models, we use Petrov-Galerkin coarse-grid correction and modified Jacobi iterations as pre- and postsmoothers. Coarse-grid correction and the set of trainable variables can vary.


## Models

### Neural multigrid

+ No serialization. All restriction and smoothing operators are distinct.
+ Coarse-grid correction is an exact matrix inversion.

[![Neural multigrid](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1jxHZ6wBAwiNjDbntiV1pOM264buL57sX)

### U-Net

This part is unique. Here you can find the U-Net preconditioner for a modified Richardson scheme. Look inside for the architecture.

[![U-Net](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Cm5GipQC-90rNdAMJbKG03mhJyd4dv35)

### fMG

+ No serialization. All restriction and smoothing operators are distinct.
+ Two additional convolutions perform the coarse-grid correction.

[![fMG](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Wd0UumKhXUF4MCwdjTEnQrAqfz9MUtti)

### s1MG(s)

+ Serialization of a single layer.
+ Pre- and postsmoothers are being learned. The restriction is a transpose for bilinear interpolation.
+ Coarse-grid correction is an exact matrix inversion.

[![s1MG(s)](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1x4w2UPRyrU8tE8InAr-qN2_HYODDAbJU)

### s3MG(s)

+ Serialization of a three layers.
+ Pre- and postsmoothers are being learned. The restriction is a transpose for bilinear interpolation.
+ Coarse-grid correction is an exact matrix inversion.


[![s3MG(s)](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1qmztUsYv6wSbhkQqXwMhGxI1p6XGBQWJ)

### s1MG(rs)

+ Serialization of a single layer.
+ The restriction operator, pre- and postsmoothers are being learned.
+ Coarse-grid correction is an exact matrix inversion.

[![s1MG(rs)](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1KZSFytiUhMPSOaeuOGmU1dJltjLbUWHZ)

# Introduction
In this repository, you can find exceptionally simple neural multigrid architecture that runs on GPU and does not depend on the matrix of a linear operator. It is concise and allows you to perform a lot of experiments with simple model problems.

If you are reviewing my paper for IJCNN 2021, you can reproduce all results effortlessly. For the model of interest, use the link to collab below and run on GPU. Otherwise, the training is slow.

In all our models, we use Petrov-Galerkin coarse-grid correction and modified Jacobi iterations as pre- and postsmoothers. Coarse-grid correction and the set of trainable variables can vary.


## Models

### Neural multigrid

+ No serialization. All restriction and smoothing operators are distinct.
+ Coarse-grid correction is an exact matrix inversion.

### U-Net

This part is distinct. Here you can find the U-Net preconditioner for a modified Richardson scheme. Look inside for the architecture.

### fMG

+ No serialization. All restriction and smoothing operators are distinct.
+ Two additional convolutions perform the coarse-grid correction.

### s1MG(s)

+ Serialization of a single layer.
+ Pre- and postsmoothers are being learned. The restriction is a transpose for bilinear interpolation.
+ Coarse-grid correction is an exact matrix inversion.

### s3MG(s)

+ Serialization of a three layers.
+ Pre- and postsmoothers are being learned. The restriction is a transpose for bilinear interpolation.
+ Coarse-grid correction is an exact matrix inversion.

### s1MG(rs)

+ Serialization of a single layer.
+ The restriction operator, pre- and postsmoothers are being learned.
+ Coarse-grid correction is an exact matrix inversion.

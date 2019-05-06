# 1.Unsupervised Person Re-identiﬁcation: Clustering and Fine-tuning

## Abstract

In this paper, we consider the more pragmatic issue of learning a deep feature with no or only a few labels. 
We propose a progressive unsupervised learning (PUL) method to **transfer pretrained deep representations to unseen domains**.

PUL iterates between

1) pedestrian clustering 

2) ﬁne-tuning of the convolutional neural network (CNN) to improve the original model trained on the irrelevant labeled dataset.

Since the clustering results can be very noisy, we add a selection operation between the clustering and ﬁne-tuning.

## I. I NTRODUCTION

The contributions of this paper are three-fold: 

1) Among the early efforts, we propose an easy-to- implement unsupervised deep learning framework for large- scale person re-ID.

2) We are the ﬁrst to discover the underlying relation between clustering and self-paced learning and integrate the self-paced learning paradigm into the unsupervised learning regime. This learning strategy facilitates PUL to extract faith- ful knowledge from highly unreliable clustering results in learning.

3) Extensive experiments on three large-scale datasets indi- cate that our method noticeably improves the re-ID accuracy in the cross-dataset evaluation.


## II. R ELATED W ORKS

### A. Deeply Learned Person Representations

Generally speaking, from the perspective of model, classiﬁcation models as used in image classiﬁcation and siamese models that use image pairs  or triplets  are two types of CNN models that are commonly employed in re-ID.

At the beginning when the training datasets are not big enough, such as VIPeR [28] that provides only two images for each identity, the siamese model dominates re-ID community. As the scale of re-ID dataset becomes large, such as Market-1501 [2], the classiﬁcation model is widely employed. A survey of re-ID can be viewed in [1].


In this paper, we adopt the baseline identiﬁcation model, named “ID-discriminative Embedding” (IDE) in [29].

### B. Unsupervised Person Re-ID

### C. Self-paced Learning

In the human learning process, knowledge is imparted in the form of curriculum and organized from easy to difﬁcult. Inspired by this process, the theory of Curriculum Learning (CL) [41] is proposed to accelerate the speed of convergence of the training process to a minimum. The main challenge of CL is that it requires a known separation to indicate whether a sample in a given training dataset is easy or hard. To alleviate this deﬁciency, self-paced learning [22], [42], [43] embeds easiness identiﬁcation into model learning. The learning prin- ciple behind SPL is to prevent latent variable models from getting stuck in a bad local optimum or oscillating. Then SPL is widely used in weakly-supervised and semi-supervised learning. For example, Zhang et al. [44] integrate self-paced learning into multi-instance learning for co-Saliency detection.

In this paper, we utilize SPL to select reliable samples to ﬁne tune the original model. If we consider the labels of the samples from the unlabeled dataset as latent variables, our method also belongs to latent variable model. Therefore, it is necessary to avoid getting stuck in bad optimums or oscillating using SPL.

## III. P ROGRESSIVE U NSUPERVISED L EARNING

Firstly, we ﬁne tune the basic model by an irrelevant labeled dataset, which is stored as the original model. This step is also called original model initialization. 

Secondly, the original model is used to extract feature for the samples from the unlabeled dataset. The data instances are clustered and selected to generate a reliable training set. 

Thirdly, the original model is ﬁne tuned by this reliable training set. 

Lastly, we use the new model to extract feature, and the second and third steps are repeated until the scale of the reliable training set becomes stable.


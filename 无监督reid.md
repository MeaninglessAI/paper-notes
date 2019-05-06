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



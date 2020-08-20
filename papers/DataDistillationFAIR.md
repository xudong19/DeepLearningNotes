[Data Distillation: Towards Omni-Supervised Learning](https://arxiv.org/pdf/1712.04440.pdf) [CVPR 18]
---------------	

__TL;DR__: The key idea is to use a pretrained model to generate (pseudo-) labels for super large scale unlabeled data availabel online so that the massive amount of data and psuedo-labels can be leveraged to improve the model performance.

__keywords__: Semi-supervised learning, Distillation, Omni-supervised learning

__Resources__: [[Github](https://github.com/facebookresearch/detectron)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The key idea of this paper is to use a pretrained model to generate pseudo labels to large unlabeled dataset. Then
a new model can be trained with the large unlabeled dataset and pseudo labels to generate better performance.
* The key is how to generate pseudo label? On paradigm is to use multiple pretrained models to do model ensemble. Instead,
the paper used test time augmentation (named as multi-transform inference in this paper) to assemble better predictions.
* This paper seems a bit primitive given the very recent progress in this area. A more sophisticated approach (presumably better)
can be found in [NoiseStudent](./noisestudent.md)

Key ideas and technical details:
------
* See above comments.

Other noteworthy points:
------
* The data augs used in this paper include scaling and horizontal flipping. 
* As the focused task is keypoint detection, the ensemble method used is to average the final heatmaps in the last layer of the network. 
* On top of that, the confidence score threshold selection is based on the data distribution in the labeled dataset. Concretely, the threshold is chosen to make the average number of gt instances in the unlabeled dataset is the same as that in the labeled dataset.
* Even the unlabeled data is in different distribution with the labeled data, the proposed approach can still improve the model's performance. 
* In the batch sampling, the paper force each batch contains at least a certain percentage of true gt data.
* In the re-training stage, the pseudo-gt and true-gt are treated equally. 




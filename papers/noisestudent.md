

[Self-Training With Noisy Student Improves ImageNet Classification](https://arxiv.org/pdf/1911.04252.pdf) [CVPR 20]
---------------	

__TL;DR__: With a trained model (maybe trained in a small labeled dataset) and very large unlabeled dataset, we can use the trained model to generate pseudo-label and then train a student model. After a few iteration, the student model will outperform the original model by a large margin.

__keywords__: Semi-Supervised, Knowledge-Distillation, Pseudo-Label

__Resources__: [[Github](https://github.com/google-research/noisystudent)] [[ProjectPage]] 

__Other Notable Info__: [[Review1](https://syncedreview.com/2020/02/13/google-brain-cmu-semi-supervised-noisy-student-achieves-88-4-top-1-accuracy-on-imagenet/)] [[Review2](https://medium.com/@nainaakash012/self-training-with-noisy-student-f33640edbab2)]  

<br/>    

General Comments:
------
* The paradigm seems perfectly fit into the scenario that you have a small labeled dataset and a large unlabled dataset. And the result shown looks very promising to achieve good result by making use of the unlabled data. 


Key ideas and technical details:
------
* The key to keeping improving at each iteration is to introduce "noise" in the student model, which are dropout, [stochastic depth](https://arxiv.org/pdf/1603.09382.pdf), and [RandAugment](https://arxiv.org/pdf/1909.13719.pdf).
* The student model has to be equal-or-larger than the teacher model
* The paradigm can iterate itself until the benefit diminishes to zero

Other noteworthy points:
------
* The paper also find the method works better with data filtering and balancing. Data filters means remove those data with low predicted confidence score from teacher model. Data balancing means for image cls task, duplicate those images in under-represented classes so that the number of data instances across classes are balanced. 
* With more data (unlabeled) used for training, not only the accuracy of the model is improved, but more importantly, the model demonstrate to be more robust to image corruptions and out-of-distribution data.

<!-- Screenshots:
------ -->


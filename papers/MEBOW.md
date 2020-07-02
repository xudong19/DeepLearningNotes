
[MEBOW: Monocular Estimation of Body Orientation In the Wild](http://openaccess.thecvf.com/content_CVPR_2020/papers/Wu_MEBOW_Monocular_Estimation_of_Body_Orientation_in_the_Wild_CVPR_2020_paper.pdf) [CVPR 20]
---------------	

__TL;DR__: Create a human body orientation dataset (540K images) with fine-grained labels (72 bins in 360&deg;). The papers shows HBOE task can also benefit HPE task.

__keywords__: HBOE, dataset, HPE, Pedestrian

__Resources__: [[Github]()] [[ProjectPage](http://infolab.stanford.edu/~wangz/project/imsearch/BODY/CVPR20/)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* An creation the biggest HBOE data so far with diverse scene. 
* The dataset can benefit both the HBOE task and other human pose estimate task.
* The paper shows adding HBOE task loss to netwokr can also benefit the performance of 3D HPE. This indicates different fine-grained pedestrian related tasks can benefit each other.

Key ideas and technical details:
------
* The creation of the dataset. The rigorous definition of human pose orientation. 
* The idea of improving HPE task with HBOE task.

Other noteworthy points:
------
* The paper find [HRNet](https://github.com/leoxiaobin/deep-high-resolution-net.pytorch) as backbone is more effective than ResNet.
* For the orientation regression, the paper use the gaussion-smoothed cls as in centernet's heat map regression. And the paper also note, the standard cls loos (normal cross engropy loss) cannot converge in their case. 

<!-- Screenshots:
------ -->


[Generalized Focal Loss: Learning Qualified and Distributed Bounding Boxes for Dense Object Detection](https://arxiv.org/pdf/2006.04388.pdf) [NeurIPS 20]
---------------	

__TL;DR__: This paper attempt to refine the cls branch to incorporate the IoU/centerness loss, and also refine the loc branch
to the regression uncertainty in the general form. The proposed refinements all leads to the formulation of cls loss and hence can be improved by using some forms of focal loss. In consequence, the paper further developed a general form of focal loss.


__keywords__: OD

__Resources__: [[Github](https://github.com/implus/GFocal)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The key motivations behind this paper is to improve the cls and loc branches respectively. Both improvements lead to using
focal loss to improve the "general classification problem". 
* To its very general extent, the focal loss is can be applied to any cls problems, with the property of overcoming the class imbalance problem.
* This method achieved new SOTA in coco.

Key ideas and technical details:
------
* The consolidation of cls branch and the extra IoU/centerness bit in loc branch. 
* The regression uncertianty in the general form.
* The generalized form of focal loss for any cls problem.

Other noteworthy points:
------
* 




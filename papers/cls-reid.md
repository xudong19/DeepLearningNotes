[In Defense of the Classification Loss for Person Re-Identification](https://arxiv.org/pdf/1809.05864.pdf) [CVPR 19]
---------------	

__TL;DR__: This paper design a person ReID framework featured by channel groupping and multi-branch 
strategy to make full use of classification loss as optimization superivision. 

__keywords__: Person-ReID, Pedestrian

__Resources__: [[Github]] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* Between the main two lines of research in optimization losses, namely metric learning loss and cls loss, the drawback of metric learning loss is that it can only make use of a small portion of training sample due to hardware limit, and the drawbach of cls loss lies in the discrepancy of network in training and inference. 
* This paper come up with two noval modules, multi-branching and channel grouping, to overcome the shortcoming of cls loss and to learn more discriminative representations. 


Key ideas and technical details:
------
* The multiple-branching mechanism to lessen the importance of fc layer in optimizing cls loss, and hence to promote more discriminative learned representations
* The channel grouping mechanise to enable more diverse discriminative representations for different aspects of object features.


Other noteworthy points:
------
* The introduction part is very informative for newbies to this field. Person ReID is very
challenging in real application due to the dramatic variation in deployment environment. As a result,
it is more critical to learn very discriminative feature representations, which means smaller intra class distance and larger 
inter class distance.
* One line of reseach is to learn local features for each part of human body, which opens possibility to partition global feature into groups as oppose (and analogy) to partitioning human into parts. This idea is one of the innovations in this paper.
* The other line of research is to use metric learning combined with hard minning strategy to replace the old-fashioned cls loss. 
This paper argues that the inferior performance of the cls loss comes from the fact that during training, there is an additional fc layer which does not exist in inference to perform the mapping from representation to cls loss. This paper argues that the discrepancy between training and inference is the root cause for the inferiority of cls loss. On the other hand, the paper argues that the cls loss has the advantage of making use of all the training samples in contrast to very limited small number of effective samples in metric learning paradigm. Therefore, this paper devise a multi-branch fc layer mechanism to enhance cls loss. 




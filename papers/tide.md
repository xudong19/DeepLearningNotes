[TIDE: A General Toolbox for Identifying Object Detection Errors](https://arxiv.org/pdf/2008.08115.pdf) [ECCV 20]
---------------	

__TL;DR__: This paper develops a really nice toolbox to help analysis the source of detection error. The tool only accepts 
the lists of gt json files and pred json files, and thus both model-agnostic and dataset-agnostic. 

__keywords__: OD

__Resources__: [[Github](https://github.com/dbolya/tide)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The tool is bot generic in the sense of model-agnostic and dataset-agnostic, and detailed in the sense of reporting errors from different parts. 
It should be very useful in practical OD systems.


Key ideas and technical details:
------
* The breakdown of the error sources into six categories: cls, loc, both cls and loc, duplicate, background, and missed gt.
* Instead of computing error progressively, which leads to biases to the order, this paper computer error separately. 
* This tool can also do error breakdown based on specific attributes, and even the contribution of the error on specific attributes to the overall errors.



Other noteworthy points:
------
* The sum of the errors from all sources plus the performance is not added up to 100%
* There are quite many labeling errors in mainstream OD datasets, e.g. coco, which might be the reason why SOTA are slowly stagnating recently. 





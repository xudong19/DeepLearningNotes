
[It’s Not All About Size: On the Role of Data Properties in Pedestrian Detection](http://openaccess.thecvf.com/content_ECCVW_2018/papers/11129/Rasouli_Its_Not_All_About_Size_On_the_Role_of_Data_ECCVW_2018_paper.pdf) [ECCVW 18]
---------------	

__TL;DR__: This paper explore the effect of dataset diversity (different weather, pedetrain apprearance, etc.) on the pedestrain detection performance. 

__keywords__: Dataset-Diversity, Pedestrian-Detection, 

__Resources__: [[Github]] [[ProjectPage]] 

__Other Notable Info__: [[JAAD Dataset](https://github.com/ykotseruba/JAAD)] 

<br/>    

General Comments:
------
* There are two primariy takeaways from the paper: 1. Algorithms perform differently if being tested under different data attributes. 2. Algorithm performs better (better generalization ability and etc.) when trained under diverse dataset. 3. Different algorithms perform very differently on different dataset and has different generalization ability.


Key ideas and technical details:
------
* Label each data object with attributes (different weather, pedetrain apprearance, etc.) such that algorithms can be evaluated on each specialized dataset.
* With the specialized dataset, one can study algorithms based on different training dataset and different evaluation dataset.

Other noteworthy points:
------
* The network could learn to localize handbags instead pedestrians if many pedestrains present are with handbags. 
* The diversity of training dataset leads to better gneralization of pedestrian detection across datasets.
* Carefully curated diverse dataset can reduce the need for large valume of training data.
* Explicitly learning pedestrain attributes can help with pedestrain detection.

<!-- Screenshots:
------ -->


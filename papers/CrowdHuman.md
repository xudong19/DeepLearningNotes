[CrowdHuman: A Benchmark for Detecting Human in a Crowd](https://arxiv.org/pdf/1805.00123.pdf) [ArXiv 18]
---------------	

__TL;DR__: The construction of a pedestrian dataset in a large scale and focused on crowed scene only. 

__keywords__: Pedestrian, Dataset

__Resources__: [[Dataset](https://www.crowdhuman.org/)]

<!-- __Other Notable Info__: [Dataset](https://www.crowdhuman.org/) -->

<br/>    

General Comments:
------
* A large-scale and crowd scene dataset is constructed. The average number of persons per image is 22.6 and the average of pairwise overlap between two persons (> IoU 0.5) is 2.4. The dataset contains 15K images.
* This dataset demonstrates very good generalization property. algorithm trained on this dataset, without any fine-tuning, outperforms algorithms trained on other dataset, when being evaluated on other datasets (other datasets include [CalTech](http://www.vision.caltech.edu/Image_Datasets/CaltechPedestrians/), Brainwash (taken down), [CityPersons](https://bitbucket.org/shanshanzhang/citypersons/src/default/)).
* When fine-tuned on other dataset, the performance is even further boosted. 

Key ideas and technical details:
------
* Very crowd dataset. The distinction of full bbox, visiable bbox, and head bbox.


Other noteworthy points:
------
* The evaluation metric, using mMR (the average log miss rate over false positives per-image ranging in [0.01, 1])
* The two-stage detector (Faster RCNN) constantly outperforms one-stage detector (RetinaNet). Visible bbox detection is the easiest ones and head and full body detection are harder.




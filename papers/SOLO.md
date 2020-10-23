[SOLO: Segmenting Objects by Locations](https://arxiv.org/pdf/1912.04488.pdf) [ECCV 20]
[SOLOv2: Dynamic, Faster and Stronger](https://arxiv.org/pdf/2003.10152.pdf) [NeurIPS 20]
---------------	

__TL;DR__: The key idea is to distinguish instances by location (and size with FPN), with the important observation that
objects distribute on different locations. The other trick is to using classification (of instance category for each pixel) 
to approach the location prediction problem, to enable the use of a fixed number of channels. Thoes ideas result in the 
final two-branches design proposed in the papers.

__keywords__: IS

__Resources__: [[Github](https://github.com/WXinlong/SOLO)] [[Github](https://github.com/aim-uofa/AdelaiDet/)]

__Other Notable Info__: 

<br/>    

General Comments:
------
* The key idea is to use location to distinguish instances, which deviates from the conventional top-down or bottom-up 
paradigms.
* The introduction of the decoupled mask branch start is essentially assembling mask from base "prototypes", which resembles
the the [YOLACT](YOLACT.md). Counte-intuitively, the decoupled mask branch not only improve the algorithm speed, but also 
even the performance.
* The SOLOv2 paper takes the assambly idea even further, instead of using simple multiplication or coefficient, more sophisticated
assambly method (convolutions) is used.
* From another perspective, convolutions based decoupled method (SOLOv2) is equivalent to the mask head in vanilla SOLO head, 
but delay the materialization of the final mask prediction to the inference stage and only materializing those positive 
sample (on the fly and only do so when needed), and hence unnecessary computations are spared and speed are improved.
* The framework is the latest SOTA. It is both accurate, fast, and most importantly, simple. It will be widely adapted. 

Key ideas and technical details:
------
* The Matrix NMS is both more accurate and faster than traditional NMS
* In the mask branch, all the feature maps from FPN are first consolidated into one unified feature map. 
* Dice loss is better than BCE and Focal Loss in the binary mask prediction part (the mask branch).
* The FPN and the CoordConv can improve the performances to a large extent.



<!-- Other noteworthy points:
------ -->



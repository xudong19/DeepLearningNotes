[Towards Real-Time Multi-Object Tracking](https://arxiv.org/pdf/1909.12605.pdf) [ECCV 20?]
---------------	

__TL;DR__: This paper devise a module to do metric learning and detection together in one network.

__keywords__: MOT, Metric-Learning

__Resources__: [[Github](https://github.com/Zhongdao/Towards-Realtime-MOT)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* This paper devise a joint learning frame (a network head) to achieve the metric learning (object embedding) along with object detection.
* The gain of the joint learning frame is mainly about the speed. 

Key ideas and technical details:
------
* Adding a new regressing branch for box embedding along with normal box cls and box regression branches. 
* Two technical challenges for such a network head, one is how to have effective metric learning loss, 
the other is how to balance different losses. The technical solutions are to use Cross-Entropy loss and use uncertainty-based
multi-tasking learning weight ([link](https://arxiv.org/pdf/1705.07115.pdf)). 


Other noteworthy points:
------
* Using object retrival as a way to evaluate the learned embedding.
* Extensive experiments to compare different metric learning losses and loss weighting strategies. 
* The good summary of research development in this area, which are mainly concentrated in three focuses: 
    1. model the assocaition problems as optimization problem on graphs (e.g. [GNN3DMOT](GNN3DMOT.md))
    2. model the association process by an end-to-edn neural network (e.g. [DeepMOT](DeepMOT.md))
    3. novel tracking paradigm other than tracking-by-detection (e.g. [CenterTrack](CenterTrack.md))




[SoDA: Multi-Object Tracking with Soft Data Association](https://arxiv.org/pdf/1912.02424.pdf) [arXiv 20]
---------------	

__TL;DR__: This papers targets at the problem of the lack of global reasoning about the learned embeddings during the 
association process. The remedy developed in this paper is to 1. use transformer module to process the learned embedding across recent frames, 2. learn an additional occulusion embedding
so that during the tracks can active associate to the occulusion. This paper is from Google and Waymo

__keywords__: OD

__Resources__: [[Github]] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The key innovation of the paper is to apply the transformer module to enable the reasoning among the embedding vectors.
* The attending nature of the transformer module is what makes it really shine at gobal reasoning in many CV tasks.
* A side innovation of the paper is to deliberately contrive an occlusion embedding so that each track can active choose to 
be occluded if it is the case. (I do not understand how the occlusion embedding is learned, though)
* Transformer is really hot now in CV area. 


Key ideas and technical details:
------
* The way to encode the sequence order infomation into the transformer module seems to be critical for the performance. 
* The similarity score threshold during the association is really painful to select. The introduction of the occlusion embedding greatly ease the pain. 

<!-- Other noteworthy points:
------
* 
*  -->




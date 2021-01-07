[Visual Odometry Revisited: What Should Be Learnt?](https://arxiv.org/pdf/1909.09803.pdf) [ICRA 2O]
---------------	

__TL;DR__: This paper revisits the visual odometry in deep learning age. With all the information that is possible to be extracted by deep learning, this paper proposes a best learning strategy.

__keywords__: Visual-Odometry

__Resources__: [[Github](https://github.com/Huangying-Zhan/DF-VO)] [[WebPage](https://huangying-zhan.github.io/publication/2019-dfvo)]

<!-- __Other Notable Info__: [Charles R. Qi](https://web.stanford.edu/~rqi/) -->

<br/>    

General Comments:
------
* In classic SLAM, there are generally two paradigms to solve visual odometry: pixel matching based methods, and direct method. The pixel matching based method can be further categorized into 2D-2D matching (eight-point algorithm) and 2D-3D matching (Perspective-n-Point (PnP) algorithm). The direct method, without knowing the matching info (sometimes even not knowing key points), tackles the problem as an optimization problem by minimizing the photometric loss (maybe with other auxiliary losses) to solve the matching and essential matrix as a whole. 
* While in the deep learning age, we are able make neural networks to learn many things, e.g. pixel depth (lifting 2D to 3D), optical flow (2D-2D matching), direct pose estimate (as commonly seen in MonoDepth algorithms e.g. [PackNet](https://arxiv.org/abs/1905.02693)), etc, this paper try to propose the best strategy to compute most accurate visual odometry.
* I find the choices of "what to be learnt" in this paper is very interesting. The paper trust better the key point matching based method then the pose info directly predicted from neural networks. 
* The depth prediction from the depth network also exhibits scale ambiguity. But this unknow scale is more consistent across frames and hence can be used to calibrate the result from eight-point algorithm. The depth of the final output in this paper is still lack of an unknown factor relative to true depth.

Key ideas and technical details:
------
* The paper proposes to mainly rely on the 2D-2D matching info from the 2D optical flow result, and the depth info from a depth prediction network, and furthermore using eight-point algorithm to solve pose info. The depth predicted from depth network is used to estimate scale factor and hence remove the scale ambiguity.  
* When eight-point algorithm is not applicable under scenarios such as pure rotational movement or very small translational movement, the papre propose to using depth prediction to lift the key points to 3D so that PnP algorithm can be used to solve pose info.

Other noteworthy points:
------
* The depth loss is consisted of: photometric loss (combined with SSIM) (overall optimize the min of each patch), edge-aware depth smoothness loss (make depth prediction smooth across one image), depth consistency loss (depth prediction consistent across frames).
* 



[Simple Online and Realtime Tracking with a Deep Association Metric](https://arxiv.org/pdf/1703.07402.pdf) [ICIP 17]
---------------	

__TL;DR__: This paper devise a module to do metric learning and detection together in one network.

__keywords__: MOT, Motion-Prediction

__Resources__: [[Github](https://github.com/nwojke/deep_sort)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* In current mainstream tracking-by-detection paradiam, the key problem regarding tracking is how to do object association
across frames. There are primarily two general ideas we can employ to approach data association, namely motion prediction and 
appearance representation. On top of this, we can use track manager to maintain a set of tracks to stablize each track. 
This paper laid fully develop these ideas and laid the general framework of the paradigm for this line of tracking methods
* With this framework in place, the tracking problem is reduced to how to obtain better motion prediction and better appearance 
representation problem.

Key ideas and technical details:
------
* The general framework for the tracking-by-detection paradigm. 

Other noteworthy points:
------
* The Kalman filter to manage each track.
* The [mahalanobis distance](https://en.wikipedia.org/wiki/Mahalanobis_distance) to compose the affinity matrix from the predicted 
Kalman states and newly arrived obvervations. One nice thing about this mahalanobis distance is that it comes with a confidence level with this distance metric.
* The binary masks to be coupled with the affinity matrices to mask out those impossible matrix entries.
* The cascade model from a tracking manager.  




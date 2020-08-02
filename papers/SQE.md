[SQE: a Self Quality Evaluation Metric for Parameters Optimization in Multi-Object Tracking](https://arxiv.org/pdf/2004.07472.pdf) [CVPR 20]
---------------	

__TL;DR__: This paper proposes a metric that can approximate the quality of tracking results without kowning the 
ground-truth.

__keywords__: MOT

__Resources__: [[Github]] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* This paper gain insight from the empirical observation that good tracking results tends to
have a single-peak shape of distribution for its "inter" and "intra" distances, and hence make use of
this observation to devise a metric to evaluate the performance of tracking result without knowing the ground-truth
* In the details analysis, the papers shows that the proposed metric correlates with the well-established MOT tracking
metrics (MOTA, IDF1, etc.) very well.
* This self-evaluation method can help with algorithm hyper-parameter adjustment in concrete real-time applications.
* Even though very empirical and lack of theorectical support, this algorithm seems to be accurate enough based on the
evaluation in this paper, and very practical in real-time applications.

Key ideas and technical details:
------
* The paper derive itself from a key observation that immaculate trackings tends to give rise to 
single-peak distributions for the intra and inter tracking distance, while when ID switches happen, it will always produce
multiple peaks in the distributions. 
* The proposed self quality evaluation algorithm use a two-class Gaussian mixture model to fit the calculated
distance distributions and furthermore access the performance based on the fitted Gaussian mixture model. 


<!-- Other noteworthy points:
------
 -->




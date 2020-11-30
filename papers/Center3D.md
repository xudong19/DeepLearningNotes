[Center3D: Center-based Monocular 3D Object Detection with Joint Depth Understanding](https://arxiv.org/pdf/2005.13423.pdf) [arXiv 20]
---------------	

__TL;DR__: This paper improves the [CenterNet-based](https://arxiv.org/pdf/1904.07850.pdf) Mono3D architecture with two primary designs. 
(i). regress the 3D center (the center of 3D bbox projected onto the image plane) from the heatmap peak of the 2D center. (ii). More accurate
object depth prediction based on DepJoin and LID.

__keywords__: Mono3D, OD

__Resources__: [[Github]] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The mismatch between projected 3D bbox center and the 2D bbox center restricts the CenterNet performance on Mono3D.
* The discrepancy of performance between LiDAR based methods and monocular image based methods lies in the depth estimate.
* This paper propose two depth estimation mechanisms to advance the performance.

Key ideas and technical details:
------
* This paper still uses the 2D bbox center as the keypoints for object localization (for the heatmap generation branch).
* The projected position of the 3D bbox are also regressed as 3D offset (in image plane) in addition to the 2D offset.
* This paper borrows the idea of [DORN](https://arxiv.org/pdf/1806.02446.pdf) and improve it with linear-increasing-discretization (LID) for depth regression.
* The key idea of DORN is to discretize depth into many bins (80 bins), and each bin will make a prediction whether the depth beyond the bin or not. During inference, voting-alike means is used to 
make final depth prediction. 
* On the other hand, this paper also extend the [Depth-Map-Prediction](https://papers.nips.cc/paper/2014/file/7bccfde7714a1ebadf06c5f4cea752c1-Paper.pdf) with depth 
prediction from both ends, to improve the accuracy in the far-away range.
* The key idea of Depth-Map-Prediction is to regress the -log(depth) instead of the depth itself, which can improve the performance of close-by range due to the larger effective feature value range. 

Other noteworthy points:
------
* For the heatmap prediction, this paper propose using Reference Area in place of single point regression. This method resembles the centerness regress design in [FCOS](FCOS.md)



[PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation](https://arxiv.org/abs/1612.00593)
======

__Publication__: CVPR 2018

__Affiliation__: Stanford

__Author__: [Charles R. Qi](https://web.stanford.edu/~rqi/)

__Group__: [Leonidas Guibas Lab in Stanford](https://geometry.stanford.edu/member/guibas/)

__Sources__: ([Github](https://github.com/charlesq34/pointnet)) ([Paper](https://arxiv.org/abs/1612.00593)) ([Website](http://stanford.edu/~rqi/pointnet/))

<br/>    

__Rating__: 5/5
<br/> 

General Comments:
------
* The architecture is simple but very effective. 
* The auther first sums up what properties the networks should pocess and then design operations accordingly.
* The result is pretty good. Beats the SOTA by a large margin.
* Have great potential to be used in self-driving cars

Main Innovations:
------
* The thought process for network design; and the design of the network
* THe empirical and theoretical analysis on the stability and efficiecy
* Proposed the concepts of critical points.

Worth-noting:
------
* The properties of the operations to process the cloud points: Unordered; INteraction among points; INvariance under transformations
* Concepts about the critial points for deciding clasification
* The feature transformations block
* Did time and space complexity analysis
* Not only coordinates but also other features can be added to points and processed by the network

Pictures:
------
![Image1](../img/pointnet_net.png "Architecture")


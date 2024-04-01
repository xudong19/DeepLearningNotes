[Query-Centric Trajectory Prediction](https://openaccess.thecvf.com/content/CVPR2023/papers/Zhou_Query-Centric_Trajectory_Prediction_CVPR_2023_paper.pdf) [CVPR23]
---------------	

__TL;DR__: blablablablabla

__keywords__: TP

__Resources__: [[Github](https://github.com/ZikangZhou/QCNet)] 

<!-- __Other Notable Info__: [blabla](blabla) -->

<br/>    

General Comments:
------
* This is a followup work from HiVT
* The raw features of all scene elements are represented in its local frame.
* Factorized attention enables cache and reuse of previously computed encodings
* recurrent decoder design improves prediction quality
* Additional "anchor-based" prediction layer, further predictin the offset for refinement,
improves the prediction performance.


Key ideas and technical details:
------
* All the coordinates, including the raw coordinate features and the relative
position transformation, are transformed into Fourier space and further processed
with the Fourier features.
* Map elements are passed through self-atten. The self-atten, just like agent-agent
interaction, also includes coordinate transformation features.


Other noteworthy points:
------
* All the raw features of scene elements are in self-centric polar coordinates, and then
the coordinates are transformed into Fourier space and the Fourier features are concated
with semantic attributes and then passed into MLP to obtain initial encodings.
* The lane line representation is in polyline (polyline * points * features),
attention based pooling is used to reduce the `points` dimension.
* 

Questions:
------
* To get the inital encoding for each agent and each lane, does it require
to use the raw features neighboring elements, or only use the raw features
of the element itself. If it's the latter, since it's self-centric, all the
positional features seems gone.

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->


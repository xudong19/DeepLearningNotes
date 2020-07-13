[Tracking Objects as Points](https://arxiv.org/pdf/2004.01177.pdf) [ECCV 2020 ?]
---------------	

__TL;DR__: The paper is an natural extension to [CenterNet](https://arxiv.org/pdf/1904.07850.pdf). The model output two more channels doing object location offset prediction on top of orginal CenterNet model, and the result proves to be very effective. 
__keywords__: MOT, Detection

__Resources__: [[Github](https://github.com/xingyizhou/CenterTrack)] 

__Other Notable Info__: [My Own Slides](https://docs.google.com/presentation/d/1JHyoTX1ckNho-dv0-jzNAPNyzmtWEd6_lNtBFC1DwGk/edit#slide=id.p)

<br/>    

General Comments:
------
* This paper propose a novel way to do detection and tracking altogether, instead of the mainstream approach as tracking by detection. 
* The method is a nature extention of CenterNet. The key is to make the network to regress the location offset relative to the objects in previous frame.
* The data augmentation which plays a big role to make the model work as expected is so aggressive to the extent that even using static images for training can yeild very decent tracking performance.
* The tracker is a local tracker, meaning that it only consider two adjacent frames. The paper argues that local tracker is enough to generate good tracking result 

Key ideas and technical details:
------
* For the input, the model takes in the current frame image (time t), previous frame image (time t-1), and the heatmap of previous frame image. And for the output, other than the normal object detection related channels, two additional channels are used to decode the association of objects between current frame and previous frame. As a result, the detection and tracking are addressed simultaneously and interdependent to each other.


Other noteworthy points:
------
* Using public detection result can even degrade the algorithm's performance due to the interwinding of detection and tracking
* Data augmentation (image scaling and translation) really matter. With it, the model can acheive very good result even without real video data for training; without it, the model cannot even converge. 

<!-- Screenshots: -->
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->


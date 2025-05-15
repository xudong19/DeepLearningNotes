[Geometric Retargeting: A Principled, Ultrafast Neural Hand Retargeting Algorithm](https://arxiv.org/pdf/2503.07541)
---------------	

__TL;DR__: unsupervised method to learn a retargetting mapping function.

<!-- __keywords__: bla-bla -->

<!-- __Resources__: [[Github](blabla)]  -->

__Other Notable Info__: [Project Page](https://zhaohengyin.github.io/geort/)

<br/>    

General Comments:
------
* Four learning objectives (losses):
    - motion preservation: meaning that preserve the movement direction of each
    fingertip to be the same, to give an intuitive feeling to operator
    - C-space coverage: robot C-space needs to be fully covered. 
    - high flatness: it means the reponse sensitivity is the relatively stable and uniform across
    the C-space.
    - Pinch correspondance: when a human finger does a pinch, the robot hand should also do
    a pinch.
    - Collision-free
* This is unsupervised learning. This is the most amazing part. Otherwise, it will be
very very hard to generate human-robot GT pairs. Good correspondance just emerges!
* Each finger is individually learned. Every finger learns an independent retargetting network.

Key ideas and technical details:
------
* Converting each criterion into a loss function.
    - motion preservation: make sure they move the same direction
    - C-space coverage: randomly sampling in the two spaces, minimizing the Chamfer distance.
    This is the most unintutive loss, as we are minimizing the distance between random pairs.
    But becasue P_r (robot C-space points) are randomly sampled, so only if when the learned network
    can cover the whole robot C-space, can the loss be minimized.
    - high flatness: make the second order gradient (not the network gradient) of the mapping function
    to be zero.
    - Pinch correspondance: when two fingertips are very close (e.g. distance < 5cm), the mapped robot hand fingertips need to be very close as well
    - Collision-free: 1. use collision checker (e.g. moveit) to generate collision/non-collision data 2. train a collision classifier. 3. use the classifer to supervise the model to generate another loss.



My thoughts
------
* human fingurs are coupled in some way as well. Shall we train a network to train all the fingers
as a whole?
* All the losses are like self-consistency losses, unsupervised, but correspondance just emerges. 
* Adding some paired GT data and applying SFT might can help further. We can collect some calibration
gestures, like finger fully open, fully close, finger touching, etc.
* How to incorporate tactile sensing and hand-object relationships into the re-targetting could be
the next frontier.
* it seems that there is no good evaluation benchmark to evaluate the results. 

Other noteworthy points:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->


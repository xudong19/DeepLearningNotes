[GR00T N1: An Open Foundation Model for Generalist Humanoid Robots](https://arxiv.org/pdf/2503.14734)
---------------	

__TL;DR__: Nvidia gr00t humanoid robot training

__keywords__: bla-bla

__Resources__: [[Github](blabla)] 

__Other Notable Info__: [Project Page](blabla)

<br/>    

General Comments:
------
* 
* 

Key ideas and technical details:
------
* latent action from internet video data: VQ-VAE model, with discretized embedding
from codebok. The encoder (from video to latent embedding) is taken as inverse dynamic
model, and the discretized embeddings are taken as the latent actions, and using the same
flow-match loss during training, and treated as [LAPA embodiment](LAPA.md).
* simulation trajectory: data augmentation, moving object location, moveing init
pose, etc. Using DexMimicGen to apply those automated data augmentation.
* neural trajectory: use video generation model (world model) to imagine/generate
new scenarios based on real initial frames. The world model is fine-tuned using the teleop data.
 - question: how to generate trajectories? Is it genie3 alike world model that's
 conditioned on actions?

Other noteworthy points:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->


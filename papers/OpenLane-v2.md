[OpenLane-V2: A Topology Reasoning Benchmark for Unified 3D HD Mapping](https://arxiv.org/pdf/2304.10440.pdf) [NerIPS 23]
---------------	

__TL;DR__: A new dataset, that detects lane centerline connectitivity in 3D, traffic elements (traffic lights and road markings), and the topology between centerlines and centerlines, and topolgy between centerlines and traffic elements. The topology is represented as edges in a graph.

__keywords__: 

__Resources__: [[Github](https://github.com/OpenDriveLab/OpenLane-V2)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* This is a very difficult perception task for several reasons:
    - centerline is invisible in the camera images. The model needs to reason between visible lane boundaries
    - 3D locations is needed for lane centerlines, which is very diffcult even for a human perception system.
    - The model needs to have an extraordinary understanding of the 2D image to 3D BEV coorespondings to be able to associate centerlines.
    - The model needs to have a exceptionally accurate scemantic understandings of the whole scene to be able to associate traffic lights in 2D and centerlines in 3D.
* Two general approaches to tackle the challenging task:
  - end-to-end: in the long run, this is the best option. On the encoding side, the model needs to fuse all cameras images, and fuse temporal embeddings. On the decoder side, the model needs to predict lane boundaries, topologies (as proposed in the paper), and moving objects all in one network. For the topologies task, the model needs to represent the information as a list of sequences and predict them auto-aggresively.
    - Pros: in the long turn, end-to-end is the best option for performance. It lends itself into an end-to-end autonomous driving system.
    - Cons: it's infeasible to launch onboard, unless using distillation. 

  - Divide and conquer: break down the task into 3D lane centerline detection, and traffic lights detection. Then use another network to reason its topologies. It requries smaller network.
    - Pros: every components has a managable task and well-established body of work to leverage.
    - Cons: Upstream task must achieve high accuracy for downstream task to be working.


Key ideas and technical details:
------
* The way to encode the sequence order infomation into the transformer module seems to be critical for the performance. 
* The similarity score threshold during the association is really painful to select. The introduction of the occlusion embedding greatly ease the pain. 

<!-- Other noteworthy points:
------
* 
*  -->




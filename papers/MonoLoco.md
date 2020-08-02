
[MonoLoco: Monocular 3D Pedestrian Localization and Uncertainty Estimation](https://arxiv.org/pdf/1906.06059.pdf) [ICCV 19]
---------------	

__TL;DR__: The localization of pedestrain in 3D with single mono camera image. This is acheive by leveraging both 3D human joints detection, normalized image plane, and uncertainty estimates. The result is STOA in both nuscene and KITTI.

__keywords__: MonoLoco, Pedestrian, Uncertainty

__Resources__: [[Github](https://github.com/vita-epfl/monoloco)] [[ProjectPage](https://www.epfl.ch/labs/vita/research/perception/monoloco/)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The primary idea of this paper is to infer the pedestrain distrance from mono image based on pedetrain keypoint detection. The assumption is that the distance scales (not necessarily linearly) with distances among human joints. 
* Even though the paper does not do alabtion study on uncertainty estimate, I think the incorporation of uncertainty estimate (both aleatoric and epistemic uncertainties) is what makes the distance estimate achieve such good performance. 


Key ideas and technical details:
------
* From the human joints estimate result to final distance estimate, the paper only use simple MLP.
* The aleatoric uncertainty is based on Lapace Distribution (L1 loss) and the epistemic uncertainty is dropout inference
* They first project the coordinates of joints into normalized plane and translate the coordinate into the center. Then regress the norm of the projecting ray vector (\sqrt(x**2+y**2+z**2)) instead of the only the depth (the assumption is that the dimension of a person is only relevant to the norm of vector. I am not sure if there is right. My feeling is that it should be only relevant to the depth (z coordinate).)

Other noteworthy points:
------
* The ablation study shows Laplace loss (uncertainty-introduced L1 loss) is better than Gaussian loss (uncertainty-introduced L2 loss).
* The paper incorporate camera intrinsics to project into normalized camera plane. Then the paper assume all persons has the same height, and thus can calculate the expected task error. 

<!-- Screenshots:
------ -->


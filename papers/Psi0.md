[Ψ₀: An Open Foundation Model Towards Universal Humanoid Loco-Manipulation](https://arxiv.org/abs/123456)
---------------	

__TL;DR__: a new foundation model that's pretrained using human video data (800 hours) and using an hand-centric action representation (task space representation). The performance is way over the previous generation of foundation models like GR00t and PI (π) series, which are trained on robot data alone.

<!-- __keywords__: bla-bla -->

__Resources__: [[Github](https://github.com/physical-superintelligence-lab/Psi0)] 

__Other Notable Info__: [Project Page](https://psi-lab.ai/Psi0/)

<br/>    

General Comments:
------
* pretraining on egocentric human video (800 hours):
    - finger movement (3D per fingertip * 10 = 30 DoF) + 9D wrist vector * 2 (task space actions) = 48 DoF
    - only predict the next action, horizon is 1 step, using VLM model, no action expert module
    - FAST tokenization to distretize the actions
* post-training on teleop robot data (30 hours):
    - freeze VLM part, only train action expert module from scratch
    - 15 DoF for lower body + 28 DoF for upper body (arm 7 DoF + hand DoF) = 43 DoF (higher-end G1 EDU configuration)
    - action expert model directly predict 8 DoF lower-body and 28 DoF upper body (36 DoF in total).
    - RL controller take in 8 DoF lower body command to control the 15 DoF lower body

* evaluation:
    - 80 teleop trajectories per task, further fine-tuning the model
    - 10 rollout per trial and compare success rate
    - 

Key ideas and technical details:
------
* even pretraining is to learn 48 DoF hand wrist action, which is wildly different from post training action, the learned representation in pretraining is still very critical
* multi-modal diffusion transformer (MM-DiT) seems better than naive DiT as action expert
* async inference is worth noting. real-time chunking with [training-time chuncking](https://arxiv.org/pdf/2512.05964) to solve the discontinuity problem in async inference. the model prediction is conditioned on proceding clean actions
* the whole body control 
* the very last fine-tuning stage is better done on a single task.
* TeleOp is done through one VR headset (PICO4U), a pair of wrist trackers, and a pair of manus gloves, with IK retargetting algorithms.

My thoughts:
------
* the comparison is a bit unfair to pi0.5, as the robot is unitree g1 humanoid, while pi0.5 is pretrained for bimanual manipulator
* pre-training models beat training from scratch models by a big margin, which shows fine-tuning foundation model is very important for robot application companies.


Questions:
------
* the paper did not show cross-embodiment generalization of the Ψ₀, which is very important for a foundation model. The action expert is suceptible for overfiting to the G1 action space.
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->


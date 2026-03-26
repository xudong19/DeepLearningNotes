[World Action Models are Zero-shot Policies](https://arxiv.org/pdf/2602.15922)
---------------	

__TL;DR__: It's a new World action model paradigm. Compared to VLA, it can learn from diverse non-repetitive data, and generalize to unseen tasks so well that you can prompt the robot to do almost anything.

__keywords__: bla-bla

<!-- __Resources__: [[Github](blabla)]  -->

__Other Notable Info__: [Project Page](https://dreamzero0.github.io/)

<br/>    

General Comments:
------
* 14B robot foundation model, the largest so far, compared to less 5B size of PI0.6 model
* It's essentially a video model with minimal additional parameters: state encoder, action encoder, and decoder. The backbone is [WAN](https://github.com/Wan-Video/Wan2.1?tab=readme-ov-file)
* autoregressive (single-direction) future video frames and actions prediction
* asynchronous closed-loop exection:
    - old way: inference first, and then exectuion; new way: inferece for the future while executing the previous inference result
    - 48 steps at 30 HZ (1.6 sec per chunk)
* other speedup techniques: system-level, implementation-level, model-level, which result in 38X speedup

Key ideas and technical details:
------
* data recipe (all teleop robot data of AgiBot G1 for both pretraining and posttraining):
  - Pretraining
    - 500 hours, 22 environment
    - each episode is around 5mins, comprised of 42 subtasks
    - also use Droid dataset
    - note that the pretraining dataset does not contain repetive data, which means repeating the same task multiple times
  - Posttraining
    - 33 hrs of shirt folding
    - 12 hrs of fruit packing
    - 40 hrs of table bussing
* evaluation
 - evaluate on AgiBot G1
    - pretrained model, 10 in-distribution tasks 
 - evaluate on post-trained tasks
    - 10 rollouts per task

* pretrained model zero-shot generalization (pretrained model out of box deployment)
    1. in-distribution tasks, but unseen objects and envirment
            - perform better then other pretrained VLA models (e.g. GR00T, or PI)
    2. unseen tasks (10 new tasks)
            - VLA model sometime fail entirely, while WAM (world-acton-model) can make meanful progresses
 - conclusion: pretrained WAM (world-acton-model) can learn from non-repetitive, diverse data, and show zero-shot generalization

* post-trained model performance
 - figure 10 shows WAM either on-par or outperform VLA models

* cross-embodiment transfer (based on the pretrained model)
 - new tasks, learning from new embodiment data, video only
 - 9 unseen tasks, 8 demos per tasks, 20 mins for YAM, 12 mins for human
 - co-trained on 1:1 mix with pretraining data for 10k steps


* few-shot new embodiment adaptation
    - post train the model on yam arm and 11 tasks, with 30 mins data (55 trajectories)
    - it performs very well and show strong language following ability

* interactive prompting
    - because the training dataset covers such a broad range of tasks, the model is robust enough, anyone can just prompt it to do any tasks, and the model can somehow do some interesting stuff. this is really unprecedented and show very strong generalization compared to other models.


discussions:
------
* Can the WAM model master high-precision tasks? It might require very high quality world model, which is very data-consuming to train
* High DOF robot hand might be more amenable embodied form for WAM, due to its close similarity with humans and the WAM will mostly pretrained on human data in the future.

Questions:
------
* i cannot tell if the model make use of the wrist camera images or not. nowdays, the wrist camera is very standard and important sensing. 
* the model requires a GB200 for inference and with a lot of low level speedup optimizations, it will be very chanllenging to further scale up the model for now.

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->


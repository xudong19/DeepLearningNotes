[EgoVerse: An Egocentric Human Dataset for Robot Learning from Around the World](https://arxiv.org/pdf/2604.07607)
---------------	

<!-- __TL;DR__: blablablablabla

__keywords__: bla-bla

__Resources__: [[Github](blabla)]  -->

__Other Notable Info__: [Project Page](https://egoverse.ai/)

<br/>    

General Comments:
------
* two questions for egocentric data: 
    - embodiment gap and scaling behavior
    - dataset are one-off, scattered, and non-standardized
* consortium-scale study: cross-lab, cross-embodiment (three embodiments)
* conclusion: 
    - co-training robot with human data leads to clear improved performance
    - benefit of scaling human data depend on the aligned human-robot data, where human dan robot data share tasks semantics and scene context
    - human data diversity:
        - Increasing demonstrator diversity improves robustness to unseen human embodiments
        - increasing scene diversity improves generalization to novel environments, particularly under limited data budgets.
* EgoDB:
    - cloud based processing pipeline
    - unified storage format
    - web-based viewer
    - sync filtered subsets of dataset
* robot data: 
    - 150 - 300 for each task, 6 tasks in total

* in domain human data: 
* EgoVerse-A: in-domain human data: the same task defintion, just different embodiment (human), different sensing (wearable video), different excution (human movement)
* EgoVerse-I: out-domain human data: 2000 tasks, 240 scenes, and 2087 dmonstractors

Key ideas and technical details:
------
* coordinate frame: the current time (t=0) head frame
* encoding:
    - image processed by ResNet-18 to get embeddings
    - proprioceptive inputs processed by MLP to get embeddings
    - finally tokenized into a shared space by learned query attention
* BC co-training loss

My thoughts:
------
* as shown in Figure 9: the more robot resembles human, the more helpful the human data
* variables in data: hardware, scenes, environment, tasks, objects, demonstractor, number of episodes. diversity vs scale, In-domain vs Out-of-domain, robot vs human, aligned or not, etc.
* variables in model: pre-train, co-train, etc.

Questions:
------
* compared to egoscale
    - this feels very limited scope. less data, less tasks
    - training paradigm feels different as well, ego-scale is pretrain using human, mid-train using human-robot aligned, and post-train using robot. this is co-train instead. 
    - egoverse feels more suitable for small-scale training. 
    - the study is also more thorough, distingushed from in-domain human data and out-of-domain data
    - the conclusion in this paper is also aligned with egoscale. in pretraining, you want diverse data. in mid and post training, you want to align human data with robot data in the same task, scene, and even similar trajectory excution.

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->


[HoMMI: Learning Whole-Body Mobile Manipulation from Human Demonstrations](https://arxiv.org/pdf/2603.03243)
---------------	

__TL;DR__: UMI with ego-centric vision and mobile robot form (adding the mobility function and long range navigation tasks).

<!-- __keywords__: bla-bla -->

<!-- __Resources__: [[Github](blabla)]  -->

__Other Notable Info__: [Project Page](https://hommi-robot.github.io/)

<br/>    

General Comments:
------
* key chanlenge: action space gap and visual gap between data collection device (UMI system) and the robot system
* the most impressive part of the paper: it can actively look around to locate the object of interest (e.g. a trolley behind and 6 meters away and move towards). this paper combines the navigation tasks with manipulation tasks so well without any robot data needed.

Key ideas and technical details:
------
* embodiment-agnostic vision representation: 3D visual representation for ego-centric observation. Use embodiment-agnostic coordinate frames (i.e. end-effector frame) and remove the human body and arm from the observation to mitigate visual distribution shift.
* relaxed head action representation: use 3D look-at point to bridge the gap between 6-DoF human head and 2-DoF robot head.
* contraint-aware whole body control: [mink](https://github.com/kevinzakka/mink) based controller to solve whole body IK problem.
* action space design: all the observation and actions are represented in the gripper-centric frame.
* model: simple diffusion policy model. past history: 2 steps
* they tested on long-range delivery tasks for 6 meters navigation and the destination is intially out of sight. It really highlight the usefulness of active head vision.

My thoughts:
------
* UMI approach design principle:
    - scalability: fast, intuitive, portable, low-cost, in-the-wild data collection
    - transferability: overcome visual and kinematic gap from human to robot
    - whole-body coordination: precise end-effector tracking and effective active perception
* where ego-centric helps: tasks requiring search, navigation. where wrist can help: tablescape manipulation tasks
* visual data representation: there is a big visual gap in the ego-centric data between human collector and the robot deployment. To mimimize this, the paper applied multiple techniques: 1. using RGBD camera to get 3D point cloud representation; 2. mask out human body to reduce visual gap. 3. using [Adapt3R](https://www.pair.toronto.edu/Adapt3R/) to geometry-aware token representations. The paper also did ablation study to show that RGB only data has larger visual mismatch than RGBD data. It seems RGBD camera for ego centric top view is a good choice for humanoid robot design.

Questions:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->


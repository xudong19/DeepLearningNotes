[HiVT: Hierarchical Vector Transformer for Multi-Agent Motion Prediction](https://openaccess.thecvf.com/content/CVPR2022/papers/Zhou_HiVT_Hierarchical_Vector_Transformer_for_Multi-Agent_Motion_Prediction_CVPR_2022_paper.pdf3) [CVPR22]
---------------	

__TL;DR__: A translation and rotation invariant network, which leads to the following QCNet work.

__keywords__: trajectory-prediction

__Resources__: [[Github](https://github.com/ZikangZhou/HiVT)] 


<br/>    

General Comments:
------
* The encoder is facterized.
* The initial features of every agent at every time (a_i_t) and of every lane segment
is self-centric. The relative relationship is captured by coordinate transformation
parameters, processed by MLP.


Key ideas and technical details:
------
* At every time, use the central agent as query, and the neighboring agents as
KV. The time dimension fold into batch.
* For every agent, think it as a sequence of data and apply self-atten to it just like BERT,
The agent dimension fold into batch.
* Use the spatial-temporal-fused feature for every agent to query nearby map
lane segments to get the final feature per agent.
* In the final global interaction encoder module, every agent is used to query
the features of all other agents; and the all other agents features includes the
coordinate transformation information.
* The Laplace distribution is used to model the multi-modal property.


Other noteworthy points:
------
* The order of processing is agent-agent interaction (in one frame), 
agent lane interaction, and temporal interaction.
* Note that in the agent-agent interaction, there is a sigmoid layer applied for weighted residual average.
* DETR like decoder. Trajectory matching uses minADE trajectory.


<!-- Screenshots:
------
![Image1](../img/pointnet_net.png "Architecture") -->


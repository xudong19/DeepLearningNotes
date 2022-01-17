[Perceiver: General Perception with Iterative Attention](https://arxiv.org/pdf/2103.03206.pdf) [Deepmind]
---------------	

__TL;DR__: A general network architecture for all perception tasks based on transformer model.

__keywords__: Transformer, network architecture

__Resources__: [[Github](https://github.com/deepmind/deepmind-research/tree/master/perceiver)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The network is based on the transformer. The key idea is to use cross-attention to replacy self-attention at the beginning stages.
* The adventage of the cross-attention compared to the self-attention is its memory effiency. 
* The size of the latent space serves as an information bottleneck, enabling the scalability to very large input data. 
* The cross-attention encoding process is iterative, to overcome the potential information loss from the bottleneck.

Remaining questions:
------
* Is it still applicable in a self-supervised manner?
* When doing predictions in the late stage, is any decoder needed? Any QKV alike architecture needed?
* How the query (latent space) and the input data are positionally encoded?

Key ideas and technical details:
------
* The latent space embeddings are the query and the input data are the keys and values.

Other noteworthy points:
------
* 


[Perceiver IO: A General Architecture for Structured Inputs & Outputs](https://arxiv.org/pdf/2107.14795.pdf) [Deepmind]
---------------	


__TL;DR__: A general multimodal and multi-task network architecture.

__keywords__: Transformer, multimodal, multi-task

__Resources__: [[Github](https://github.com/deepmind/deepmind-research/tree/master/perceiver)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* This is an natural extension to the Perceiver paper. 
* Built upon the encoder model in the Perceiver, this paper adds the decoder model to make any types of desired predictions. 
* The predictions are based from output queries. Predictions from different modilities (tasks) are distinguished by the output query. The output query are learned during training.

Remaining questions:
------
* Is the output query positionally encoded? 


Key ideas and technical details:
------
* The whole network is divided into three main stages: encode, process, and decode. 
 - The encode is cross attention between latent space (query) and the input data (key-value).
 - The process is self-attention QKV structures.
 - The decode is cross attention between output query (query) latent space (key-value).

Other noteworthy points:
------
* 
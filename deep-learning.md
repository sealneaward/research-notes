# Deep Learning Research Papers

### [Recurrent Neural Network Regularization](https://arxiv.org/pdf/1409.2329.pdf)

#### Problem Statement
- Dropout is an excellent regularization method that can used to strengthen neural networks and prevent overfitting.
- In it's current application, dropout regularization performs poorly on recurrent nueral networks due to adding noise recursively.

#### Short Summary
- Researchers avoid the current issues with dropout in LSTM's by applying dropout in between the LSTM layers.

#### Strong Points
- By applying dropout in the non-recursive connections allows the LSTM units to keep memory from previous units.
- Figure 4 provides an example of how the application of dropout can prevent overfitting with the generative outputs.

#### Weak Points
- Allthough this paper assumes prior knowledge of RNN's and LSTM, it would still be beneficial to explain word perplexity and entropy in the evaluation step.

#### Questions
- At what depth does dropout regularization become irrelevant and the model starts to overfit?

#### Future Work
- How would this framework apply batch normalization?
- Would introducing batch normalization have the same effect as dropout?

### [Detecting events and key actors in multi-person videos](https://arxiv.org/pdf/1511.02917v2.pdf)

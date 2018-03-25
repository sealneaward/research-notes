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

- [Data](http://basketballattention.appspot.com/)

#### Problem Statement
- Computer vision has expended available information from picture data. Deep learning methods have allowed for object detection and image segmentation, where location information about objects in interest can be derived.
- Object detection for a single object in a video is very easy. Once multiple objects are introduced in a single picture, the task of detecting objects becomes much more difficult.

#### Short Summary
- Using one model for attention, and another model for detection and classification, the researchers use RNN's to detect actions and players in NCAA video feeds.
- Using attention based modeling, events can be tracked as points of attention, which can be used by a seperate RNN to classify events based on their attention formations.
- The model can identify which players are responsible for the event that is identified.

### [Soccer Field Localization from a Single Image](https://arxiv.org/pdf/1604.02715v1.pdf)

#### Problem Statement
- The NBA has employed state of the art video tracking systems with multiple cameras to track and identify players across an entire game. Although effective, this method is extremely costly for non-professional teams to implement.
- Using just single images, the methods proposed in the paper use deep learning to localize positions of a soccer field in a single image onto a 2D plane.

#### Short Summary
- Vanishing points are intersections of otherwise parallel lines, but meet in preojection because of the angle of the image taken.
- From the vanishing points, a grid can be made from intersections of the parallel lines that run through the vanishing points. Each box or shape on the field has corresponding locations on the grid, based on the vanishing points.
- The field is projected from four rays that originate from two separate vanishing points. These rays produce cross ratios that can be used to inference position based on the apparent rays. This produces a projection matrix H, which represents the perception of the field over the actual birds-eye view of the field.
- Along with lines projected along the vanishing point matrix, shapes can be placed within the matrix as well. Circles canbe parameterized in a matrix based on inner and outer quadrilaterals.
- Using the vanishing ray matrix, cross ratios between points and lines identified in the image can be used to transform the points into locations within the matrix, and identify other unseen points based on the cross matrix ratios.
- A segmentation network is trained to classify pixels to belong to vertical, horizontal, circles, grass, or outside of the field.
- The loss function that the learner trains on the projected grid by comparing field and non field cells.

#### Strong Points
- The research introduces the accuracy metric for localization of Intersection over Union.
- The researchers define their grass potential function within their energy maximization as one of semantic segmentation, which maximizes the observed grass in an image vanishing matrix and minimizes the grass observed outside of a field.
- The line potential function is also defined as a segmantation problem, when the semantic functions tries to maximize the segmented line positions against the ground truth lines identified.
- To find the dimensions of the field projection matrix, all of the potentials are optimized via branch and bound. To find the potentials of grass, both an upper bound field (largest possible field) representing the maximum amount of grass and a lower bound field are created. Line potentials are bound
- The grass segmentation was strengthened with fine tuning the CNN with annotated examples to show grass and non grass pixels, even though some of the fans would be wearing shirts that would be confused with grass pixels.

#### Weak Points
- Localization methods compared are driven by the researchers and comparisons are not made to methods conducted outside of the research group.

#### Questions
- Have you compared the Intersection Over Union to other localization methods, like ones that use reference ppoints to build the projection matrix?

#### Future Work
- Look to provide projection information of moving objects (players) to get a full description of the movement in game.


### [Auto-Encoding Variational Bayes](https://arxiv.org/pdf/1312.6114.pdf)
#### Problem Statement
- How can we perform efficient approximate inference and learning with directed probabilistic models whose continuous latent variables and/or parameters have intractable posterior distributions?
- Using Stochastic Gradient Ascent, the paper can yield an unbiased estimator of a posterior distribution from a random initial encoded sample using a variational approximator.

#### Short Summary
- By using auto-encoding in a neural network, parameters for a recognition model can be maximized for generating a posterior distribution.  As the variational parameters learn, so do the generative parameters in order to create more realistic post distributions.
- Given a sample variable `x`, a condensed representation is formed as an encoding `z`. The encoding is formed from a distribution of possible codes that are most likely to recreate the initial sample of `x`. From the condensed representation, an approximate posterior distribution is formed and copmared to the true distribution.
- Minibatches are used for training and updating parameters of the variational and the generative models.


#### Strong Points
- Because the KL divergence between the approximate and the true posterior distributions can never be negative, lower bounds are formed from both variational and generative model parameters.
- The reconstruction error from the encoding is approximated through training in minibatches.
- Based on the KL divergence, the variational parameters can be regularized to ensure that the approximate distribution is as close as possible to the ground truth.
- Neural networks can be easily applied to create coded representations and adversarial posterior distributions, where Gaussian distribution parameters can be updated through an optimization process of computing gradients of the lower bound estimator.
- The VAE is compared to the wake-sleep distribution approximation methods.

#### Weak Points
- The authors did not explain why there was such a huge improvement when comparing the VAE with the Wake-Sleep methods for the Frey Face dataset.

#### Questions
- Why is there such an improvement for VAE with Frey Face, but not MNIST?

#### Future Work
- Revisit the comparisons with newer generative models, such as GANs.


### [Trajectory Clustering via Deep Representation Learning](http://chaozhang.org/files/papers/ijcnn17.pdf)
#### Problem Statement
- Current methods for trajectory clustering often rely on comparison metrics that are used for distance based clustering models.
- They do not rely on space and time when comparing trajectories.
- The methods proposed allow for time and space consideration.

#### Short Summary
- In the proposed methods, a sliding window approach is used to extract a set of behaviour features sampled from movement descriptions.
- The windows are used as sequence input for a seq2seq encoding problem.
- From training a seq2seq model, the model tries to reconstruct the behaviour descriptions used as input.
- The learnt embeddings are then used as input to standard clustering algorithms like k-means.

#### Strong Points
- The paper provides a simple architecture, but very strong and innovative approach to an old problem using seq2seq embedding.
- Instead of having gigantic inputs sequences, behaviour features(like speed, rate of turn) at each window is extracted.

#### Weak Points
- It might be interesting to see what exactly the results would look like in a pure unsupervised setting as well as comparing the clustering results with true labels.

#### Questions
- How many different setups of the seq2seq model did you use?
- Would attention based seq2seq modelling show any improvement.

#### Future Work
- Would be intersting to see another comparison with the Bezier curve method explored in Bornne's work in 2017.

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

#### Strong Points
-

#### Weak Points
-

#### Questions
-

#### Future Work
-

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

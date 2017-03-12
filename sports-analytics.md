# Sports Analytics Research Papers

### [Pointwise: Predicting Points and Valuing Decisions in Real Time with NBA Optical Tracking](http://www.lukebornn.com/papers/cervone_ssac_2014.pdf)

#### Problem Statement
- Individual skills can be easily measured by analysts to seek effecient players in a sought after skill.
- There is no definate method presented for analysts to measure and observe the decision making skill of players.

#### Short Summary
- By using expected posession value (EPV) for each posession observed, the proposed method can evaluate the outcomes of the decision made by the expected number of points scored.
- Using the spacial configurations of all players on the court, as well as the ball, the EPV score can be calculated.
- The authors implement a competing risk model that uses the spacial formation of all the players in order to determine the probabilities of passing or shooting the ball.
- EPV can be shown in real time in a stock graph to show impact of decisions made as they are made.

#### Strong Points
- Using EPVr to compare replacement player decision ability is a great way to show invividual impact from a player's decision making.

#### Weak Points
- The research does not present how drives to the hoop are evaluated as EPV vs a jump shot at the drive starting location. The jump shot is easy to determine the EPV value from. But with no derivation on this specific event, the EPV representation in Figure 1 is confusing for the drive to the basket.

- The framework only attributes the ball handler with decision making and contributing to EPV. Realistically, all players involved during a posession should be attributed with increasing or decreasing EPV value. An example would be setting an off-ball screen to get a shooter open. Just because someone passed the ball to the open shooter doesn't mean that they should be entirely attributed with the increase in EPV.

#### Questions
- Would adding turnovers as posession probabilities be beneficial in getting more accurate EPV values? An example would be not passing to a center that is heavily covered as the turnover probability would be high, decreasing the EPV of the center.

#### Future Work
- Now that defensive matchups and defensive intensity is tracked in real time during a posession, how much would this data make an impact on determining EPV? Would the model become simpler and less computationally expensive.

### [To Crash or Not To Crash: A quantitativer look at the relationship between offensive rebounding and transition defense in the NBA](http://www.sloansportsconference.com/wp-content/uploads/2013/To%20Crash%20or%20Not%20To%20Crash%20A%20quantitative%20look%20at%20the%20relationship%20between%20offensive%20rebounding%20and%20transition%20defense%20in%20the%20NBA.pdf)

#### Problem Statement
- Based on a coach's rebounding strategy during a game, tranitional defense and offensive rebounding can be greatly impacted.
- TV analysts often misrepresent these strategies in their commentary, referring to transition points and offensive rebounding rate as an indication of which strategy is being employed.
- This paper analyzes two rebounding strategies to see how the two different approaches affect both offensive and defensive efforts.

#### Short Summary
- Using SportVU data, the research presented determines each offense player's rebounding intention. Using positioning of player when the shot is taken, and when the ball hits the rim, players who crash and players that retreat can be determined.
- Using the crash index and the retreat index, comparisons can be made to see the correlation of teams that have higher crash index vs retreat index to the offensive rebounding rate of that team.
- Retreat index and crash indexes are also correlated with net gain. The net gain can be determined from a team's offensive rebound probability and the opposing team offensive rebounding probability as a metric of points gained/lost from a rebound.
- Retreating is expanded to show the impact of neutralization of the opponent's offense by closing out players as they transition.


#### Strong Points
- The research shows the impact retreating has on eliminating points lost during transition defense and shows that retreating does not have much effect on long possessions at all. This is likely due to longer posessions allow teams to settle into defensive positioning regardless of how the posession started with a fast break or not.
- The research expands the anlaysis behind getting back on defense by emphasizing the importance of threat neutralization when setting up on other end of court. Threats are defined to be players in areas of the court that are typically high FG% areas for them.


#### Weak Points
- Allthough pointed out for further analysis, it would be good to include features on the players that are crashing or retreating to see how different player types affect rebounding probabilities and transition defense.
- Allthough many of the metrics calculated are easy to understand, it would be more professional to include formulas for each new metric derived.

#### Questions
- Could there be more analysis done with threat neutralization to see how teams neutralize threats that are more damaging in transition (ie. Lebron James)? The threat neutrlization only looks at regions of high interest, instead of looking at specific fast breaks to see which players should be neutralized and where.

#### Future Work
- This analysis should be done on a full range of teams and should expand the offensive rebounding analysis to look at specific players that contribute to offensive rebounds more than others. Just because 3 guards try to get a rebound doesn't mean that they will get the ball. A rebounding center like Andre Drummond should be valued more than a standard player in this analysis.

### [Deconstructing the Rebound with optical Tracking Data](http://www.sloansportsconference.com/wp-content/uploads/2012/02/108-sloan-sports-2012-maheswaran-chang_updated.pdf)

#### Problem Statement
- Without optical tracking data, defining relationships for offensive rebounding becomes very difficult.
- As SportVU data was introduced, relationships between shot location and rebound locations can be investigated, as well as finding optimal locations for players to move to in order to optimize their chances of obtaining an offensive rebound.

#### Short Summary
- Offensive rebounding is higly correlated with the area of the court that the ball ends up in after the ball bounces off the rim. Both in the restricted area, and outside of the three point line produce high probabilities of getting an offensive rebound.
- Offensive rebounding is also correlated with the origin of the shot itself. Shots that occur close to the basket are more likely to have rebounds located close to the basket, so there is a decent chance of grabbing an offensive rebound. Shooting from outside the three line increases the chance of getting an offensive rebound compared to a mid range shot.
- Using spacial data of the players and the ball at the time of the rebound occuring, models can predict the team that get's the rebound 87.5% of the time.

#### Strong Points
- The rebound location analysis really stresses that most rebounds occur within a defined radius and that increasing offensive rebounding probabilities would involve crashing that specific area.                                                                                                                                   

#### Weak Points
- The research suggests that three point shots give greater run-outs, but do not follow through with this suggestion. This analysis would be easy to do, as the analysis primarily depends on the time the rebounded ball spends in the air and modelling the distributions of the rebound locations of both mid range and three point shots.
- Allthough the prediction model is easy to visualize, there is not proper equation presented to represent the data that is used in the SVM prediction.

#### Questions
- Would adding ball velocity and other player velocities to and of the anlaysis be effective in increasing the accuracy of the team rebounding prediction model?

#### Future Work
- Now that deep-learning research has exploded in the last 4 years, would it be possible to extend this research and use an LSTM model to approach predicting rebound locations and ball trajectories based on the full (or partial) directory of the initial shot?
- It would be interesting to look into how define boxing out and how boxing out directly affects rebounding probabilities.

### [The Three Dimensions of Rebounding](http://www.sloansportsconference.com/wp-content/uploads/2014/02/2014_SSAC_The-Three-Dimensions-Of-Rebounding.pdf)

#### Problem Statement
- Rebounding statistics have been very one dimensional before the introduction of SportVU data. The only tracked metrics were the type of rebound and to which player got the rebound.
- Using SportVU data, researchers give insight into the timeline of a rebound, develop metrics for the rebound timeline, and use the metrics to evaluate a player's true rebounding ability.

#### Short Summary
- Crashing the boards and boxing out players is part of positioning to get into a location on the floor to increase to likelihood of getting a rebound after a missed shot.
- The timeline of a rebound is dependant on positioning, hustle, and conversion of opportunities.
- The key to positioning is based on the real estate occupied and evaluated based on Voronoi tesselations that put point value to areas of the floor.
- The Voronoi tesselations can have real estave value based on the likelihood of a rebound ocurring in the area based on the shooting location on the floor (distributions of rebound locations based on shooting zone basic).
- When looking at crashing, the changing real estate value of the space occupied by a player can indicate the intuition to crashing the boards.
- In order to properly measure hustle, one can look at rebounding opportunities (closest player to ball once the ball is below 10ft) earned and compare the opportunities against total field goals missed.
- Conversion can be obtained by dividing the number of rebounds obtained by the number of opportunities had.

#### Strong Points
- By comparing real estate at time of shot and time the ball hits the rim can introduce bias towards wings and guards that do not occupy expensive real estate at the time of the shot. Even though centers and forwards are more likely to get these offensive rebounds, their crash index would indicate a lack of effort towards crashing, when compared to other players. The authors saw this bias and subtracted the raw regression value from the initial positioning of the player at the time of the shot. This is essential positioning over replacement player that starts in the same region.


#### Weak Points
- There are no real expecations presented in the analysis.
- The real estate evaluation using Voronoi tesselations should be given a proper definition with an equation.

#### Questions
- Can you use these three main rebounding factors to predict which player/team gets the rebound?
- Can Positioning be extended to intuition, where players can be measured on how well an individual predicts the location of the rebound, instead of just driving straight to the net?

#### Future Work
- The authors should look to determine whether positioning of rebounds is a property of skill or luck.
- The acutal ability of boxing out a player should be explored at length to see volume of blocking out player and effeciency of the blocking out as it converts to rebounding percentage.

### [Predicting Shot Making in Basketball using Convolutional Neural Networks Learnt from Adversarial Multiagent Trajectories](https://arxiv.org/pdf/1609.04849.pdf)

#### Problem Statement
- Predicting whether a shot goes in has many deep dependancies that rely on several spacial features.
- Hand crafting features for predicting shot success can be somewhat tasking, and important features in floor spacing can be ignored.
- To best represent the various spacial dependancies of shot success, visualizations can be made of the possession to predict from.

#### Short Summary
- Using player trajectories, a convolutional neural network can be applied to predict shot success over a section of a possession.
By combining features engineered that cannot be represented in the visualizations, the authors combine a conv net and a feed forward network to get the best results

#### Strong Points
- Instead of using player defined positions (PG, SG, etc) player channels are representative of their roles. To determnie roles, they use a representation based on player ineractions within temporal space.
- The authors showed how important the 11 channel trajectories were by comparing the CNN with three different channel 'options' (Grey, RGB, 11 channel).
- Multiple models were compared to show the improvements of the combined CNN and FNN had over the baseline.
- Using heat maps, the authors show the areas of the court that the model sees as high accuracy shots (close to the basket). Heat maps are provided for the 5 roles.
- By visualizing the filters, the authors show how different filters look for combinations of offensive, defensive, and ball positioning.

#### Weak Points
- No distribution of shots made vs shots missed is presented
- The role determining is extremely brief and does not give detail into how these roles were determined.

#### Questions
- Would introducing [Real Estate](http://www.sloansportsconference.com/wp-content/uploads/2016/02/1556-NBA-Court-Realty.pdf) as a feature of size into the trajectories improve the accuracy?
- Instead of 11 channels as a fixed size, can you use varying channel sizes based on player embeddings? Not all players will be distinct in their roles (ie multiple corner three shooters)
- Would only having player roles for offense have any effect on the accuracy vs having 5 roles for defense defined as well?

#### Future Work
- Combine Jackson Wang's work (sequence detection using RNN's) and the fully connected layer of the CNN over 'slices' of the possession to get better accuracy.

### [Applying Deep Learning to Basketball Trajectories](https://arxiv.org/pdf/1608.03793.pdf)

#### Problem Statement
- Using deep learning methods, can shot predicting accuracies be improved?
- Does sequential learning out perform static machine learning methods?

#### Short Summary
- By using only the trajectory of a ball, shot success from the three point line can be determined.
- Using the X,Y,Z and game clock data, trajectories can be learnt from and used to predict shot success.

#### Strong Points
- The authors compared several baseline linear models to show the improvements made by using RNN's
- Instead of just measuring accuracy at the shot, the authors compare the accuracy at different distance 'steps' in a shot.

#### Weak Points
- The mention of mixed density networks is very brief and the authors do not explain how MDN's contribute to predicting shot success.
- Most of the shots are take beyond 8ft, yet there are no accuracy numbers for the distances of the actual shot (all shots are taken 22ft+).

#### Questions
- Why are only three point shots considered? Does this approach not work for mid-range shots, etc?

#### Future Work
- Look at varying sequence lengths to find the optimal length for accuracy.

# [Representing and Discovering Adversarial Team Behaviors using Player Roles](http://www.cv-foundation.org/openaccess/content_cvpr_2013/papers/Lucey_Representing_and_Discovering_2013_CVPR_paper.pdf)

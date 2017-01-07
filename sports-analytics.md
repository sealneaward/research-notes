# Sports Analytics Research Papers

### [Pointwise: Predicting Points and Valuing Decisions in Real Time with NBA Optical Tracking](http://www.lukebornn.com/papers/cervone_ssac_2014.pdf)

#### Problem Statement
- Individual skills can be easily measured by analysts to seek effecient players in a sought after skill.
- There is no definate method presented for analysts to measure and observe the decision making skill of players.

#### Short Summary
- By using expected posession value (EPV) for each posession observed, the proposed method can evaluate the outcomes of the decision made by the expected number of points scored.
- Using the spacial configurations of all players on the court, as well as the ball, the EPV score can be calculated.
- The authors implement a competing risk model that uses the spacial formation of all the players in order to determine the probabilities of passing or shooting the ball.
- EPV can be shown in real time in a stock graphg to the direct impact of decisions made.

#### Strong Points
- Using EPVr to compare replacement player decision ability is a great way to show invividual impact from a player's decision making.

#### Weak Points
- The research does not present how drives to the hoop are evaluated as EPV vs a jump shot at the drive starting location. The jump shot is easy to determine the EPV value from. But with no derivation on this specific event, the EPV representation in Figure 1 is confusing for the drive to the basket.

- The framework only attributes the ball handler with decision making and contributing to EPV. Realistically, all players involved during a posession should be attributed with increasing or decreasing EPV value. An example would be setting an off-ball screen to get a shooter open. Just because someone passed the ball to the open shooter means that they should be entirely attributed with the increase in EPV.

#### Questions
- Would adding turnovers as posession probabilities be beneficial in getting more accurate EPV values? An example would be not passing to a center that is heavily covered as the turnover probability would be high, decreasing the EPV of the center.

#### Future Work
- Now that defensive matchups and defensive intensity is tracked in real time during a posession, how much would this data make an impact on determining EPV? Would the model become simpler and less computationally expensive.

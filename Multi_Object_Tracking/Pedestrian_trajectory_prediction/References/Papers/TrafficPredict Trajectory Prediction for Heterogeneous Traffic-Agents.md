#  TrafficPredict: Trajectory Prediction for Heterogeneous Traffic-Agents 

## Summary
The algorithm can be divided into 2 main layers:

* the instance layer
  * Designed to capture dynamic properties and the interactions between the traffic agent. 
* the  category layer 
  * To conclude the behavior similarities of instances of the same category and guide the prediction for instances in turn.
  * The author also use a self attention mechanism to capture the historical movement patterns and highlight the category difference. 

![1602728557769](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\1602728557769.png)

## Research Objective 
Propose a long short-term memory-based real-time traffic prediction algorithm. And prediction 4 type of group by considering the coexistence and the interaction among vehicles and pedestrians.

## Methods
Based on LSTM method and take into account the interactions among different kinds of traffic agent. 

![1602724351187](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\1602724351187.png)

## Notes

Using these networks to predict trajectories of human crowds(Alahi et al. 2016) and vehicles trajectories (Lee et al. 2017) 

The author also gave a summary of classical methods and DL-based methods for trajectory prediction.

```
Classical methods:

* Bayesian networks

* Monte Carlo Simulation 

* Hidden Markov Models

* KF

* linear and non-linear Gaussian Process regression models 
```
These methods focus on analyzing the inherent regularities based on their previous movements. They don't consider the interactions among different kinds of traffic agents. 

```
Behavior modeling and interactions:

* Social Force model
	pedestrian motion model with attractive and repulsive forces (Yamaguchi et al. 2011).
	Combine with EKF and human motion model to predict hte trajectories for crowds (Wang et al. 2008), etc. Bera et al. (2016;2017).
```

```
RNN networks for sequence prediction:

(Alahi et al. 2016; Gupta et al. 2018; Vemula et al. 2017) use LSTM for predicting trajectories of pedestrians in a crowd, by taking into account the hunman-human interactions.
```
These methods require clear road lanes and simple driving scenarios without other types of traffice agents passing through. 

## References
[Alahi et al. 2016] A. Alahi, K. Goel, V. Ramanathan, A. Robicquet, F.F. Li, and S. Savarese. Social lstm: Human trajectory prediction in crowded spaces. In CVPR, pages 961–971, 2016. 2, 5, 6  

[Lee et al. 2017] N. Lee, W. Choi, P. Vernaza, C.B. Choy, P.H. Torr, and M. Chandraker. Desire: Distant future prediction in dynamic scenes with interacting agents. In CVPR, pages 336–345, 2017. 2 

[Yamaguchi et al. 2011] K. Yamaguchi, A.C. Berg, L.E. Ortiz, and T.L. Berg. Who are you with and where are you going? In CVPR, pages 1345–1352. IEEE, 2011. 2 

[Wang et al. 2008] J.M. Wang, D.J. Fleet, and A. Hertzmann. Gaussian process dynamical models for human motion. TPAMI, 30(2):283–298, 2008. 2 

[Bera et al. 2016] A. Bera, S. Kim, T. Randhavane, S. Pratapa, and D. Manocha. Glmp-realtime pedestrian path prediction using global and local movement patterns. In ICRA, pages 5528–5535. IEEE, 2016. 2 

[Bera et al. 2017] A. Bera, T. Randhavane, and D. Manocha. Aggressive, tense, or shy? identifying personality traits from crowd videos. In IJCAI, volume 17, pages 112–118, 2017. 2 

[Gupta et al. 2018] A. Gupta, J. Johnson, F.F. Li, S. Savarese, and A. Alahi. Social gan: Socially acceptable trajectories with generative adversarial networks. In CVPR, number CONF, 2018. 2  

[Vemula et al. 2017] A. Vemula, K. Muelling, and J. Oh. Social attention: Modeling attention in human crowds. arXiv:1710.04689, 2017. 2, 3, 4, 6 
# Automated Analysis of Pedestrian Group Behavior in Urban Settings 

When studying crowd behavior, understanding grop activities is more important. Studying the individual actions such as joining and leaving a group is also important for Vehicle Decision.


## Research Objective 
The objective of this paper is grouping pedestrians in small group using the movement similarity measures. 

## Methods
*  Automatic Groups Analysis 

*  Automatic Walking Gait Detection 

The author gives a very interesting method to evaluate the dissimilarity among pedestrians. 
The length and frequency of steps determine the walking speed, so that walking speed is not uniform with regard to time. Rather, the pedestrian speed profile is composed of cyclic fluctuations repeated continuously over time. Therefore, it is important to transform the time-series into a domain space, where the resemblance between the series is apparent. The proposed dissimilarity measure is based on the ordinal pattern analysis of time-series [42]. 

Here, the author used all the past information to evaluate dissimilarity.

## Notes

* When pedestrians are walking in a group, they tend to
  adjust their speed and direction accordingly, while maintaining
  interpersonal distances [12].

* Group behavior is based on the concept of individual personal space[19] as well as group configuration [7].
* Rules to identify pedestrians that are traveling together[20]. The rules are derived from **spatial, directional constraints, relative speed and displacement vectors**. Based on these rules, a clustering based group identifications was demonstrated [21, 22].
* [24] considered  pedestrian groups to deal with occlusion problems.
* For the gait, the mean walking speed decreases with increasing group size.  And the gait measures can characterize pedestrian attributes such as age, gender and even health problems. 


## References

 [7] M. Moussaïd, N. Perozo, S. Garnier, D. Helbing, and G. Theraulaz, “The walking behaviour of pedestrian social groups and its impact on crowd dynamics,” PLoS ONE, vol. 5, no. 4, p. e10047, 2010, doi: 10.1371/journal.pone.0010047. 

[12]  K. Rio and W. H. Warren, “The visual coupling between neighbors in real and virtual crowds,” Transp. Res. Procedia, vol. 2, pp. 132–140, Oct. 2014. 

 [20] C. McPhail and R. T. Wohlstein, “Using film to analyze pedestrian behavior,” Sociol. Methods Res., vol. 10, no. 3, pp. 347–375, 1982. 

[21] W. Ge, R. T. Collins, and R. B. Ruback, “Vision-based analysis of small groups in pedestrian crowds,” IEEE Trans. Pattern Anal. Mach. Intell., vol. 34, no. 5, pp. 1003–1016, May 2012. 

[24] S. Pellegrini, A. Ess, and L. Van Gool, “Improving data association by joint modeling of pedestrian trajectories and groupings,” in Computer Vision—ECCV. Berlin, Germany: Springer-Verlag, 2010, pp. 452–465. 

[42] G. Ouyang, C. Dang, D. A. Richards, and X. Li, “Ordinal pattern based similarity analysis for EEG recordings,” Clin. Neurophysiol., vol. 121, no. 5, pp. 694–703, May 2010. 
# Vehicle Trajectory Prediction based on Motion Model and Maneuver Recognition

## Summary 
This paper proposes a trajectory prediction method that combines a trajectory predicted by CYRA motion model and a trajectory predicted by maneuver recognition. For long term prediction, need to take into account the Maneuver Recognition Model. 

## Notes 
### MANEUVER RECOGNITION MODULE (MRM)
In a normal driving context (e.g. no control loss), the path of a vehicle depends on the maneuvers decided by the driver. These can roughly be limited to these canonical cases:
• Keep lane
• Change lane (to the right or the left side lane) on the same road
• Turn (at an intersection).

Priori assumption: There is no oscillation and constant longitudinal acceleration, the comfort is only quantified y the normal acceleration during the maneuver. 

Trajectory prediction with motion model (Tmdl) is very accurate only for a short term. For a longer terms and for specific maneuver the motion model does not fit the actual movement. Trajectory prediction based on maneuver recognition(Tman)  is based on maneuver detection and is thus more adapted to longer time prediction than Tmd. Therefore, Tfin is a weighted sun of Tmdl and Tman with time-series.

![formula_22](.\img_for_md\formula_22.png)




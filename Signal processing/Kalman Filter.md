[medium article](https://medium.com/towards-data-science/exposing-the-power-of-the-kalman-filter-1b78621c3f56)
- **Object tracking**: 
predict the system's future state based on past measurements. The Kalman filtering is a relatively simple state-space algorithm to produce estimates of the hidden variables based on uncertain and inaccurate measurements.
- **State-space model**: 
State-space models help analyze time series problems. State-space models describe the relationship between hidden variables and their observed measurements.
- Kalman Filter is applied to model systems with multiple noisy inputs and outputs hopefully less noisy and more accurately estimated output data. It is applicable to stationary and non-stationary situations.

#### Two inputs
1. Initialization: initial state, initial state uncertainty
2. Measurement performed for every filter cycle and have parameters

#### Two steps
1. Prediction step: the Kalman Filter predicts the next state of the system given the previous measurements.
2. Update step: the Kalman Filter estimates the current state of the system given the measurement at that time step.

#### Two outputs
1. System State Estimate
2. Estimate Uncertainty


"predict-correct" loop:
- *r* - measurement uncertainty
- *p* - estimate uncertainty covariance matrix
- *q* - process noise variance
- *K* - kalman gain
- *H* - observational model matrix

![working procedure](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*MitdOoW3-u80LG1qV9Lyeg.png)
_K_ attempts to balance uncertainty in the predictions with that present in the measurements. As mentioned above, the Kalman Gain is applied to correct the state estimates and covariance
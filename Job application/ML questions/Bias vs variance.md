**- In an ML model what is the tradeoff between bias and variance?**
[answer_medium](https://towardsdatascience.com/understanding-the-bias-variance-tradeoff-165e6942b229)
**Bias**: Bias is the difference between the average prediction of our model and the correct value which we are trying to predict. Model with high bias pays very little attention to the training data and oversimplifies the model. It always leads to high error on training and test data.((**underfitting**))

In supervised learning, **underfitting** happens when a model unable to capture the underlying pattern of the data. These models usually have high bias and low variance. It happens when we have very less amount of data to build an accurate model or when we try to build a linear model with a nonlinear data. Also, these kind of models are very simple to capture the complex patterns in data like Linear and logistic regression.


**Variance**: Variance is the variability of model prediction for a given data point or a value which tells us spread of our data. Model with high variance pays a lot of attention to training data and does not generalize on the data which it hasn’t seen before. As a result, such models perform very well on training data but has high error rates on test data.(**overfitting**)

In supervised learning, **overfitting** happens when our model captures the noise along with the underlying pattern in data. It happens when we train our model a lot over noisy dataset. These models have low bias and high variance. These models are very complex like Decision trees which are prone to overfitting.

![diagram](https://miro.medium.com/v2/resize:fit:720/format:webp/1*xwtSpR_zg7j7zusa4IDHNQ.png)
![diagram](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*9hPX9pAO3jqLrzt0IE3JzA.png)
**Tradeoff**: Bias Variance Tradeoff lies in the complexity of the model. To build a good model, we need to find a good balance between bias and variance such that it minimizes the total error.
![1](https://miro.medium.com/v2/resize:fit:580/format:webp/1*BtpFTBrGaQNE3TvU-0EVSQ.png)
![[Pasted image 20231120220639.png]]
![[Pasted image 20231120220647.png]]

-------------------------------


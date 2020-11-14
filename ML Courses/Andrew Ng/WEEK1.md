## Introduction

<details>
  <summary> <b>Supervised Learning</b>: where we give the algorithm a dataset with the "right answers" included. </summary>
  
  - With supervised learning, we understand there is a rlationship between the input and output.
  - Supervised learning problems are categorised into "regression" and "classification" problems.
</details>  
  
- __Regression__ problem: predicting a continuous valued output.
  - For example, we think of price as a scalar value, as a continuous value number. Although we could also round the price so that it would be a descrete variable.  
  
- __Classification__: predicting a discrete value output, zero or one. (You can have more than 2 output values.)  

- __SVM (Support Vector Machine__: allows for the computer to deal with an infinite number of features.

<details>
  <summary> <b>Unsupervised Learning</b>: where our data may not contain any labels, or they all have the same labels. </summary>
  
  - We have little to no idea what our results should look like, and can derive structure from data where we may not know the effect of the variables.
</details> 

- __Clustering__ algorithm - e.g. Google news
  - you'd get a news title, with many links below (as they have been clustered together)
  
- __Non-clustering__ algorithm - e.g. Cocktail Party problem
  - allows you to find structure in a chaotic environment. (i.e. identifying individual voices and music from a mesh of sounds at a cocktail party).


## Linear Regression with One Variable

- __Model Reresentation__
  - Univariate Linear regression → Linear regression with one variable

- __Cost Function__: helps us figure out how to fit the best possible straight line to our data.
  - Walked through the _Square Error Cost_ / _Mean Squared Error_ function.
    - mostly used for regression problems
  - This helps us measure the accuracy of our hypothesis function.
  - Our goal is to minimise the cost function.
  - We then took a look at contour plots for <img src="https://render.githubusercontent.com/render/math?math=J(\theta_0, \theta_1)">, and will look at an algorithm to help us find the minimum cost function (J).
    - Gradient Descent



## Linear Algebra Review

# Introduction to Supervised Learning

# REFER TO THIS LINK for full cheatsheet: https://stanford.edu/~shervine/teaching/cs-229/cheatsheet-supervised-learning
# TYPES OF MODEL EXAMPLES

Discriminative Model Example: Let's say we want to build a model to classify whether an email is spam or not, given the content of the email. A discriminative model would directly learn the decision boundary that separates spam emails from non-spam emails based on the email content features. The goal is to directly predict the probability that an email is spam given its content, P(spam|email_content).

Generative Model Example: Now, let's say we want to generate new emails that look similar to real emails. A generative model would first learn the underlying probability distributions of the features in real emails, such as the word frequencies, sentence structures, etc. This allows the model to learn the patterns and structure of real emails. Then, the model can use this learned distribution to generate new emails that resemble real ones, by sampling from the learned probability distributions.

The key difference is that the discriminative model focuses on directly predicting the output (spam or not), while the generative model tries to learn the patterns in the input data (email content) in order to generate new samples.


# General concepts

  # Loss and Cost function:
  The cost function and loss function refer to the same context (i.e. the training process that uses backpropagation to minimize the error between the actual and predicted outcome). We calculate the cost function as the average of all loss function values whereas we calculate the loss function for each sample output compared to its actual value.

# Loss Functions for Regression 
 1.  MSE: Mean Square Error / Quadratic Loss / L2 Loss

![image](https://github.com/user-attachments/assets/9c72b868-988a-4667-bd54-087efa7818e6)

![image](https://github.com/user-attachments/assets/0278edd2-8e39-4d06-91c7-9f0fb83ce822)

The MSE loss function penalizes the model for making large errors by squaring them and this property makes the MSE cost function **less robust to outliers**. Therefore, you shouldn’t use it if the data is prone to many outliers.

2. Mean Absolute Error / L1 Loss : MAE loss function as the average of absolute differences between the actual and the predicted value.
     ![image](https://github.com/user-attachments/assets/0c785051-fae6-44c8-9ffb-450bb9c53a9a)
   ![image](https://github.com/user-attachments/assets/89dfd677-4c3e-47e9-bfde-7792fad48483)

 The MAE loss function is more robust to outliers compared to the MSE loss function. Therefore, you should use it if the data is prone to many outliers.

# Loss Functions for Classification

1. Binary Cross-Entropy Loss / Log Loss
    cross-entropy loss decreases as the predicted probability converges to the actual label. It measures the performance of a classification model whose predicted output is a probability value between 0 and 1.
    When the number of classes is 2, it’s binary classification.
     ![image](https://github.com/user-attachments/assets/64bc8b4e-cac9-4d7a-9159-332ceb1f4c1e)


   When the number of classes is more than 2, it’s multi-class classification.

     ![image](https://github.com/user-attachments/assets/0b36e1a2-de35-4d13-9a6b-285ae46a6f71)


    ![image](https://github.com/user-attachments/assets/2458605a-35db-4a85-9972-c1d8f5f58436)

3.   Hinge Loss : Hinge loss penalizes the wrong predictions and the right predictions that are not confident. It’s primarily used with SVM classifiers with class labels as -1 and 1

     ![image](https://github.com/user-attachments/assets/7b72bb1a-5d56-4593-81ab-c48e2dce2c6f)
     
     ![image](https://github.com/user-attachments/assets/ec55d37e-9995-4d01-a443-ee3ddfed92b5)


# GRADIENT DESCENT:

    GOAL : gradient descent is to minimize the cost function, or the error between predicted and actual y. 
    HOW: requires two data points—a direction and a learning rate. 
      DIECTION: Given by providing feedback to the model for COST FUNCTION so that it can adjust the parameters to minimize the error and find the local or global minimum. 
                Continuously iterates, moving along the direction of steepest descent (or the negative gradient) until the cost function is close to or at zero. 
      LEARNIG RATE: Learning rate (also referred to as step size or the alpha) is the size of the steps that are taken to reach the minimum. 
   ![image](https://github.com/user-attachments/assets/4da0a8ec-1ee2-41b0-ab49-cf7a73fd2096)

   Stochastic gradient descent (SGD) is updating the parameter based on each training example, and batch gradient descent is on a batch of training examples

   Challenges with gradient descent
    ![image](https://github.com/user-attachments/assets/081a1b51-c6af-42b4-b1a2-83ef11ed8ddd)





 

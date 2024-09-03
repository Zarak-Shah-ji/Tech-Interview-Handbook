# Introduction to Supervised Learning

# REFER TO THIS LINK for full cheatsheet: https://stanford.edu/~shervine/teaching/cs-229/cheatsheet-supervised-learning
# TYPES OF MODEL EXAMPLES

Discriminative Model Example: Let's say we want to build a model to classify whether an email is spam or not, given the content of the email. A discriminative model would directly learn the decision boundary that separates spam emails from non-spam emails based on the email content features. The goal is to directly predict the probability that an email is spam given its content, P(spam|email_content).

Generative Model Example: Now, let's say we want to generate new emails that look similar to real emails. A generative model would first learn the underlying probability distributions of the features in real emails, such as the word frequencies, sentence structures, etc. This allows the model to learn the patterns and structure of real emails. Then, the model can use this learned distribution to generate new emails that resemble real ones, by sampling from the learned probability distributions.

The key difference is that the discriminative model focuses on directly predicting the output (spam or not), while the generative model tries to learn the patterns in the input data (email content) in order to generate new samples.

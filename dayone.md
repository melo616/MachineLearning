# Overview

## Deep Learning
**Optimizing neural networks, often with many hidden layers, to perform unsupervised or supervised learning.**
- Data can be images
- Goal is: Take image, feed it into deep learning model, model makes prediction of whether or not it contains item
- Give feedback to the model letting it know if it was right or wrong

## Supervised Learning
**Optimizing machine learning models based on previously observed features and labels. Typically, the goal is to attach the most likely label to some provided features.**
- Requires data, e.g. BitCoin price across time
- Requires labels, e.g. an indicator, such as up or down, of how the price moved since the last piece of data
- We then build a model including both of these for the model to learn on
- Then put in data the model isn't trained on and say its prediction based on what has happened before

## Unsupervised Learning
**An approach within machine learning that takes in unlabeled examples and produces patterns from the provided data. Typically, the goal is to discover something previously unkown about the unlabeled examples.**
- Data, but no labels
- Use unsupervised learning algorithm to group like things together
- Go into a cluster, read data, and get output about the data

## Recommendations
**Systems with the goal of presenting an item to a user such that the user will most likely purchase, view, or like the recomended item. Items can take many forms, such as music, movies, or products. Also called recommender systems.**
- E.g. next video in YouTube: out of hundreds of possible suggested next video, gives the best one

## Ranking model
**Optimizing machine learning models to rank candidates, such as music, articles, or products. Typically the goal is to order the candidates such that the candidates which are most likely to be interacted with (purchased, viewed, liked, etc.) are above other candidates that aren't as likely to be interacted with.**
- For instance, selects next TikToks in feed with the goal of keeping you on the platform as long as possible. Thus it should suggest the ranked next videos to achieve this goal.


Features
** A set of quantities or properties describing an observation. They can be binary like "day" and "night"; categorical like "morning", "afternoon", "evening"; continuous like 3.141; or ordinal like "threatened", "endangered", "extinct", where the categories can be ordered. **
- Observation
    - continuous
    - categorical
    - ordinal


Features are generally paired with labels. Usually used with supervised models. Unsupervised models generally do not have labels.

Labels: usually paired with a set of features for use in supervised learning. Can be discrete or continuous.
Continuous variables can take any value within a given range and can be measured with high precision.
Discrete variables can only take distinct, separate values, often representing categories or classes.

Math
arrays/vectors
indices are x1, x2, x3, and so on.
Matrix: a 2D array, generally assigned with the variable name of a capital letter. We can multiple, use the inverse A^-1, or transpose A^T
Polynomials: Line, Quadratic
Derivatives: indicate how much the output of a function will change with respect to a change in its input.

Probability
- Basics: rolling a 2 on a 6-sided die has a probability of 1/6
    - rolling 2 2s is 1/6 * 1/6 = 1/36
- Conditional: drawing two hearts in a row from a deck: 13/52 * 12/52
- Distributions:
    - Gaussian (aka bell curve aka normal dist)
    - Uniform (straight line across)
    - Beta eg for conversion rate

## Bayes Theorum
**Bayes theorum is a formula used to evaluate the conditional probability of something, i.e. the probability of something occurring given other occurrences in the past.**
Mathematically Bayes Theorum is expressed as:
P(A|B) = (P(B|A) * P(A)) / P(B)

Where:
- \( P(A|B) \) is the probability of event A given that event B has occurred.
- \( P(B|A) \) is the probability of event B given that event A has occurred.
- \( P(A) \) is the prior probability of event A.
- \( P(B) \) is the prior probability of event B.


- naive Bayes sees all words in isolation, not adding probability of seeing one word given another (naive independence)
- Laplace smoothing eliminates the issue of having the numerator be 0 when calculating probability. It involves adding 1 to the numerator and 2 to the denominator
- Tokenization takes in a string and separates the words into an array
- Stop word removal - gets rid of words that don't add significant meaning, such as "is"
- Non alphabetic removal - gets rid of random chars
- Stemming: removes ending from different stem. Lemmatization takes a more nuanced approach to get a more accurate stem. However, it is more accurate than stemming.
- Note: if you lowercase everything, you could lose the meaning of proper nouns, e.g. Mark => mark (n, verb)
- Vectorization: changes it to binary whether or not its in the model's vocabulary
- Bernoulli model: a probability model using binary to express a successful outcome or a failure
- Denominator is called the evidence; result of the entire model is called posterior
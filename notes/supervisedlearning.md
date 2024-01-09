# Supervised Learning

## Bayes Theorum
**Bayes theorum is a formula used to evaluate the conditional probability of something, i.e. the probability of something occurring given other occurrences in the past.**
Mathematically Bayes Theorum is expressed as:
P(A|B) = (P(B|A) * P(A)) / P(B)

Where:
- \( P(A|B) \) is the probability of event A given that event B has occurred.
- \( P(B|A) \) is the probability of event B given that event A has occurred.
- \( P(A) \) is the prior probability of event A.
- \( P(B) \) is the prior probability of event B.

### Terminology
- Naive Bayes sees all words in isolation, not applying a probability of seeing one word given another because they frequently cooccur (naive independence)
- Laplace smoothing eliminates the issue of having the numerator be 0 when calculating probability. It involves adding 1 to the numerator and 2 to the denominator
- Tokenization takes in a string and separates the words into an array, or in other words splits raw input into individual words/elements
- Stop word removal - gets rid of words that don't add significant predictive value, such as "is"
- Non alphabetic removal - gets rid of random chars
- Stemming: removes ending from different stem. Lemmatization takes a more nuanced approach to get a more accurate stem. However, it is more expensive than stemming.
- Note: if you lowercase everything, you could lose the meaning of proper nouns, e.g. Mark => mark (n, verb)
- Vectorization: Used in a step of featurizing; transforms some input into something else. One example transforms tokenized messages to a binary value indicating whether or not words from the vocabulary appear in the message.
- Bernoulli model: a probability model using binary to express a successful outcome or a failure
- The denominator of the Naive Bayes classifier is called the **evidence**; the result of the entire model - in other words, the probability given some features - is called the **posterior**.

## Performance
**How do we determine if our model is an improvement on filter rules?**
Accuracy = correct guesses / total guesses
Correct guesses is adding up correct guesses in a negative or positive sense, e.g. is spam, isn't spam.
Accuracy might not be a great metric to gauge the efficacy of a model.
False negative and false positive are the opposite of true negative and true ositive, which can be grouped into a matrix:

**Confusion Matrix**
            Actual
                    spam            legit
Predicted   spam    true positive   false positive
            legit   false negative  true negative

### Common Metrics
**Sensitivity** = true pos / true pos + false neg. Generally means less false negatives.  
**Specificity** = true neg / true neg + false pos. Generally means less false positives
**Precision** = true pos / true pos + false pos
**F1 score** = 2 * (sensitivity * precision) / (sensitivity + precision)

### Additional Terms
- Decision point: Also called decision rule or threshold. It is a cut-off point in which anything below the cutoff is determined to be a certain class and anything above the cutoff is the other class. In the example, the cutoff point separates true positives from false positives and true negatives from false negatives.
- Receiver Operator Characteristic (ROC) Curve: A plot of how the specificity and sensitivity change as the decision threshold changes. The area under the ROC curve, or AUC, is the probability that a randomly chosen positive example will have a higher prediction probability of being positive than a randomly chosen negative example. 
- Unbalanced classes: When one class is far more frequently observed than another class.

Validation set after training set allows you to tune your model before applying to test set. The test set is used to evaluate the model peformance, giving insight into how our model will react to unseen/unlabeled examples.

Hyperparameters are params that go along with the model that you don't necessarily train. These can be tuned using your validation set.

Validation methods:
- Holdout validations: Assign a subset of examples to be a validation set
- K fold cross validation: Instead of taking a random subset as a validation set, train k different models and use a different validation set each time, but with the test set set aside and used the same for each. Each fold of data will be used by a different model. The metrics will be averaged out. This elimates the chance ofhaving chosen the most favorable validation set at random.
- Leave-one-out validation

The process to develop a model is:
1. Problem
2. Hypothesis
3. Simple heuristic
4. Measure impact
5. More complex technique
6. Measure impact
7. Tune model
8. Replace existing technique
One should be able to describe these steps and the different iterations of your project you went through to reach step 8.
If you are stuck on step 4, revisit your hypothesis.
Step 8 should tie back to a tangible business impact.
This process goes more slowly for companies where it's more expensive and failed experiments can directly affect people's health.
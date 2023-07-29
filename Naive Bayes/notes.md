# Naive Bayes Algorithm
Naive Bayes is a popular and simple machine learning algorithm based on Bayes' theorem, which is a probabilistic theorem used to update the probability of a hypothesis based on new evidence. It is commonly used for classification tasks, where the goal is to predict the class label of an input based on its features.

The "naive" part of Naive Bayes comes from the assumption that all features are independent of each other, given the class label. This assumption simplifies the calculations and makes the algorithm computationally efficient, especially for high-dimensional data.

Here's a step-by-step explanation of how the Naive Bayes algorithm works:
α
1. **Data Preparation:**
   - Gather a labeled dataset, which consists of samples with their corresponding class labels.
   - Preprocess the data, including feature selection/extraction and handling missing values, if necessary.

2. **Probability Calculation:**
   - Compute the prior probabilities of each class label (the probability of each class occurring in the dataset). This is done by counting the number of occurrences of each class and dividing by the total number of samples.

3. **Likelihood Estimation:**
   - For each feature in the dataset, calculate the likelihood of that feature given each class. This is done by counting how many times a particular feature occurs in samples of each class and dividing it by the total number of samples in that class.

4. **Feature Independence Assumption:**
   - This is the key assumption in Naive Bayes. It assumes that all features are independent of each other, given the class label. In reality, this assumption may not hold, but it simplifies the calculations and often works well in practice.

5. **Predictions:**
   - Given a new sample with its features, the algorithm calculates the conditional probability of each class label given the observed features using Bayes' theorem.
   - Bayes' theorem is expressed as:
   
     P(class | features) = (P(features | class) * P(class)) / P(features)
   
   - P(class | features) is the posterior probability of the class given the observed features.
   - P(features | class) is the likelihood, which we calculated earlier.
   - P(class) is the prior probability of the class, which we also calculated earlier.
   - P(features) is the probability of the observed features. Since it is constant for all classes in this context, it is often omitted.
   
   - The algorithm then assigns the class label with the highest posterior probability as the predicted class for the new sample.

6. **Model Evaluation:**
   - Evaluate the performance of the Naive Bayes classifier using metrics like accuracy, precision, recall, F1-score, etc., on a separate test dataset.

Naive Bayes is a popular choice for text classification tasks (e.g., spam detection, sentiment analysis, topic categorization) and works well when the independence assumption is not severely violated. Despite its simplicity, Naive Bayes can perform surprisingly well, especially when the dataset is not too large and the features are relatively independent.

## Important Notes
1. Naive Bayes is used in Spam Ham detection.
2. Its Naive because features are independent.
3. Bayes Theorm - Mathematical formula to determine conditional probability. 
    $$Posterior = {(Prior * Likelihood) \over evidence}$$
    $$P(A/B) = {P(A)*P(B/A)\over P(B)}$$
4. Laplace Smoothing - Problem of zero probability
        $$P(E/f) = {0 + α \over n + αk}$$
        f => unknown variable<br>
        α => hyperparameter<br>
        k => No. of values a feature can take (No. of unique values in that feature)<br>
        n => No. of data points of your class.<br>
5. If α is very low model will overfit.<br>
    if α is very high model will underfit.
6. Problem with dimensions - lot of dimensions -> Prbability will be very low -> we take log of Probabilities.
7. Imbalanced Data - if not rectified, model will be biased, it will favour the majority class
8. Outliers - taken care by Laplace smoothing
9. Naive Bayes if of 3 types.
    - Guassian Naive Bayes - Numerical features
    - Bernoulli Naive Bayes - when features are Binomial (1, 0) or (True, False)
    - Multinomial Naive Bayes - more than 2 classes
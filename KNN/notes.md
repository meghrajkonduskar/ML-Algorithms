# KNN - K Nearest Nighbours

K-Nearest Neighbors (KNN) is a simple and widely used supervised machine learning algorithm used for classification and regression tasks. It is a non-parametric and lazy learning algorithm, meaning it doesn't make any assumptions about the underlying data distribution and it defers learning until the time of prediction. Instead of learning a specific model during the training phase, KNN stores the entire training dataset and makes predictions based on the similarity between the input data and the training examples.

The "K" in KNN refers to the number of nearest neighbors that the algorithm considers when making predictions. Here's a step-by-step explanation of the KNN algorithm:

1. Data Preparation: Start with a labeled dataset consisting of input features (attributes) and their corresponding output labels (class labels for classification or continuous values for regression).

2. Choose K: Determine the value of K, which is the number of neighbors to consider. This value is a hyperparameter, and selecting an appropriate K is crucial to the algorithm's performance. A small K might make the model sensitive to noise, while a large K might oversmooth the decision boundary.

3. Calculate Distance: Compute the distance between the input data point (the one you want to classify or predict) and all the data points in the training dataset. Common distance metrics include Euclidean distance, Manhattan distance, and others, depending on the data type and problem domain.

4. Find K Nearest Neighbors: Select the K data points with the smallest distances to the input data point. These K points are the "neighbors" of the input data point.

5. Majority Vote (for Classification): For a classification problem, take a majority vote among the K neighbors to determine the class label of the input data point. The class with the most occurrences among the K neighbors is assigned as the predicted class for the input data point.

6. Average (for Regression): For a regression problem, take the average of the output labels of the K nearest neighbors and use it as the predicted value for the input data point.

7. Make Prediction: The algorithm has now made a prediction based on the majority vote or average, depending on whether it's a classification or regression task, respectively.

8. Evaluate Performance: Measure the performance of the KNN model using evaluation metrics appropriate for the task (e.g., accuracy for classification, mean squared error for regression).

9. Parameter Tuning: Adjust the value of K and/or explore other distance metrics to improve the model's performance.

It's important to note that KNN has some limitations, such as being computationally expensive on large datasets since it requires calculating distances for every data point. Additionally, the algorithm can be sensitive to the scale of the features, so it's often necessary to normalize or standardize the data before applying KNN. Despite its simplicity, KNN can be surprisingly effective, especially on small to medium-sized datasets with well-defined decision boundaries.

## Important Points

1. K should be odd. To avoid equal voting.
2. K is hyperparameter.
3. KNN is mostly used in healthcare.
4. There are 2 types of distance calculation
    - Euclidean
			$$ d = {\sqrt{(x_2^2 - x_1^2 ) + (y_2^2 - y_1^2 )}} $$
			
	- Manhatten
			$$ d = {(x_2 - x_1 ) + (y_2 - y_1 )}$$
5. When K=n Underfitting. When K=1 Overfitting.
6. KNN is sensitive to Outliers.
7. KNN is lazy learner - Computes at the time of prediction.
8. Space issues - Entire dataset is loaded in RAM. Might be an issue where there is less RAM left for computation after loading data.
9. Accuracy of KNN increases and then decreases hen K increases.

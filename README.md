# fashion-mnist-model-comparison
Classification of Fashion MNIST images using Logistic Regression, Random Forest, and Support Vector Machine with performance tuning and evaluation.



Fashion MNIST Classification – Full Project Summary
This project explores the Fashion MNIST dataset, a modern and challenging alternative to the classic MNIST digit set. The goal is to build image classification models that can distinguish between 10 classes of clothing items using deep learning techniques in Python.

 #1. The Fashion MNIST Dataset
We begin by introducing the dataset, which includes 60,000 training and 10,000 test images of 28×28 grayscale clothing items, divided into 10 categories (e.g., Shirt, Sneaker, Dress).

# 2. Challenges and Characteristics
Fashion MNIST presents real-world difficulties: several classes look very similar (e.g., Pullover vs. Coat), and the low resolution limits fine detail detection. These traits make it a good benchmark for evaluating model robustness.

# 3. Preprocessing
We normalize pixel values to the range [0, 1] and reshape the data as needed for feeding into machine learning models. This step ensures training stability and compatibility with neural networks.

 #4. Data Representation
The dataset is split into training and test sets. Each image is represented as a flattened 784-dimensional vector (28x28), and labels are mapped to their respective clothing categories.

# 5. Why Fashion MNIST Was Created
The original MNIST dataset became too easy for modern models. Fashion MNIST was introduced by Zalando Research to provide a more realistic, vision-based classification problem while maintaining the same structure.

# 6. Model Building and Evaluation
In this project, three classification models were implemented to classify Fashion MNIST images: Logistic Regression, Random Forest, and Support Vector Classifier (SVC). Each model was tuned using GridSearchCV for optimal performance, and evaluated based on test accuracy, confusion matrix, and classification report.

# -- Logistic Regression
A multinomial logistic regression model was used as a baseline classifier. The model was trained with the 'lbfgs' solver and multi_class='multinomial', with max_iter=1500 to ensure convergence. A grid search was applied to tune the regularization strength C over the values [0.01, 0.1, 1, 10].
While Logistic Regression is fast and interpretable, it showed limited performance on this complex visual dataset compared to the nonlinear models.

# -- Random Forest Classifier
A Random Forest classifier was implemented with a parameter grid exploring:

Number of estimators (n_estimators): [100, 200]

Maximum depth of trees (max_depth): [10, 20, None]

Minimum samples for splitting and leaves (min_samples_split, min_samples_leaf)

Using GridSearchCV, the best-performing tree structure was selected. The model demonstrated solid performance and robustness, especially in handling visual class overlaps, though at a higher computational cost.

# -- Support Vector Classifier (SVC)
Support Vector Machines were trained with both linear and rbf kernels. The C parameter, controlling the trade-off between margin width and classification accuracy, was tuned over [0.1, 1, 10].
Among all models, SVC with the appropriate kernel showed competitive accuracy. However, training time was longer, particularly with the RBF kernel and larger input size.

# Conclusion
All three models were tested on the held-out test set. While Logistic Regression served as a quick baseline, Random Forest and SVC offered stronger predictive power for this image classification task. The best-performing model was selected based on test accuracy and generalization capability.



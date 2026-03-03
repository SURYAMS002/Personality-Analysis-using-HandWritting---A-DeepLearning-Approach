## Project Description

# Personality Analysis using Handwriting – A Deep Learning Approach

This project presents an automated system designed to predict an individual’s personality traits from handwritten images using image processing techniques, handcrafted feature extraction, and a Multi-Layer Perceptron (MLP) classifier. The system is based on the Big Five Personality Model, which includes Agreeableness, Conscientiousness, Extraversion, Neuroticism, and Openness.

---

## Objective of the Project

The primary objective is to analyze handwriting samples and classify them into one of the five major personality traits using supervised machine learning techniques. The project aims to transform unstructured handwriting images into structured numerical features that can be used for accurate personality classification.

---

## Overall Workflow of the Project

### 1. Data Collection

The dataset is organized into augmented training and testing folders, each containing subfolders corresponding to the five personality classes. Handwritten images are loaded programmatically and labeled according to their respective class directories.

---

### 2. Feature Extraction from Handwriting Images

Instead of directly applying convolutional neural networks on raw images, the system extracts fifteen handcrafted handwriting features. These features are inspired by graphological attributes and structural writing characteristics, including slant angle, letter spacing, pressure, line alignment, loop formation, stroke smoothness, word spacing, letter size consistency, pen lift, legibility, writing style, speed variation, pen tilt, and stroke patterns.

For example, slant angle is computed using edge detection and Hough Transform to estimate the average orientation of strokes.

All extracted features are stored in a structured dataset and exported as a CSV file, effectively converting image data into numerical feature vectors suitable for machine learning.

---

### 3. Data Preprocessing

The extracted dataset undergoes preprocessing steps including label encoding of personality classes, feature normalization using StandardScaler, train-test splitting, and class weight computation to address potential class imbalance.

---

### 4. MLP Model Architecture

A fully connected neural network is implemented using TensorFlow and Keras. The architecture consists of:

* Input layer with fifteen numerical features
* One or more hidden dense layers
* Dropout layers to reduce overfitting
* Output layer with five neurons using softmax activation for multi-class classification

The model is trained using the Adam optimizer and categorical crossentropy loss function. Early stopping is applied to prevent overfitting.

---

### 5. Model Evaluation

The performance of the model is evaluated using multiple classification metrics to ensure reliability and generalization. These include:

* Accuracy, which measures the overall proportion of correctly classified samples
* Precision, which evaluates the correctness of positive predictions for each class
* Recall, which measures the model’s ability to correctly identify actual class instances
* F1-score, which provides a balanced measure of precision and recall
* Confusion matrix, which highlights class-wise prediction performance and misclassification patterns
* Training and validation accuracy and loss curves to monitor learning behavior and detect overfitting

These evaluation measures collectively provide a comprehensive assessment of the classification performance.
## Evaluation Metrics (Short Description for Your Project)

Since your project predicts **5 personality traits** from handwriting using an MLP model, it is evaluated using the following metrics:

###  Accuracy

Accuracy measures the overall percentage of correctly predicted personality classes.

[
Accuracy = \frac{\text{Correct Predictions}}{\text{Total Predictions}}
]

It shows how well the model performs overall.

---

###  Precision

Precision tells how many predicted personality labels are actually correct.

[
Precision = \frac{TP}{TP + FP}
]

High precision means fewer wrong personality assignments.

---

###  Recall

Recall measures how many actual personality samples were correctly identified.

[
Recall = \frac{TP}{TP + FN}
]

High recall means fewer missed predictions.

---

###  F1-Score

F1-score is the balance between Precision and Recall.

[
F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}
]

It is useful when class distribution is uneven.

---

### Confusion Matrix

Shows how the 5 personality classes are classified and where misclassifications occur.

---

###  Loss Function

Categorical Crossentropy is used during training to measure prediction error.

---

**Summary:**
The model performance is evaluated using Accuracy, Precision, Recall, F1-score, Confusion Matrix, and training/validation accuracy curves to ensure reliable personality classification.


---

### 6. Prediction on New Handwriting Samples

The trained model can be used to predict personality traits for new handwritten images. The process involves image preprocessing, feature extraction, scaling using the trained scaler, and final classification using the saved MLP model. This makes the system suitable for deployment and real-world application.

---

## Technical Stack

The implementation utilizes the following technologies:

* OpenCV for image processing
* NumPy and Scikit-Image for feature extraction
* Pandas for data handling
* Scikit-learn for preprocessing and evaluation
* TensorFlow and Keras for deep learning modeling
* Matplotlib and Seaborn for visualization

---

## Nature of the Problem

The project addresses a multi-class supervised classification problem where the input consists of fifteen numerical handwriting features and the output is one of five personality categories.

---

## Strengths

The system effectively transforms unstructured handwriting into structured analytical features. It integrates interpretable graphological attributes with deep learning classification and includes mechanisms to handle class imbalance and overfitting. The end-to-end pipeline supports training, evaluation, and prediction.

---

## Limitations

The performance depends on the quality and representativeness of handcrafted features. The psychological validity of graphology-based traits remains debated. Additionally, the MLP model does not directly analyze raw pixel-level texture patterns as convolutional networks would.

---

## Final Summary

This project develops a structured personality prediction framework that extracts graphology-inspired handwriting features and applies a Multi-Layer Perceptron classifier to categorize individuals into the Big Five personality traits. The system includes preprocessing, training, evaluation using standard classification metrics, and prediction capabilities, making it a complete and deployable deep learning-based personality analysis solution.

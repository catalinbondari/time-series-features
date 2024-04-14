#Time Series Features Project
This project implements activity recognition on time-series accelerometer data. It extracts features from segmented data and utilizes machine learning models for classification.

If you're looking to leverage accelerometer data to identify activities, this project serves as a solid foundation!

##Getting Started
This project requires the following Python libraries:

pandas https://pandas.pydata.org/
numpy https://numpy.org/
matplotlib https://matplotlib.org/
scikit-learn https://scikit-learn.org/
Please ensure you have these libraries installed before running the script.

##Project Overview
The core functionalities of the script can be summarized as follows:

**Data Loading:** The script assumes your data is stored in a folder named data within the project directory. It iterates through sub-folders within data, reading all CSV files. Each file is expected to contain:

Accelerometer data (X, Y, and Z axes) for activity measurements.
A column named "type" that specifies the activity type for each data point.
Data Preprocessing:

**Concatenation:** All data from CSV files are combined into a single Pandas DataFrame named inpDf.
Standardization: The script employs a StandardScaler object to standardize the accelerometer data (X, Y, and Z axes) for better model performance.

##Feature Engineering

**Segmentation:** The script divides the data into fixed-length windows, known as segments.
**Feature Extraction:** For each segment, the script calculates a comprehensive set of statistical features:
Mean, standard deviation, median, minimum, maximum, range, and interquartile range (IQR) for each accelerometer axis (X, Y, and Z).
**Feature Storage:** The extracted features are stored in a dictionary and subsequently appended to a list named segments. The activity type corresponding to the first element within each segment is also appended to a separate list named labels.
Feature DataFrame: Finally, a DataFrame named features_df is constructed from the segments list, and the labels list is incorporated as a new column named "type".

##Machine Learning Models:

The script evaluates the performance of two machine learning models for activity classification:

**Random Forest Classifier:** A popular ensemble method known for its effectiveness in classification tasks.
**Linear Support Vector Classifier (SVC):** A powerful linear classifier adept at separating data points into distinct classes.

The script trains each model on a portion of the data (training set) and assesses its performance on the remaining data (testing set). Classification reports and accuracy scores are utilized to evaluate model performance.

##Evaluation:

**Classification Report:** Provides a detailed breakdown of the model's performance, including precision, recall, F1-score, and support for each activity type.
**Accuracy:** The overall percentage of correct predictions made by the model.
The script additionally checks for missing values in the data and compares the classification performance using features versus raw accelerometer data.

##Note
This project offers a fundamental framework for activity recognition using time-series accelerometer data. You can further enhance the project by:

*Experimenting with different feature sets.
*Exploring various machine learning models and hyperparameter tuning for potentially improved performance.
*Tailoring the project to your specific dataset and desired activity recognition outcomes.
*We welcome your contributions and suggestions! Feel free to explore the code and make modifications to suit your needs.

Author: Catalin Bondari

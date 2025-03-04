# Star Dataset Analysis and Classification

This project analyzes a dataset of stars downloaded from Kaggle. It includes data extraction, exploratory data analysis (EDA), feature engineering, and classification using machine learning algorithms like AdaBoost, Decision Tree, and Random Forest. The aim is to understand stellar properties and predict star categories based on various features.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Modeling and Evaluation](#modeling-and-evaluation)
- [Conclusions](#conclusions)

## Introduction

Stars can be categorized based on several physical attributes like temperature, luminosity, radius, and absolute magnitude. In this project, we:
- Extract and load the dataset from Kaggle.
- Perform visual and statistical EDA to uncover trends.
- Engineer additional features for improved model performance.
- Train and evaluate multiple classification models to predict star categories.

## Installation

Clone the repository and install the required libraries using pip:

```bash
git clone <repository-url>
cd <repository-directory>
pip install pandas numpy matplotlib seaborn scikit-learn kaggle
```
## DataSet

The dataset is obtained from Kaggle. To set up your Kaggle credentials and download the dataset, follow these steps:
1. Place your `kaggle.json` file in the repository root.
2. Run the commands below to configure your Kaggle environment and download the dataset:
```bash
# Set up the Kaggle credentials
mkdir -p ~/.kaggle
cp kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json

# Download the dataset from Kaggle
kaggle datasets download -d deepu1109/star-dataset
```
3. Extract the dataset using Python:
```bash
from zipfile import ZipFile

dataset = 'star-dataset.zip'
with ZipFile(dataset, 'r') as zip_file:
    zip_file.extractall()
    print('The dataset is extracted')
```

## Project Structure

- **Data Extraction:** Commands to download and extract the star dataset.
- **Data Preprocessing:** Loading the CSV data, exploring the dataset structure, and performing basic cleaning.
- **Exploratory Data Analysis (EDA):**
    - Scatter plots for relationships such as Temperature vs. Luminosity, Temperature vs. Radius, and Temperature vs. Absolute Magnitude.
    - Box plots to compare distributions of Luminosity, Radius, and Temperature across different star categories.
- **Feature Engineering:** Creation of new features such as:
    - **Mass (M/Mo):** Derived from Luminosity.
    - **Magnitude_Temperature_Ratio:** The ratio of Absolute Magnitude to Temperature.
    - **Radius_Luminosity_Ratio:** The ratio of Radius to Luminosity.
- **Machine Learning Models:** Training and tuning of:
    - AdaBoost Classifier
    - Decision Tree Classifier
    - Random Forest Classifier
- **Evaluation:** Using accuracy, precision, recall, F1 score, and confusion matrices to assess model performance.

## Usage

You can run the entire workflow as a Jupyter Notebook or as a Python script. The typical steps are:

1. **Download and Extract Data:** Run the commands provided to set up Kaggle credentials and extract the dataset.
2. **Execute Data Analysis:** Run the notebook/script to preprocess data, perform EDA, and visualize trends.
3. **Train Models:** Execute the code sections for feature engineering and training/testing of machine learning models.
4. **Review Results:** Check the generated plots and printed classification reports for insights.

## Exploratory Data Analysis

The EDA section of the project includes:

- **Scatter Plots:** Illustrate relationships among temperature, luminosity, radius, and absolute magnitude.
- **Box Plots:** Show distributions of these features across star categories.
- **Insights:** Detailed commentary on how dwarf stars, main sequence stars, supergiants, and hypergiants differ in terms of stellar attributes.

## Modeling and Evaluation

The project uses three classifiers:

- **AdaBoost Classifier:** Shows decent performance with slight signs of overfitting.
- **Decision Tree Classifier:** Achieves perfect scores on both training and testing data, suggesting possible overfitting.
- **Random Forest Classifier:** Provides very high testing accuracy and is recommended for its generalization capabilities.

Evaluation metrics such as accuracy, precision, recall, and F1 score are computed, and confusion matrices are visualized to assess each model’s performance.

## Conclusions

- **Dwarf Stars:** (Brown, Red, and White Dwarfs) tend to have low luminosity, small radii, and relatively low temperatures
- **Main Sequence Stars:** Follow clear patterns with increasing temperature, luminosity, and radius.
- **Supergiants and Hypergiants:** Exhibit significantly higher luminosity and radii, with broader temperature ranges.
- **Model Recommendation:** The Random Forest Classifier is preferred due to its strong performance on unseen data, while the Decision Tree might need further tuning to avoid overfitting.

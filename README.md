# Titanic-Machine-Learning-From-Disaster

## Overview
A machine learning model is trained on a titanic onboard data and the passenger survival is predicted using the best model.

## General idea
This project solves the famous Kaggle Titanic Challenge. The goal is to predict which passengers survived the Titanic shipwreck using historical data. 
Instead of just guessing, this project uses data science techniques to analyze passenger information (like age, class, and gender) to build a prediction model.

##  Project steps

The project can be broken down into four main steps:

### 1. Data Exploration 
Before building a model, data is analyzed to study the data and to find patterns.
* **Visualizations:** Different graphs are created to study correlation between different variables and the survival rate. Those variables include: **Age**, **Gender**, **Ticket Class** and so on.
* **Discoveries:** Seeing the visualization, it can bee seen that women and children were much more likely to survive, and passengers in 1st Class had a better chance than those in 3rd Class and the classes below.

### 2. Data Cleaning 
This is a Real-world data and it is a little messy. A lot of passengers were missing their **Age** and **Cabin** numbers. There was a significant amount of missing data, so deleting them was not useful. Instead of using traditional ways such as averages, we used a little bit of predictive modeling to predict those missing values.
* **Predicting Age:**  **Random Forest** model was used to predict the age. To predict passenger's age, the algorithm incorporated use of passenger's title (Mr., Mrs., Master), family size, and fare.
* **Predicting Cabins:**  "Deck" from the cabin number was extracted and then a**Gradient Boosting** algorithm was used to predict the deck for passengers where that information was missing.

### 3. Feature Engineering
To help the AI understand the data better, new categories were created:
* **Title Extraction:** ITitles (like Mr., Miss, Dr.) were extracted from names to understand social status.
* **Family Size:** "Siblings" and "Parents" were combined. This helped us see if big families struggled to escape together.
* **IsElderly:** A special flag for passengers over 60 years old was created.

### 4. Finding the Best Model 
Hyperparameter tuning was done for different models and different Machine Learning models were tested to see which worked the best.
* **Algorithms Tested:** Logistic Regression, Decision Trees, Random Forest, SVM, and Gradient Boosting.
* **Best model:** The **Gradient Boosting Classifier** gave the best results (approx 84% accuracy during training).

---

## Files used for model training and testing:

* **`Titanic.ipynb` **
    * This is where the analysis happens. It loads the training data, visualizes it, cleans it, and trains the machine learning models. It saves the best model to a file. We use train.csv in this notebook file.
* **`Titanic_prediction.ipynb`**
    * This file takes the saved model and runs it against new data (the test set) to generate the final list of survivors for submission.

##  Technologies Used

* **Python**: The programming language.
* **Pandas**: For organizing data into tables.
* **Matplotlib & Seaborn**: For creating graphs and charts.
* **Scikit-Learn**: For building the Machine Learning models.

##  How to Use This Project

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/titanic-project.git](https://github.com/yourusername/titanic-project.git)
    ```
2.  **Install the required libraries:**
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn
    ```
3.  **Run the Training Notebook:**
    Open `Titanic.ipynb` in Jupyter Notebook or VS Code to see the analysis and train the model.
4.  **Make Predictions:**
    Open `Titanic_prediction.ipynb` to load your trained model and create a `submission.csv` file.

---


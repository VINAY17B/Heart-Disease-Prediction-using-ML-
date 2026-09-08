# ❤️ Heart Disease Prediction using Machine Learning

A machine learning project that predicts whether a person is likely to have heart disease based on various medical attributes. The project uses **Logistic Regression** for binary classification and evaluates the model using accuracy.

## 📌 Project Overview

Heart disease is one of the major health concerns worldwide. This project demonstrates how machine learning can be used to analyze patient-related features and predict the presence or absence of heart disease.

The workflow includes:

* Loading and exploring the heart disease dataset
* Separating features and target variables
* Splitting the dataset into training and testing sets
* Training a Logistic Regression model
* Evaluating model accuracy
* Making predictions on unseen patient data

## 🛠️ Technologies Used

* **Python**
* **Pandas** – Data loading and manipulation
* **NumPy** – Numerical operations
* **Scikit-learn** – Machine learning and model evaluation
* **Jupyter Notebook** – Development environment

## 🧠 Machine Learning Model

### Logistic Regression

The project uses **Logistic Regression**, a supervised learning algorithm suitable for binary classification.

The target variable represents whether heart disease is present:

* `0` → No heart disease
* `1` → Heart disease

## 📊 Dataset

The project uses a CSV dataset named:

```text
heart_disease_data.csv
```

The dataset contains patient medical attributes, with the `target` column used as the prediction label.

The input features include values representing attributes such as:

* Age
* Sex
* Chest pain type
* Resting blood pressure
* Cholesterol
* Fasting blood sugar
* Resting ECG
* Maximum heart rate
* Exercise-induced angina
* ST depression
* ST slope
* Number of major vessels
* Thalassemia-related measurement

> The exact feature meanings and dataset schema should be verified against the supplied CSV dataset.

## 🔬 Project Workflow

```text
Dataset
   ↓
Data Exploration
   ↓
Feature / Target Separation
   ↓
Train-Test Split
   ↓
Logistic Regression
   ↓
Model Prediction
   ↓
Accuracy Evaluation
   ↓
Prediction on Unseen Data
```

## 📂 Project Structure

```text
Heart-Disease-Prediction/
│
├── Heart_Disease_Prediction.ipynb
├── heart_disease_data.csv
└── README.md
```

## ⚙️ Installation

Clone the repository:

```bash
git clone <your-repository-url>
cd Heart-Disease-Prediction
```

Install the required dependencies:

```bash
pip install pandas numpy scikit-learn jupyter
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
Heart_Disease_Prediction.ipynb
```

## 🚀 Model Training

The dataset is divided into training and testing sets using an 80/20 split:

```python
X_train, X_test, Y_train, Y_test = train_test_split(
    X,
    Y,
    test_size=0.2,
    stratify=Y,
    random_state=2
)
```

The Logistic Regression model is then trained:

```python
model = LogisticRegression()
model.fit(X_train, Y_train)
```

## 📈 Model Evaluation

Predictions are generated on the test dataset:

```python
Y_pred = model.predict(X_test)
```

The model's performance is measured using accuracy:

```python
score = accuracy_score(Y_test, Y_pred)

print("The accuracy score is", score)
```

The notebook calculates the accuracy score based on the test-set predictions.

## 🔮 Prediction on Unseen Data

The trained model can also make predictions for a new patient's input data.

Example:

```python
input_data = (
    62, 0, 0, 140, 240, 0,
    160, 0, 3, 6, 0, 2, 2
)

arr = np.array(input_data)

prediction = model.predict(arr.reshape(1, -1))
```

The prediction is then interpreted as:

```text
0 → Your heart is healthy
1 → Your heart is not healthy
```


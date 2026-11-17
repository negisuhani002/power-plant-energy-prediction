# Power Plant Energy Output Prediction

## Overview

This project focuses on predicting the electrical energy output of a power plant using regression techniques.

An Artificial Neural Network (ANN) is developed using PyTorch and its performance is compared with two traditional machine learning models: Linear Regression and Support Vector Regression (SVR).

## Dataset

The project uses the Power Plant Energy Prediction dataset.

It contains four input features and one target variable:

| Feature | Description |
|---|---|
| AT | Ambient Temperature |
| V | Exhaust Vacuum |
| AP | Ambient Pressure |
| RH | Relative Humidity |
| PE | Electrical Energy Output (Target) |

The dataset is not included in this repository.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- PyTorch
- Matplotlib

## Project Workflow

### 1. Data Loading and Exploration
- Load the dataset using Pandas.
- Explore the dataset and understand the features.
- Check for missing values.

### 2. Feature Selection
- Input features: AT, V, AP, RH
- Target variable: PE

### 3. Data Preprocessing
- Split the dataset into training (70%), validation (15%), and testing (15%) sets.
- Apply StandardScaler to scale the input features.
- Fit the scaler only on the training data.
- Transform the validation and testing data using the fitted scaler.

### 4. ANN Model Development
- Build a regression model using PyTorch.
- Use ReLU activation in the hidden layers.
- Use Mean Squared Error (MSE) as the loss function.
- Use Adam optimizer.
- Train the model for 100 epochs.
- Monitor training and validation loss.
- Save the model with the best validation loss.

### 5. Model Evaluation
- Evaluate the ANN using Mean Squared Error (MSE) and R² score.
- Compare its performance with Linear Regression and Support Vector Regression.
- Use the same test dataset to evaluate all three models.

### 6. Visualization
- Plot training and validation loss to observe the model's learning progress.

## ANN Architecture

The Artificial Neural Network consists of:

- Input layer: 4 features
- Hidden layer 1: 6 neurons with ReLU activation
- Hidden layer 2: 6 neurons with ReLU activation
- Output layer: 1 neuron

**Architecture:** `4 → 6 → 6 → 1`

## Model Evaluation and Comparison

All three models were evaluated on the same test dataset.

| Model | Testing MSE | R² Score |
|---|---:|---:|
| Artificial Neural Network (ANN) | 20.62 | 92.94% |
| Linear Regression | 20.38 | 93.02% |
| Support Vector Regression (SVR) | **16.69** | **94.29%** |

### Comparison and Observation

- **ANN:** Achieved an R² score of 92.94%.
- **Linear Regression:** Achieved an R² score of 93.02%, slightly outperforming the ANN.
- **SVR:** Achieved the lowest testing MSE of 16.69 and the highest R² score of 94.29%.

**Best Performing Model: SVR**

Among the three models, SVR performed best on the test dataset, followed by Linear Regression and ANN.

A lower MSE indicates smaller prediction errors, while a higher R² score indicates that the model explains a larger proportion of the variance in the target variable.

## Key Learnings

- Data exploration and preprocessing.
- Feature scaling using StandardScaler.
- Splitting data into training, validation, and testing sets.
- Building and training an ANN using PyTorch.
- Understanding forward propagation and backpropagation.
- Using validation loss for model selection.
- Evaluating regression models using MSE and R² score.
- Comparing deep learning and traditional machine learning models.

## Repository Structure

```text
Power-Plant-Energy-Prediction/
│
├── ANN_Regressor.ipynb
└── README.md
```

## Conclusion

This project explores the prediction of power plant electrical energy output using an Artificial Neural Network and compares it with traditional machine learning regression techniques.

The results show that all three models achieved good predictive performance. However, Support Vector Regression performed best, achieving an R² score of approximately 94.29% and a testing MSE of 16.69.

This project demonstrates that traditional machine learning algorithms can perform very well on structured tabular datasets and that a neural network is not necessarily the best-performing choice for every regression problem.

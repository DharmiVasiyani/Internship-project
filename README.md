# Internship-project
Anomaly Detection in Network Traffic

# Anomaly Detection using Autoencoder and Isolation Forest

This project performs anomaly detection on the KDD Cup 1999 dataset using two unsupervised learning algorithms: Autoencoder and Isolation Forest. The goal is to identify unusual patterns in network traffic data that may indicate potential security breaches or system malfunctions.

## Dataset

- Contains 41 features and 1 label column
- The label column includes both normal and various attack types. These are converted into binary labels for this project:
  - 0: Normal
  - 1: Attack (Anomaly)

## Project Workflow

### 1. Data Loading and Preprocessing

- The dataset is downloaded using `kagglehub` (for use in Google Colab).
- Data is extracted from the `.gz` file and column names are assigned.
- Categorical columns (`protocol_type`, `service`, `flag`) are label encoded.
- Feature values are normalized using MinMaxScaler.
- A new column `binary_label` is created to represent normal vs attack traffic.

### 2. Autoencoder Model

- An unsupervised neural network is trained only on normal data.
- Reconstruction error is used to identify anomalies.
- A threshold is set based on reconstruction error from normal data.
- Accuracy is calculated at the end of each epoch.
- Final predictions and evaluation are done on the entire dataset.

### 3. Isolation Forest Model

- The model is trained on the full dataset.
- Anomalies are predicted based on how isolated the data points are.
- Predictions are compared with actual binary labels to evaluate accuracy.

### 4. Evaluation and Comparison

- Accuracy is calculated for both models.
- Confusion matrices are plotted.
- Classification reports are generated.
- A bar chart is used to compare the accuracy of both methods.

## Results

| Model            | Evaluation Metrics      |
|------------------|--------------------------|
| Autoencoder      | Accuracy (shown per epoch and final) |
| Isolation Forest | Final accuracy displayed |

Both models are compared using accuracy, precision, recall, and F1-score.

## Requirements

The following Python libraries are required:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- tensorflow
- kagglehub

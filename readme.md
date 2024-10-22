# Predicting Remaining Useful Life (RUL) of Engines

## Project Description
This project is designed to predict the Remaining Useful Life (RUL) of aircraft engines based on the PHM08 Prognostics Data Challenge dataset. 
The goal is to predict the number of remaining operational cycles until engine failure.

## Key Features
- **Dataset**: The PHM08 dataset is used, containing time series with numerous sensor measurements.
  
- **Model**: A combination of a Convolutional Neural Network (CNN) and Bidirectional LSTM (Bi-LSTM) layers. 
This architecture allows for effective extraction of both local and long-term dependencies in the data.

### Data Preprocessing:
- **Feature standardization** using `StandardScaler`.
- **Removal of uninformative sensors** based on data analysis.
- Generation of fixed-length sequences using a sliding window and application of masks to handle sequences of varying lengths.

### Loss Function:
A custom loss function that accounts for the asymmetry of prediction errors. Underestimation and overestimation of RUL are penalized differently, aligning with real-world forecasting requirements.

### Model Evaluation:
Metrics such as RMSE, MAE, R², and SMAPE are used to assess model performance.

### Visualization:
Creation of plots for analyzing model performance and error distribution, including loss, MAE, prediction error distribution, and comparison of true and predicted RUL values.

---

## Installation
### Clone the repository:

```bash
git clone https://github.com/pavelMerlin/RUL_biLSTM
cd RUL_biLSTM
```

### Install the required dependencies:

```bash
pip install -r requirements.txt
```
Note: The project was developed using Python 3.12.3.

## Usage

### File Descriptions

- **`train.ipynb`**:
  - Loads and preprocesses the data.
  - Trains the model on the training set using early stopping.
  - Saves the best model and scalers for later use.

- **`generate.ipynb`**:
  - Loads the test data and the saved model.
  - Applies the trained model to predict RUL on the test data.
  - Saves the results to the file `final_test_predictions.csv`.

- **`data_analysis.ipynb`**:
  - Exploratory data analysis on the training set.
  - Identification of uninformative sensors for exclusion from the model.

---

## Results

### Metrics on the Validation Set

- **Validation Score**: 66
- **RMSE**: 11.2
- **MAE**: 8.5
- **R²**: 0.86
- **SMAPE**: 19.43%

### Results and Compliance with Technical Requirements

The obtained results demonstrate high model accuracy and meet the requirements for RUL prediction. 
The metric values indicate that the model is capable of accurately predicting the remaining useful life of the engines.

Completed for softinway tech task.

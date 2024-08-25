# Fault Detection in DC-microgrids
## Project Overview

This project involved simulations of Direct Current (DC) microgrids using DIgSILENT software. The simulations generated data with eight discretized variables derived from voltage and current signals at both poles and ends of the line. The primary goal was to develop a model for bus 1 to detect and locate line faults.

## Data Description, Feature Extraction and Selection, and Applied ML Methods

- **Sampling Rate:** 50000, aiming to distinguish internal faults (lines 1-2) from external ones using seven samples (0.14 milliseconds).
- **Feature Extraction:**
  - **Discrete Wavelet Transform (DWT):** Produces 16 features (two components per variable).
  - **Fast Fourier Transform (FFT):** Results in 32 features (four components per variable).
- **Machine Learning Methods:** Logistic Regression (LR), Linear Discriminant Analysis (LDA), Support Vector Machine (SVM), Random Forest (RF), Extreme Gradient Boosting (XGBoost).
- **Feature-Selection Methods:** Mutual Information (MI), ANOVA F-measure, Pearson correlation.

## CNN-based Model Development

- **Convolutional Neural Networks (CNN):** Employed for spatial and temporal feature extraction and classification. Four different CNN model configurations were tested.
- **Evaluation Strategy:** (5-2)-fold cross-validation.
  - **Inner Two-Fold:** Tuning hyper-parameters (Grid-search for ML-based models, Bayesian optimization for CNN) and feature selection (ML-based models).
  - **Outer Five-Fold:** Model performance evaluation using selected features and tuned hyper-parameters.

## Performance Metrics

- **Stored Data:** Optimal hyper-parameters and selected features for each fold and model.
- **Metrics:** Accuracy, F1-measure, F2-measure.
- **Results Documentation:** Excel file with results based on models and feature-selection methods.

## Robustness Evaluation

- **Noise Conditions:** Gaussian noise added to input data, SNR values ranging from 20 to 45 decibels.
- **Model Training:** Conducted on clean data.
- **Testing:** Performed on noisy data in the outer 5-fold.
- **Result Storage:**
  - **Noisy Data:** Stored in the "Noisy Evaluation" folder.
  - **Clean Data:** Stored in the "Without Noise Evaluation" folder.

## Notes

- The data and results for this project are stored in the respective folders for easy access and review.

## Detailed Project Description

The data for this project was procured from numerous simulations of Direct Current (DC) microgrids using DIgSILENT software. The software generated data from each simulation containing eight discretized variables. These variables were derived from voltage and current signals measured at both the positive and negative poles and at both ends of the line. One of the primary objectives was to develop a model for bus 1 that could detect and locate faults on the line. The sample rate for these variables was set at 50000, to identify an internal fault (lines 1-2) from other external faults using only seven samples, equivalent to 0.14 milliseconds. This was to ensure precise protection of the DC microgrid.

Feature extraction from the data was achieved using Discrete Wavelet Transform (DWT) and Fast Fourier Transform (FFT). The FFT yielded four components for each variable, amounting to 32 features, while the DWT produced two components for each variable, resulting in 16 features. Five machine learning methods, Logistic Regression (LR), Linear Discriminant Analysis (LDA), Support Vector Machine (SVM), Random Forest (RF), and Extreme Gradient Boosting (XGBoost), were then utilized for two-class classification. Moreover, three different feature-selection methods, Mutual Information (MI), ANOVA F-measure, and Pearson correlation, were implemented to select the most valuable features from the 32 (FFT) and 16 (DWT). The raw data, represented by a window of seven by eight samples, was used for Convolutional Neural Networks (CNN) models for spatial and temporal feature extraction and classification. Four configurations of CNN models with different capacities were employed for this purpose.


The effectiveness of the models was evaluated using a (5-2)-fold cross-validation strategy. In the inner two-fold, the hyper-parameters of the models (for CNN and ML-based models) were tuned, and feature selection was performed (only for ML-based models). This was achieved using the Grid-search algorithm for ML-based models and Bayesian optimization for the CNN models. In the outer five-fold, the performance of the model was evaluated and averaged using the selected features and tuned hyper-parameters. The optimal hyper-parameters and selected features were stored for each fold and model. The final performance of the model, in terms of "Accuracy", "F1-measure", and "F2-measure", was documented in an Excel file based on the models and the feature-selection method.
To assess the performance of the models under noisy conditions, the input data was contaminated with Gaussian noise at different Signal-to-Noise Ratio (SNR) values, ranging from 20 to 45 decibels. The model results were only reported when the test data were corrupted with noise. The models were not trained using noisy data. The feature selection and hyper-parameter tuning were conducted using clean data. In the outer 5-fold, the test data were evaluated using the aforementioned noisy data. 
This process was undertaken to evaluate the robustness of the methods in conditions with noise interference. The outcomes of this part of the study are stored in a folder named "Noisy Evaluation". Conversely, the results from the evaluation of clean data are documented in a folder titled "Without Noise Evaluation".

## Author
- **Ali Amini**: Machine Vision Engineer and Software Developer at RCDAT.
- **GitHub Repo**: [Repo Adress](https://github.com/AliAmini93/Fault-Detection-in-DC-microgrids) 

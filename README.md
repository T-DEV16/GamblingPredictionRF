# Random Forest Predictor for iEEG Data


This project implements a Random Forest model to predict gambling behavior based on intracranial EEG (iEEG) data. The predictor is designed to classify whether a subject will gamble or opt for a safe bet during a decision-making task. The data used is less than 2 GB, and while the current accuracy is around 65%, larger datasets can potentially improve prediction accuracy.

Requirements
Python 3.6+
Required Python libraries:
numpy
h5py
scikit-learn
You can install the required Python libraries using the following command:

bash
Copy code
pip install numpy h5py scikit-learn
Dataset
The dataset used in this project is stored in an HDF5 file named BrainWaveData.mat. It includes high-gamma power spectral data from different brain regions and behavioral data indicating whether a gamble was made.

Code Explanation
Loading the Data
The iEEG data is loaded from the BrainWaveData.mat file using the h5py library. The dataset is preprocessed by selecting a subset of the data and then transposing it to match the expected input shape for the machine learning model.

Data Preprocessing
The iEEG data is divided by brain regions, and Principal Component Analysis (PCA) is applied to reduce the dimensionality. The reduced data is then binned into histograms to create features for the model.

Model Training
A Random Forest Regressor is used to train the model on the preprocessed data. The data is split into training and testing sets, with 70% used for training and 30% for testing.

Prediction and Evaluation
The model predicts whether a gamble will be made based on the input features. The predictions are then compared to the actual labels to calculate the accuracy of the model. Feature importance is also assessed to understand which brain regions contribute the most to the predictions.

Model Accuracy
The current model achieves an accuracy of approximately 65%. Due to the limited size of the dataset (less than 2 GB), this accuracy is expected to improve with a larger dataset.

Feature Importance
The model also provides insights into the importance of different brain regions in predicting gambling behavior. This is useful for understanding the neural basis of decision-making.

Conclusion
This project demonstrates how to use Random Forests to predict gambling behavior from iEEG data. With more data, the model's accuracy can be further improved, making it a powerful tool for understanding decision-making processes in the brain.

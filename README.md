# Predictive-Maintenance-using-LSTM
# Recurrent Neural Networks for Predictive Maintenance




## Software Environment
* Python 3.6
* numpy 1.13.3
* scipy 0.19.1
* matplotlib 2.0.2
* spyder 3.2.3
* scikit-learn 0.19.0
* h5py 2.7.0 
* Pillow 4.2.1 
* pandas 0.20.3
* TensorFlow 1.3.0
* [Keras 2.1.1](https://keras.io)


The network uses simulated aircraft sensor values to predict when an aircraft engine will fail in the future, so that maintenance can be planned in advance.
The question to ask is "Given these aircraft engine operation and failure events history, can we predict when an in-service engine will fail?"
We re-formulate this question into two closely relevant questions and answer them using two different types of machine learning models:

	* Regression models: How many more cycles an in-service engine will last before it fails?
	* Binary classification: Is this engine going to fail within w1 cycles?

## Data Summary
In the **Dataset** directory there are the training, test and ground truth datasets.
The training data consists of **multiple multivariate time series** with "cycle" as the time unit, together with 21 sensor readings for each cycle.
Each time series can be assumed as being generated from a different engine of the same type.
The testing data has the same data schema as the training data.
The only difference is that the data does not indicate when the failure occurs.
Finally, the ground truth data provides the number of remaining working cycles for the engines in the testing data.
The following picture shows a sample of the data: 
<p align="center">
  <img src="https://github.com/hazembhs/Predictive-Maintenance-using-LSTM/tree/main/Output/datasetSample.png"/>
</p>
You can find more details about the data at <a href="https://github.com/Azure/lstms_for_predictive_maintenance/blob/master/Deep%20Learning%20Basics%20for%20Predictive%20Maintenance.ipynb">[1]</a> and <a href="https://gallery.azure.ai/Experiment/Predictive-Maintenance-Step-2A-of-3-train-and-evaluate-regression-models-2">[2]</a>.

## Experimental Results
### Results of Regression model

|Mean Absolute Error|Coefficient of Determination (R^2)|
|----|----|
|12|0.7965|


         
### Results of Binary classification 

|Accuracy|Precision|Recall|F-Score|
|----|----|----|----|
|0.97|0.92|1.0|0.96|

The following pictures show trend of loss Function, Accuracy and actual data compared to predicted data: 
<p align="center">
  <img src="https://github.com/hazembhs/Predictive-Maintenance-using-LSTM/tree/main/Output/model_loss.png"/>
</p>
<p align="center">
  <img src="https://github.com/hazembhs/Predictive-Maintenance-using-LSTM/tree/main/Output/model_accuracy.png"/>
</p>
<p align="center">
  <img src="https://github.com/hazembhs/Predictive-Maintenance-using-LSTM/tree/main/Output/model_verify.png?raw=true"/>
</p>

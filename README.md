# Deep Learning Charity Success

Tools used:

- VS Code 1.8
- Python 3.10
  - Tensorflow
  - Pandas

### Overview

Deep Learning neural nets, developed to predict a charity's success based on various features, such as Application Type, Affiliation, Class, Use Case, Organization Type, Active Status, Income, Special Considerations, and Ask Amount. After preprocessing the data and handling class imbalances, four different models were evaluated.

### Model Evaluation

During transformations, and while binning parts of the data, multiple features had values that heavily outnumbered the rest of the dataset, this discrepency was accounted for and explored while evaluating different models.

#### Model 1

- 3 layers (30, 15,  and 8 nodes respectively) + 1 output layer

The first model was ran and used oversampling of the minority Application types to better balance the training data.

- ##### Outcome Oversampling Model

  - Loss: 0.532
  - Accuracy: 0.734
  - Precision: 0.725
  - Recall: 0.793
  - F1: 0.758

Ultimately the model fails to meet the target accuracy of 75%. Multiple layer and node variations were attempted with the 3 layer model performing the closest to target with a 73% accuracy score.


#### Model 2/3

- 2 layers (30, and 15 nodes respectively) + 1 output layer

For the next model(s) The data was split by the Application type, the T3 types only were one dataset and the rest of the application types for the other. The amount of T3 charities heavily outnumbered the rest of the application types.

- ##### Outcome No_T3 Model

  - Loss: 0.461
  - Accuracy: 0.779
  - Precision: 0.599
  - Recall: 0.894
  - F1-Score: 0.717
- ##### Outcome T3_Only Model

  - Loss: 0.568
  - Accuracy: 0.721
  - Precision: 0.649
  - Recall: 0.493
  - F1-Score: 0.561

The T3_only dataset's features were better representative of the dataset as a whole but ultimately this didnt prove helpful in predicting charity outcomes. Each model was compiled on its own data and tested against its counterpart, ie the Model trained on the T3 applicaitons was evaluated using the No_T3 testing set. In the end the model trained on No_T3 applications performed well and beat the target score with an accuracy of 78%.


#### Model 4

- 3 layers (30, 15, and 8 nodes respectively) + 1 output layer

The final model utilized undersampling of the T3 application types.

- ##### Outcome Undersampling Model

  - Loss: 0.559
  - Accuracy: 0.711
  - Precision: 0.672
  - Recall: 0.877
  - F1: 0.761

Ultimately undersampling didn't reach the target accuracy either. With an accuracy of 71% the model underperformed every other.


### Summary

Despite employing various techniques to handle class imbalances, the models largely didn't meet the target accuracy. While the model trained on non-T3 applications showed the best performance with an accuracy of 78%, it is evident that further exploration of the features and potential changes to the neural net architecture may be necessary. The features that may contribute the most to a charity's success may not be represented in our dataset as well. Social impact, awareness, and engagement are all large factors in donations to charities, that are not measured in our dataset. The ability to gather a quantifiable metric of those factors would contribute to the overall performance of the model(s).

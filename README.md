# Neural_Network_Charity_Analysis

## Overview

    The purpose of this analysis was to develop a learning model, using pandas and tensorflow, that would correctly predict if a company that was potentially funded would be succesful in their campaign.

## Results

- _Data Preprocessing_

  - Targets for this model were:

    - 'IS_SUCCESSFUL' - this was a binary series that listed whether or not the funding campaign was successful

  - The features for this model were:

    - 'APPLICATION_TYPE'
    - 'AFFILIATION'
    - 'CLASSIFICATION'
    - 'USE_CASE'
    - 'ORGANIZATION'
    - 'STATUS'
    - 'INCOME_AMT'
    - 'SPECIAL_CONSIDERATIONS'
    - 'ASK_AMT'

  - The variable(s) that were neither targets nor features, that were removed from the input were:

    - 'EIN'
    - 'NAME'

- _Compiling, Training, and Evaluating the Model_

  - Both the models folowed the same layout:

    - 30 neurons in their first hidden layer, as the general rule is two to three times your input dimensions this seemed appropriate.
    - 15 in their second hidden layer, to narrow the training before output.
    - The output was a sigle neuron.
    - Both the first and second layers had an activation of 'relu' for its ability to train the model more effeciently.
    - The output layer had an activation of 'sigmoid' for its ability of binary classification, in out case, whether or not a funding campaign was successful.

  - Ability to meet target model performance:

    - Deliverables' 1 and 2 model was unable to meet the target accuracy of 75%

      - Model 1 accuracy score: 72.51%

    - Deliverable 3's model was able to beat the target accuracy of 75%

      - Model 2 accuracy score: 79.07%

  - The difference in accuracy between the two models came from filtering the input dataset to remove values within the "APPLICATION_TYPE" feature that heavily skewed the training of the model. The "T3" type loans greatly outnumbered the rest of the other loan types. This offset potentially gave weight to the "APPLICATION_TYPE" feature that was unneccesary and casued the model to predict incorrectly.

## Summary

    Overall the model was succesful at reaching the target accuracy but there is still room for improvement. This analysis being a binary classification could be better fit for a regression model rather than a deep learning one. By using a different learning model, potentially a Random Forest Model, that could allow for the weights of each feature to be better handled, and create more accurate predictions.

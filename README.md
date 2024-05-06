# Predicting Horse Health Using Decision Tree
***************************************
- This repository holds and attempt to apply Decision Tree to the "Predict Health Outcomes of Horses" Kaggle challenge.

### Overview
***************************************
The task, as defined by the Kaggle challenge is to use predefined medical parameters to predict the health outcomes of horses. The approach in this repository formulates the problem as classification task, using the predefined features given in the dataset as input as well as doing some clean up of the dataset. Only one machine learning model was analyzed, decision tree. Accuracy, precision, recall, and F-1 were calculated based on the training and validation set. The accuracy of the decision tree model is 83.06% indicating that the model can correctly predict the outcome around 83% of the time.

### Summary of Workdone
***************************************
- ***Data Overview***
  - Data Type: Tabular
  - train.csv (229.2 kB)
    - 1235 rows, 29 columns
  - test.csv (148.32 kB)
    - 824 rows, 28 columns
    - omits the target column ("outcome")

![download](https://github.com/cpham893/DATA3402_KaggleChallenge/assets/143844689/9edb587f-d958-4bab-95b1-7a65f3b92d98)
![download](https://github.com/cpham893/DATA3402_KaggleChallenge/assets/143844689/04840dc0-5531-4be0-87d8-c38b7192560a)

- ## **Preprocessing**
  - Duplicates: N/A
  - Outliers: N/A
  - Remove Columns: 'id', 'hospital_number', 'cp_data' 
  - Null Values: imputation (mode)
    - Columns: 'temp_of_extremities', 'peripheral_pulse', 'mucous_membrane', 'capillary_refill_time', 'pain', 'peristalsis', 'abdominal_distention', 'nasogastric_tube', 'nasogastric_reflux', 'rectal_exam_feces', 'abdomen', 'abdomo_appearance'
  - Inconsistant Data Inputs
    - 'nasogastric_reflux': replace 'slight' with mode
    - 'rectal_exam_feces': replace 'serosanguious' with mode
    - 'peristalsis': replace 'distend_small' with mode
  - Encode Categorical Features (One-Hot Encoding)
    - 'surgery', 'age', 'temp_of_extremities', 'peripheral_pulse', 'mucous_membrane', 'capillary_refill_time', 'pain', 'peristalsis', 'abdominal_distention', 'nasogastric_tube', 'nasogastric_reflux', 'rectal_exam_feces', 'abdomen', 'abdomo_appearance', 'surgical_lesion', 'outcome'
  - Normalize Numerical Features: MinMaxScaler   

- ## **Training**
    - Train: 1111 rows (90% of train.csv)
    - Validation: 124 rows (10% of train.csv)
    - Test: 824 rows (100% of test.csv)
    - Model: Decision Tree
      - max_depth=10
![download](https://github.com/cpham893/DATA3402_KaggleChallenge/assets/143844689/a307647c-b13e-4785-94c7-9a1bee21658d)

- ## **Results**
  - Accuracy: 0.8306451612903226
  - Precision: 0.8702380952380953
  - Recall: 0.8252324905550713
  - F1: 0.8413170163170163
    
![download](https://github.com/cpham893/DATA3402_KaggleChallenge/assets/143844689/bfceb230-dc6f-4258-b1ac-fcae3de01c7a)

- ## **Future Work**
  - I would try tuning and hyperparameters in order to improve my current decision tree model.
  - I would also like to try XGBoosting since it is know to be effective.
 
## How to reproduce results
***************************************
1. Download the train.csv and test.csv from the kaggle challenge (https://www.kaggle.com/code/chirag2306/predict-health-outcomes-of-horses/notebook)
2. Load the CSV files and run the DataUnderstanding_Preprocessing notebook in order to obtain the train_preprocessed.csv and test_prepocessed.csv.
3. Load the preprocessed CSV files and run the ML_DecisionTree notebook to train the model and look at the results. You can also modify the max_depth if needed.

## Citations
***************************************
 - https://www.kaggle.com/code/chirag2306/predict-health-outcomes-of-horses/notebook
 - https://www.kaggle.com/datasets/yasserh/horse-survival-dataset

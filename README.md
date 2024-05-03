# DATA3402_KaggleChallenge
***************************************
- This repository holds and attempt to apply Decision Tree to the "Predict Health Outcomes of Horses" Kaggle challenge https://www.kaggle.com/code/chirag2306/predict-health-outcomes-of-horses/notebook.

### Overview
***************************************
- Goal: The task, as defined by the Kaggle challenge is to use predefined medical parameters to predict the health outcomes of horses.
- My approach: The approach in this repository formulates the problem as classification task, using the predefined features given in the dataset as input as well as doing some mild clean up of the dataset. Only one machine learning model was analyzed. Precision, recall, F-1, R^2, and RMSE were calculated based on the model.
- Performance: The results for precision, recall, and F-1 were pretty lack-luster with all of them being <0.40. RMSE was not great either at a 1.25. R^2 recieved a -0.94.

### Libraries
***************************************
- Packages: pandas, numpy, matplotlib.pyplot, sklearn

### Summary of Workdone
***************************************
- Data:
  - train.csv (229.2 kB)
    - 1235 rows, 29 columns
  - test.csv (148.32 kB)
    - 824 rows, 28 columns
    - omits the target column ("outcome")
- Instances
    - Train: 1111 rows
    - Validation: 124 rows
    - Test: 824 rows
- Preprocessing / Clean up
  - no duplicates
  - no outliers
  - removed columns: id, hospital_number, cp_data 
  - null values: impute with mode
  - nasogastric_reflux & rectal_exam_feces had inconsistent categories: impute with mode
- Training
  - split the train.csv into train (90%) and validation (10%) since there's already a testing file
- Future Work
  - I would try tuning and hyperparameters in order to improve my current decision tree model.
  - I would also like to try XGBoosting since it is know to be effective.

 ## Citations
 ***************************************
 - https://www.kaggle.com/code/chirag2306/predict-health-outcomes-of-horses/notebook
 - https://www.kaggle.com/datasets/yasserh/horse-survival-dataset

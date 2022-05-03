## Project: Heart Disease Prediction with BRFSS Survey

### Background
The most horrible Cardiovascular Disease (CVD), heart disease, is now one of the leading causes of death around the world. There are many risk factors for heart disease, such as high blood pressure, high cholesterol, smoking, high BMI, lack of exercise, etc. Among those, the first three are the key risk factors; and about half of all Americans have at least one of them according to the Centers for Disease Control and Prevention (CDC).

This project takes the dataset from CDC to build machine learning models which could predict whether a patient is likely to have heart disease. The data are taken from the Behavioral Risk Factor Surveillance System (BRFSS) which annually organizes surveys regarding of basic health status of U.S. residents. A direct quote from the CDC is: "Established in 1984 with 15 states, BRFSS now collects data in all 50 states as well as the District of Columbia and three U.S. territories. BRFSS completes more than 400,000 adult interviews each year, making it the largest continuously conducted health survey system in the world.”

### Guideline
Here our team took the newest data, which are from 2020, to analyze and learn from. From the observation on EDA, we found that the distribution of dependent variable is highly imbalanced. The data discrimination may cause potential problems such as biased prediction which leads to a high accuracy but a relatively low AUC. Thus, for the purpose of building better models, we undersampled the data points for people who do not have a heart disease. Specifically, we constructed five classification machine learning models including Random Forest, Gradient Boosting, Bagging, Ada Boosting and Decision Tree techniques. Then we tuned hyperparameters, selected best model, evaluated its performance and conducted feature importance analysis. The findings of the project could not only serve as a method to predict the existence of a heart disease, but also educate doctors, nurses, researchers and potential patients to focus more on certain factors and take precautions in advance.

### Data
Data Resource: https://www.kaggle.com/datasets/kamilpytlak/personal-key-indicators-of-heart-disease

### Model Comparision
![image](https://user-images.githubusercontent.com/87988673/166567781-4b3460f4-627e-4918-86e1-e7f9b3ba88e6.png)
Eventually, we found the best model to be `RandomForestClassifier(criterion='entropy', max_depth=10, n_estimators=90)`. Before evaluating its performance on test set, we retrained it on the entire training set (training + validation set) and recognized it as the final model.

### Result
To sum up, Random Forest is chosen as the best among all of the classifiers, compared with other models which utilize Gradient Boosting, Bagging, Decision Tree and Adaptive Boosting techniques. For evaluation on test set, it has a high AUC of 0.838 and AP of 0.816.

![image](https://user-images.githubusercontent.com/87988673/166568147-08fd5187-377a-4a75-9ab8-28d3eb5f8e57.png)

The drawback of the project is that the false negative rate (0.199) is not as low as what we expected. Relatively inaccurate results like this may give patients a false sense of security, leading them to become lax about dieting and exercising. To deal with this, some future work needs to be done. For example, the adjustments could be: 1. use oversampling instead of undersampling to get more datapoints, which might benefit model training, tuning, evaluating and predicting. 2. perform analysis first to narrow down the number of variables (e.g. PCA), and select more proper features with heart disease to optimize the models.

![image](https://user-images.githubusercontent.com/87988673/166568209-90403e4b-2fec-48af-8e65-9ecd50ecd079.png)

For the insights, aging problem, self-evaluation, difficulty walking or climbing stairs, stroke and recent days assessment are found to be the top 5 important features for heart disease. This finding could educate doctors, nurses, researchers and potential patients to focus more on these factors and take precautions in advance.


### Project members
Jiaao Shen,
Linhui Fu,
Jingjing Wang,
Congjun Huang

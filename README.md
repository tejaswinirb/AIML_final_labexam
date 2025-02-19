# AIML_final_labexam
Problem Statement
PS: DO NOT FORGET TO TRAIN-TEST SPLIT AT AN APPROPRIATE TIME IN THE ENTIRE FLOW.

You decide where you want to position the train test split in the stages below

I. Create a pandas dataset for apples satisfying the following constraints:
Datset should have six columns - weight, volume, pesticide per apple, discoloration, machine_plucked and apple_type and 100 records with 70 Gala apples, 15 Fuji apples and 15 Red apples
Apple type is a target variable. Remaining are predictor variables.
There are 3 apple types: Gala, Fuji, Red.
Machine Plucked is either yes or no.
Simulate the data randomly such that subsequent simulations produce very similar or identical data
Simulate the data for the 3 types of apples according to the following rules:
Gala apple weights are normally distributed with mean of 155 g and a standard deviation of 5 g.
Fuji apple weights are uniformly distributed between 200 and 250 gram
Red apple weights are distributed according to triangular distribution with minimum weight of 100g, maximum weight of 190 g and the most frequent weight being 170g
Apple volumes are normally distributed for the three apple types Gala, Fuji and Red with a mean of 187cc, 270cc and 150cc respectively and variance of 25cc respectively
A pesticide Quinalphos was dissolved in water and sprayed at the rate of 500 gm per 100 apples. The spray was unequal and had a variance of 4 milligram per apple. This pestiside dosage is common to all three apple types. This data will be used to populate "pesticide per apple" feature
Discoloration of the apple is equal to the percentile of the pesticide per apple
II. Introduce NaNs
Randomly introduce NaN for weight and volume feature for 25% of the records such that the fraction of NaN for each apple type is proportional to the ratio of samples.
Pesticide_per_apple data should be randomly nulled out for data beyond 75th percentile
Randomly introduce NaN for machine plucked apples for 5% of records
Randomly introduce NaN for apple type for 10% of records
III Transform, Train/Test Split and Impute
Ask yourself these questions and do accordingly:

Will you do train test split before or after doing train test split?
Will you do transformation after imputation or before?
Will you do split before transformation?
According to your choice do these three in the order you deem fit

Impute the data for relevant columns using an appropriate imputation method fit for each scenario
If there are any records that you feel should be deleted, then please do so
Do a train test split 80:20 such that the fraction of NaN for each apple type is proportional to the ratio of samples of that apple type
Do any other data transformation you feel is needed
IV Feature Elimination and Feature Selection
If there are any features that you can immediately drop without any exploration, programming then please do so first
Check which features have highest predictive power wrt target variable
Check features on which target is dependent. Use a mechanism that is different from previous method for this.
Base on the above two checks, choose 2 features for predicting apple type
V ML Prediction
Apply Logistic Regression to predict apple type
Choose a metric that you think is most suitable for this scenario

Summary:
The project involved creating a synthetic dataset of 100 apples with attributes such as weight, volume, pesticide per apple, discoloration, machine plucked status, and apple type as the target variable. The dataset was generated with statistical distributions specific to each apple type: Gala apples followed a normal distribution for weight, Fuji apples were uniformly distributed, and Red apples had a triangular distribution. Volume was normally distributed for all types, while pesticide application was randomly varied with a fixed mean. Discoloration was derived as the percentile of pesticide per apple. Missing values were introduced strategically—weight and volume were nullified in 25% of records proportionally across apple types, pesticide values were removed for the top 25% percentile, machine plucked status was randomly nullified in 5% of records, and 10% of the target variable was also nullified. To ensure data integrity, train-test splitting was performed before imputation to prevent data leakage, maintaining an 80:20 ratio with proportional NaN distribution. Different imputation methods were applied based on the nature of missing data, such as mean for normally distributed features, mode for categorical variables, and median for skewed distributions. Data transformation included normalization, one-hot encoding, and log transformation where necessary. Feature selection was conducted by analyzing feature importance and dependencies, leading to the selection of weight and volume as the most predictive features. Finally, a Logistic Regression model was implemented to classify apple types, with F1-score chosen as the evaluation metric due to class imbalance. The approach ensured a structured pipeline for data preprocessing, imputation, feature engineering, and predictive modeling, optimizing accuracy while preserving data integrity.

# income-qualification-simplilearn

## Problem Statement :
Many social programs have a hard time making sure the right people are given enough aid. It’s tricky when a program focuses on the poorest segment of the population. This segment of population can’t provide the necessary income and expense records to prove that they qualify.

In Latin America, a popular method called Proxy Means Test (PMT) uses an algorithm to verify income qualification. With PMT, agencies use a model that considers a family’s observable household attributes like the material of their walls and ceiling or the assets found in their homes to classify them and predict their level of need. While this is an improvement, accuracy remains a problem as the region’s population grows and poverty declines.

The Inter-American Development Bank (IDB) believes that new methods beyond traditional econometrics, based on a dataset of Costa Rican household characteristics, might help improve PMT’s performance.

## Step 1: Understand the Data

The important piece of information here is that we don’t have ‘Target’ feature in Test Dataset. There are 5 object type, 130(Train set)/ 129 (test set) integer type and 8 float type features. Lets look at those features next.

Looking at the different types of data and null values for each feature. We found the following: 1. No null values for Integer type features. 2. No null values for float type features. 3. For Object types v2a1 6860 v18q1 7342 rez_esc 7928 meaneduc 5 SQBmeaned 5.

## Step 2: Data Cleaning

According to the documentation for these columns:

dependency: Dependency rate, calculated = (number of members of the household younger than 19 or older than 64)/(number of member of household between 19 and 64)

edjefe: years of education of male head of household, based on the interaction of escolari (years of education), head of household and gender, yes=1 and no=0

edjefa: years of education of female head of household, based on the interaction of escolari (years of education), head of household and gender, yes=1 and no=0

For these three variables, it seems “yes” = 1 and “no” = 0. We can correct the variables using a mapping and convert to floats.

According to the documentation for these columns:

v2a1 (total nulls: 6860) : Monthly rent payment v18q1 (total nulls: 7342) : number of tablets household owns rez_esc (total nulls: 7928) : Years behind in school meaneduc (total nulls: 5) : average years of education for adults (18+) SQBmeaned (total nulls: 5) : square of the mean years of education of adults (>=18) in the household 142

## Step 3: Predict the accuracy using random forest classifier.

## Step 4: Check the accuracy using random forest with cross validation.

Looking at the accuracy score, RandomForestClassifier with cross validation has the highest accuracy score of 94.60%

To get a better sense of what is going on inside the RandomForestClassifier model, lets visualize how our model uses the different features and which features have greater effect.



I'm sharing solution to my 1st GreyAtom Hackathon. This is my first end to end problem solution in ML using Python. Solving a problem is all about understanding data and processing it to implement model. We worked in a team size of 5 and were given four problem statements to select one.

Problem Statement::Build a model to compute probability of default for Taiwanese Credit Card Clients.

For any credit card company to run it is very crucial for them to minimize their losses. Default on credit card payment can result in great financial loss. In order to reduce or even prevent loss of this kind, banks need to determine appropriate given credit for each specific client based on their information. This can be acheived by understand there customers behaviour and able to predict probability of Customers default on Payments.

This was a clear case of supervised classification problem. As dataset I was given data for 30K Taiwanese customers including AGE,SEX,EDUCATION,MARRIAGE,LIMIT BALANCE and each last six month's bill amount, payment amount and default details.

Source The dataset is availble at the Center for Machine Learning and Intelligent Systems, Bren School of Information and Computer Science, University of California, Irvine: https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients

Insights from dataset given This Multivariate dataset is made up of 30K transactions with 24 Attributes. Overall 22.1% transaction values are default and 77.88% are not default. Categoric features: 'SEX', 'EDUCATION', 'MARRIAGE'. Numeric features: 'LIMIT_BAL', 'AGE', 'BILL_AMT1', 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4', 'BILL_AMT5', 'BILL_AMT6', 'PAY_AMT1', 'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5', 'PAY_AMT6’,'PAY_0', 'PAY_2', 'PAY_3', 'PAY_4', 'PAY_5', 'PAY_6’. Target Variable: 'default payment next month’. No Null values in any of 24 attributes provided.

We started with exploring data by making crosstabs for categorical data and did Inputation for unknown categories. Used seaborn displot to check skewness in numeric features. Did sqrt transformation on AGE and LIMIT BALANCE as data was greater than 0 and right skewed to bring data as close to normal distribution. Also applied scaling transformation using StandardScaler on numeric features. Ploted seaborn heat map to see correlation between numeric features. Also used box plot to check outliers.Performed One hot encoding on categorical features ‘SEX’, ‘MARRIAGE’ and ‘EDUCATION’ to bring then to similar scale.

Modeling We decided to use the predictive power of three bespoken classes of algorithms Logistic regression (scikit-learn) Random Forests (scikit-learn) Boosted Trees (xgboost)

On each model we applied feature selection and parameter tuning to build best predictive model. Also tried Resampling technique to best fit model.

# Network-Intrusion-Detection
Develop a binary classification model using machine learning classifiers for intrusion detection, aiming to distinguish between normal and abnormal network traffic behavior.

## Dataset 
A dataset including a wide range of simulated attacks into a military network environment was made available for assessment. By emulating a typical US Air Force LAN, it established a setting for acquiring raw TCP/IP dump data for a network. The LAN was bombarded with several attacks and concentrated like a genuine atmosphere. A connection is a series of TCP packets that begin and stop at specific times and allow data to flow from a source IP address to a target IP address according to a specific protocol. Additionally, each link has a label designating it as either normal or an attack of exactly one particular attack kind. An average connection record is 100 bytes long.
For each TCP/IP connection, 41 quantitative and qualitative features are obtained from normal and attack data (3 qualitative and 38 quantitative features) .The class variable has two categories:
• Normal
• Anomalous

## Workflow
Data Split: Split the dataset into training and testing sets, avoiding train-test contamination. Implement KFold cross-validation on the training data to assess model generalization.

Exploratory Data Analysis (EDA):

Basic Description: Provide an overview of the training data, including data appearance, feature data types, NaN ratios, and feature statistics.
Categorical Features: Analyze the three categorical features: protocol type, service, and flag.

Numeric Features:
Examine univariate distributions through histograms.
Assess statistical dispersion and variation to identify constant features.
Explore bivariate distributions after filtering features based on specific thresholds.
Groundtruth Distribution: Investigate the distribution of groundtruth labels to check for class imbalance.
KFold Cross Validation with RandomForestClassifier (RFC): Employ KFold cross-validation to evaluate model generalization. The RandomForestClassifier serves as the baseline model.

Feature Importance: Determine feature importance to identify which features significantly impact the decision-making process of the random forest model.

Evaluation on Unseen Data (Testing Set):

Assess the model's performance on the testing set.
Implement bagging to enhance prediction stability through majority voting.

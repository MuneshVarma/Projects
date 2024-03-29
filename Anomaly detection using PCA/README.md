# Anomaly Detection using PCA
## Table of Contents
  - [Anomaly Detection using PCA](#anomaly-detection-using-pca)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
  - [Problem Statement](#problem-statement)
  - [Methodology](#methodology)
  - [Technology Used](#technology-used)

## Overview
In today’s world of distributed systems, managing and monitoring the system’s performance is a chore—albeit 
a necessary chore. With hundreds or thousands of items to watch, anomaly detection can help point out where 
an error is occurring, enhancing root cause analysis and quickly getting tech support on the issue.
 Anomaly detection helps the monitoring cause of chaos engineering by detecting outliers, and informing the responsible parties to act.

## Problem Statement
- [probem statement.txt](https://github.com/MuneshVarma/Projects/blob/master/Anomaly%20detection%20using%20PCA/problem%20statement.txt)
## Methodology
1) The data was imported using pandas.read_csv().
2) The data is preprocessed with filled missing values and scaling already perfomed.
3) Since the data is from 5 sensors for 365 days, a date column was added from '01-01-2016' to '30-12-2016'. This date column was set as index. 
4) The data was split into train and test set with first 9 months as train and rest 3 months as test
5) A new column 'anomaly' was added which marked the dates between 14-02-2016 to 21-02-2016 as 1 and rest all as 0 which act as a label.
6) PCA was applied on train data to generate principal (eigen) vectors.
7) Inverse PCA was applied on the components(eigen vectors) generated from PCA. 
8) Construction loss was calculated by subtracting the original dataset from the dataset generated by inverse transform of eigen vectors.
9) This loss will be maximum for anomaly readings since the principal components will not extract the information from abnormal behaviour. 
10) To find optimum number of numbers we plot the errors for all the components. From graph we select 3 as optimum number of components.
11) From visual inspection we selected 3 as threshold. Reconstruction errors above 3 will be treated as anomaly.
12) PCA with components as 3 was applied on test data (last 3 months) and reconstruction loss above 3 was labelled as anomaly.




## Technology Used
- Jupyter Notebook
- Python

<h1> Written Answers
  
<h2> 1. Why did you choose specific imputation methods?
  
<p1> I first identified the columns that contained missing values and treated numerical and categorical features separately.
For numerical features, I used the median to impute missing values because the data contained extreme values, which could distort the mean. The median is more robust to outliers and better represents the central tendency in such cases.
For categorical features, I used the mode, as it is the most appropriate method for replacing missing values in categorical data.</p1>

<h2> 2. How did you handle outliers and why?
  
Outliers were detected using the Interquartile Range (IQR) method. The first quartile (Q1) and third quartile (Q3) were calculated, and the IQR was obtained as Q3 − Q1. Any values below Q1 − 1.5 × IQR or above Q3 + 1.5 × IQR were considered outliers.
Instead of removing these data points, I applied capping (winsorization) to limit extreme values within the acceptable range. This approach reduces the impact of outliers while preserving all data points.

<h2> 3. Where and how might data leakage occur in this dataset?
Data leakage occurs when information from the test set or future data unintentionally influences the training process, leading to overly optimistic model performance.
In this dataset, data leakage may occur if:

  Feature scaling is applied before splitting the data into training and test sets,

  Missing values are imputed using statistics calculated from the entire dataset, or

  Features that are directly related to the target variable are used incorrectly. \n

To prevent data leakage, all preprocessing steps should be performed after the train–test split and should rely only on the training data.

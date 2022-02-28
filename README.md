# DataScience
•	Documentation:
  1.	Competition Question: (ds_kaggle_assignment)
    •	Pre-processing:
      o	Dropped the columns with too many null values. (> 100) 
      o	For Training Data, filled null values with mean for integer valued columns and deleted rows with null values in categorical valued columns.
      o	For Test Data, filled null values with mean for integer valued columns and used method ‘bfill’ i.e., fill null with next valid value for categorical valued columns.
      o	Encoded categorical features in both test and training data using One-Hot Encoding.
      o	Encoding resulted in unequal columns of training and testing data, hence I found intersection of both datasets and deleted the uncommon features.
      o	Scaled both input datasets using StandardScaler().
      o	Used PCA (Principal Component Analysis) for dimensionality reduction. n_components = 100 was decided after trial and error on different values.
    •	Trained model using ‘eig’ algorithm and predicted SalesPrice.
    •	Score: 0.16769, Rank: 3287 out of 4396
2.	Comparison of 5 Algorithms: (comparisonoflralgos)
    •	Since test data didn’t have the column ‘SalePrice’ for generating metrics for comparison. I split training data into test and train to check this.
    •	Pre-processing:
      o	Dropped the columns with too many null values. (> 100) 
      o	Filled null values with mean for integer valued columns and deleted rows with null values in categorical valued columns.
      o	Encoded categorical features using One-Hot Encoding.
      o	Used train_test_split for splitting data, with test size = 0.3.
      o	Scaled xtrain and xtest using StandardScaler().
      o	Used PCA (Principal Component Analysis) for dimensionality reduction. n_components = 182 was decided after trial and error on different values.
    •	Fit 5 Algorithms in xtrain and ytrain and predicted ypred.
    • Metrics obtained are as follows:
        Algorithm	          MAE	              MSE	          R2-Score
        eig	        18303.241895261846	759142772.169576	87.90648481667125
        svd	        18303.241895261846	759142772.169576	87.90648481667117
        svd-jacobi	18303.241895261846	759142772.169576	87.90648481667117
        qr	        18303.241895261846	759142772.169576	87.90648481667121
        svd-qr	    18303.241895261846	759142772.169576	87.90648481667122
      It can be seen that there is only a minor difference in R2 Score. 

This code is for selecting features that are predictive and generalizable between two datasets using the COXEN approach [Lee et al., 2007]. Both datasets have the same set of features but different samples. Dataset 1 includes the prediction target, which can take either numeric values for regression problem or binary values for two-class classification problem. Dataset 2 does not include values of the prediction target, and we need to do prediction for samples in dataset 2. The COXEN approach takes the following steps.
First, select predictive features based on dataset 1.
Second, calculate the correlation coefficient matrices of the selected predictive features in dataset 1 and dataset 2. 
Third, based on the two correlation coefficient matrices, select the predictive features that are most generalizable between dataset 1 and dataset 2 based on the cross-correlation coefficient. The cross-correlation coefficient is the correlation coefficient between the vector of correlation coefficients of a feature against with other predictive features in dataset 1 and the vector of correlation coefficients of this feature with all other predictive features in dataset 2.

There are three functions in the module, which are ttest_FS, correlation_FS, and COXEN_FS. ttest_FS uses t-test to select predictive features for binary classification problem. correlation_FS uses Pearson correlation coefficient to select predictive features for regression problem. Based on the selected predictive features, we can use COXEN_FS to identify the predictive features that generalizable with top cross-correlation coefficients. In summary, either ttest_FS or correlation_FS needs to be used first to select predictive features, then datasets with only selected predictive features should be input into COXEN_FS for selecting generalizable features.

Reference: Lee JK, Havaleshko DM, Cho H, et al. (2007) A strategy for predicting the chemosensitivity of human cancers and its application to drug discovery. Proc Natl Acad Sci USA, 2007 Aug 7; 104(32):13086-91. Epub 2007 Jul 31.
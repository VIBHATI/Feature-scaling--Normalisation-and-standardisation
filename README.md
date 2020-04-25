# Feature-scaling--Normalisation-and-standardisation
Feature scaling is a critical pre-processing step involved developing Machine Learning/ Deep Learning based models. It is paticularly significant for cases where where the independent variables/ features have different scales. For example, when one of the features varies in the range of [0,100] and some other feature varies in the range of [0,1], we need to perform feature scaling before feeding the data to ML/DL model. Feature scaling helps the model learn better. Also, feature scaling can help gradient decent to  converge faster. 

# Normalisation : 
Re-scales the data to lie in the range 0 to 1.
# Standardisation : 
Rescales the data to have zero mean and unit variance.

#  Which part of the data should we fit to the StandardScaler() and MinMaxScaler()?
We should fit the training data and the use that to scale training and test data.

#  Do we need to standardise/ normalize the target variable? 
Generally, it's not necessary. 
(reference- https://stats.stackexchange.com/questions/111467/is-it-necessary-to-scale-the-target-value-in-addition-to-scaling-features-for-re )

#  Should we standardise the one-hot encoded variables?
No. The one-hot encoded features already have a range of [0,1] , so, no question of normalization as performing this step will have no effect on the feature. We also do not want to perform the standardisation step on the one-hot encoded features as this will change the original mean to 0 and variance to 1.

#  Do all ML algorithms require feature scaling?
- Algorithms which are distance based are impacted adversely if the input features are not scaled and have varying scales. This is because the features with higher scale will influence the distance much more than the small scaled features. Without feature scaling the features with higher scale are the ones assuming higher priority. Therefore we must perform feature scaling when we are working with the following algorithms: K-means(works on euclidean distance), KNN , LDA , PCA.

- Algorithms, such as decision tree,random forest ,that are not based on distance calculation are not affected by feature scaling. So, feature scaling is not a necessary step for these algorithms


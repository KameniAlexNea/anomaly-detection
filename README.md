# anomaly-detection

Anomaly detection on thyroid dataset

## Dataset information

The original [thyroid disease](https://archive.ics.uci.edu/ml/datasets/Thyroid+Disease) (ann-thyroid) dataset from [UCI machine learning repository](https://archive.ics.uci.edu/ml/) is a classification dataset, which is suited for training ANNs. It has 3772 training instances and 3428 testing instances. It has 15 categorical and 6 real attributes. The problem is to determine whether a patient referred to the clinic is hypothyroid. Therefore three classes are built: normal (not hypothyroid), hyperfunction and subnormal functioning. For outlier detection, 3772 training instances are used, with only 6 real attributes. The hyperfunction class is treated as outlier class and other two classes are inliers, because hyperfunction is a clear minority class.

## Source (citation)

F. Keller, E. Muller, K. Bohm.“[HiCS: High-contrast subspaces for density-based outlier ranking.](https://www.ipd.kit.edu/~muellere/publications/ICDE2012.pdf)” ICDE, 2012.

C. C. Aggarwal and S. Sathe, “[Theoretical foundations and algorithms for outlier ensembles.](http://www.kdd.org/exploration_files/Article4.pdf)” ACM SIGKDD Explorations Newsletter, vol. 17, no. 1, pp. 24–47, 2015.Downloads

Saket Sathe and Charu C. Aggarwal. [LODES: Local Density meets Spectral Outlier Detection.](http://saketsathe.net/papers/lodes.pdf) SIAM Conference on Data Mining, 2016.

## Downloads

File: [thyroid.mat](https://www.dropbox.com/s/bih0e15a0fukftb/thyroid.mat?dl=0)

Description: X = Multi-dimensional point data, y = labels (1 = outliers, 0 = inliers)

## Techniques applied

### Multivariate Gaussian

The Multivariate Gaussian appears frequently in Machine Learning and the following results are used in many ML books and courses without the derivations.

> Given data in form of a matrix **X**X of dimensions **m**×**p**m×p, if we assume that the data follows a *p-variate Gaussian* distribution with parameters mean **μ** ( **p**×**1**) and covariance matrix **Σ** (**p**×**p**) the **Maximum Likelihood Estimators** are given by:
>
> * **μ =**1**m**∑**m**i**= **1**x^(**i**)**=**x**¯**μ^=1m∑i=1mx(i)=x¯
> * **Σ** **=**1**m**∑**m**i**=**1**(**x**(**i**)**−**μ**^**)**(**x**(**i**)**−**μ**^**)**T**

|          | All features | Features<br />selection | PCA  | LOF  | IsoForest | OneClassSVM |
| -------- | ------------ | ----------------------- | ---- | ---- | --------- | ----------- |
| F1-Score | 98.3         | **98.6**               | 98.4 | 93   | 91.2      | 49.5        |
| Accuracy | 71.1         | **75.0**               | 68.4 | 10.2 | 36.5      | 9           |

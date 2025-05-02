# Decline-Curve-Analysis
Decline Curve Analysis is done for future forecasting of oil production . 
Oil and gas industry generally have smaller dataset which is most important challenge to overcome.
Making a good model requires a bigger dataset.
Apart from having a smaller dataset , we have also a problem of significant outliers. 
Removing outlier is not going to be fruitful because already we are lacking with our dataset.
we are unable to apply our traditional algorithms like Linear Regressoin, Artificial Neural Networks and others. 
So, we are using Modified Linear regression that is Huber regression todeal with outliers.
In this way we are boosting our midel performance .


Huber regression is a robust regression technique that is less sensitive to outliers than ordinary least squares (OLS). It combines the squared loss (used in OLS) and absolute loss (used in least absolute deviations). This is particularly useful in DCA, where real-world data can include sudden changes, shut-ins, or operational anomalies

Here’s how Huber regression fits into DCA:

Data Preparation:

Gather production data (typically daily/monthly oil or gas rates).

Clean data to remove clear operational artifacts (if possible).

Model Selection:
Choose a decline model:

Exponential decline: 
𝑞
(
𝑡
)
=
𝑞
𝑖
𝑒
−
𝐷
𝑡
q(t)=q 
i
​
 e 
−Dt
 

Harmonic decline: 
𝑞
(
𝑡
)
=
𝑞
𝑖
1
+
𝐷
𝑡
q(t)= 
1+Dt
q 
i
​
 
​
 

Hyperbolic decline: 
𝑞
(
𝑡
)
=
𝑞
𝑖
(
1
+
𝑏
𝐷
𝑡
)
1
/
𝑏
q(t)= 
(1+bDt) 
1/b
 
q 
i
​
 
​
 

Log Transformation (if needed):
For exponential decline, taking the natural log of both sides gives a linear form:

ln
⁡
𝑞
(
𝑡
)
=
ln
⁡
𝑞
𝑖
−
𝐷
𝑡
lnq(t)=lnq 
i
​
 −Dt
This can be fit using linear Huber regression.

Fit Model with Huber Regression:

Use Huber regression to fit the transformed or original nonlinear model.

Libraries like scikit-learn in Python offer HuberRegressor for this.

Forecast Production:
Use the fitted parameters to project future production and estimate EUR (Estimated Ultimate Recovery).

✅ Benefits of Using Huber Regression in DCA
Reduces the influence of outliers, which is common in production data.

Provides a more stable estimate of decline parameters.

Works well when you have few extreme values that skew traditional regression.



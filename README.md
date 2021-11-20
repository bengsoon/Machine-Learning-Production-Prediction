# Machine Learning Production Forecast

The idea to this repository is to create a "virtual meter" that acts as a _second opinion_ to the measurements obtained from either Multiphase Flow Meter (MPFM) or periodic welltest operations (through test separators) by taking account into the totality of each well parameters on the platform.

The models were train based on these input parameters to try to predict the daily oil production for a particular well and validated against the actual measured Oil Production values.

The beauty about the models was that it takes account into all data available (downhole gauges, wellhead data, annulus data, nearby wells etc), as opposed to physics-based models where the data considerations are limited within the domain of that particular well (eg. Reservoir, Well Model etc).

The downside to this, however, is also worth to be noted. Because it takes into account into all data available, there may be instances where the model may take correlation as a causation (which is not always true) or that the parameters may be non-physical. 

As such, results should be evaluated with care and should only serve as a "second opinion" as physics-based models should still be considered as the ultimatum to the predictions / measurements.

A few assumptions and caveats to this model:
1. The input parameters are assumed to be "trustworthy" enough to be used as input parameters.
2. The measured values (Oil Production values) are assumed to be callibrated and representative of the reality of the well performances.

## This notebook

The notebook consists of a walkthrough / **EDA** of the Volve production dataset and then exploring tree-based algorithms starting from the simplest **Decision Tree**, followed by **Random Forest** and then finally **XGBoost**.

In the XGBoost section, I also explored **Hyperparameter Grid Search** to search the optimal values to tune the XGBoost model. Finally, I performed **Feature Selection** using the feature importance tool in the XGBoost model before finalizing it.

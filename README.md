# Machine Learning Production Prediction

The idea to this repository is to create a "virtual meter" that acts as a second opinion to the measurements obtained from either Multiphase Flow Meter (MPFM) or periodic welltest operations (through test separators) by taking account into the totality of each well parameters on the platform.

## Why Not Nodal Analysis? 
Conventionally, physics-based simulation models like Nodal Analysis look at a limited framework of the wells itself, as accurate as that can be (and still is an ideal way of well modeling for Petroleum Engineers), it does not scale up well to bring in a holistic consideration of the whole production operation - such as effects of neighboring wells, backpressures from the downstream etc. 

Not only that, the process of building physics-based models like Nodal Analysis requires extensive (and not to mention, expensive) subsurface data such as fluid tests, fluid levels, downhole pressures, some of which are obtained only once  during the whole life of the field. However, subsurface (and surface, for that matter), parameters dynamically change at different phases of the field life.

Having an ML model that is adaptable and scalable to the dynamic changes of the operation can at least serve as a second opinion on top of the industry-standard physics-based models.

## Downside of ML models
As much as it can bring value, it must also be noted that there are definitely downsides to ML models. Because ML models basically brings correlations between different signals from the data to the dependent / target variable (in this case, Oil Production value), it is only as good as the data can get. There is a risk that the model prediction is "unreasonble" or "non-physical" as an ML model does not understand the "physical" boundaries of the problem. Much care must be taken for this. 

As such, it is not recommended that we use ML models for the purposes where accuracies are expected and required such as reserves reporting, in which case the true and tested physics-based models should be used.

## This notebook

The notebook consists of a walkthrough / **EDA** of the Volve production dataset and then exploring tree-based algorithms starting from the simplest **Decision Tree**, followed by **Random Forest** and then finally **XGBoost**.

In the XGBoost section, I also explored **Hyperparameter Grid Search** to search the optimal values to tune the XGBoost model. Finally, I performed **Feature Selection** using the feature importance tool in the XGBoost model before finalizing it.

## Dataset Used

The production data used here is a subset of the Volve field data which was released by Equinor. To find out more information on this subset (and other data), [click here](https://www.equinor.com/en/what-we-do/norwegian-continental-shelf-platforms/volve.html).

## Yield and Tensile Strengths Machine Learning Prediction of Fe (Steel) Alloys

### Executive summary
Steel, one of the oldest know material to mankind remains is a vital material both technologically and economically. Researchers, scientist and engineers continue to study and synthetise new alloys with unique properties for diverse advanced applications and environments. Machine learning, with it's ability to apply complex statistical calculation offers efficient and sometimes precise ways to predict properties of the materials based on mirad of features which would have been almost impossible using the convention monte carlo simulations methods. In this project, I used Random Forest Regression, Linear Regression with Polynomial Features and Ridge Regularization, Deep Neural Networks, XGBoost, and Support Vector Regression model to proedict the yield and tensile strengths of steel using the alloy's compositions as features. The two ensemple techiniques used: Random Forrest and XGB Regressors produced the lowest mean square errors and the overall best results. 

### Rationale
Steel is an alloy of iron and carbon that has played a pivotal role in the development of modern civilization. Its strength, durability, and versatility have made it an indispensable material in various industries, including construction, transportation, manufacturing, and energy. However, predicting the mechanical properties of steel, such as yield strength, tensile strength, and elongation, remains a significant challenge due to the complex interactions between its various alloying elements.

### Why is Predicting Steel Properties Important?
Researchers continue to explore and develop steel alloys with new compositions and improved performance characteristics. An understanding of the current design space can help accelerate the discovery of new alloys.
This project aims to develop predictive models for estimating the yield strength, tensile strength, and elongation of steel based on its chemical composition and other relevant factors. 

### Data Source
https://ml.materialsproject.org/projects/matbench_steels)

### Methodology
The code provided used the steel dataset from materialsproject.org (https://ml.materialsproject.org/projects/matbench_steels) demonstrates various approaches, including Random Forest Regression, Linear Regression with Polynomial Features and Ridge Regularization, Deep Neural Networks, XGBoost, and Support Vector Regression.

In addition to the model MSE, I set an artificial Pass/Fail criteria, for engineering purposes, of 10% allowable error for each prediction error (_preds_% columns). The reasons for this is in the real world, these values typically have a range to account for various measurements error and otyher variations. This value could easliy be chnaged to any other values.

### Results

#### Random Forest Regression with Grid Search
The Random Forest Regression model with Grid Search achieved the following results:
- Best Parameters: {'max_depth': 10, 'max_features': 'sqrt', 'min_samples_leaf': 1, 'min_samples_split': 2, 'n_estimators': 100}
- Best Score (Negative Mean Squared Error): -21222.820554471615
- Grid Search CV Random Forest Regressor Mean Squared Error (Test set) for Yield Strength: 13226.23401298962
- Percentage of Yield Strength Grid Search Random Forest Predictions within 10% of Actual Value: 96.47%
- Random Forest Regressor Mean Squared Error for Tensile Strength: 11157.12503723807
- Percentage of Random Forest Tensile Strength Predictions within 10% of Actual: 93.91%
- Random Forest Regressor Mean Squared Error for Elongation: 16.712264606557383
- Percentage of Random Forest Elongation Predictions within 10% of Actual: 72.61%
The Grid Search improved the Random Forest Regressor model by finding the optimal hyperparameters, resulting in a high percentage of accurate predictions within 10% of the actual values for yield strength, tensile strength, and elongation.

#### Linear Regression with Polynomial Features and Ridge Regularization
The Linear Regression model with Polynomial Features and Ridge Regularization achieved the following results:
- Best Parameters: {'polynomialfeatures__degree': 1, 'polynomialfeatures__include_bias': True, 'polynomialfeatures__interaction_only': True, 'ridge__alpha': 0.1, 'ridge__random_state': 42, 'ridge__solver': 'svd'}
- Best Score (Negative Mean Squared Error): -48656.46692222369
- Grid Search CV Linear Regressor with Polynomial Features and Ridge Regularization Mean Squared Error (Test set) for Yield Strength: 71404.69990276478
- Percentage of Yield Strength Grid Search Polynomial Regressor Predictions within 10% of Actual Value: 64.10%
While the Linear Regression model performed reasonably well, it did not achieve the same level of accuracy as the Random Forest Regressor for predicting yield strength.

#### Deep Neural Network
The Deep Neural Network model achieved the following results:
- Neural Network Mean Squared Error for Yield Strength: 56689.21484375
- Percentage of Yield Strength Predictions within 10% of Actual Value: 49.04%

The Deep Neural Network model did not perform as well as the Random Forest Regressor or the Linear Regression model in predicting the yield strength of steel accurately. I am still new to the concept; however, I find it facinating and looking forward to increase my knowledge and skills in developping better deep neural networks.

#### XGBoost
The XGBoost model achieved the following results:
- XGBoost Mean Squared Error for Yield Strength: 18539.889298940114
- Percentage of Yield Strength Predictions within 10% of Actual Value: 96.47%
The XGBoost model performed on par with the Random Forest Regressor in predicting the yield strength of steel accurately.

#### Support Vector Regression
The Support Vector Regression model achieved the following results:
- Best Parameters: {'C': 0.1, 'gamma': 'auto', 'kernel': 'poly'}
- Best Score (Negative Mean Squared Error): -39672.454757165215
- Grid Search CV Support Vector Regression Mean Squared Error (Test set) for Yield Strength: 62701.19591106039
- Percentage of Yield Strength Predictions within 10% of Actual Value: 80.45%
The Support Vector Regression model performed reasonably well but did not achieve the same level of accuracy as the Random Forest Regressor or the XGBoost model in predicting the yield strength of steel.

### Conclusion
Based on the results, the Random Forest Regression model with Grid Search performed the best in predicting the yield strength, tensile strength, and elongation of steel, with a high percentage of accurate predictions within 10% of the actual values. The XGBoost model also performed well in predicting the yield strength, achieving similar accuracy to the Random Forest Regressor. The Linear Regression model with Polynomial Features and Ridge Regularization showed promising results for yield strength prediction, while the Deep Neural Network and Support Vector Regression models did not perform as well as the other models.
It's important to note although Random Forrest Regressor performed the best, it may be more difficult to use this model to predict or interpolate data for future prediction. In that instance it seems like XGBoots may be the best predictor.
Continuous refinement and exploration of different modeling techniques, along with the integration of additional relevant features, could further improve the accuracy of predicting steel properties.

Overall, this project highlights the potential importance machine learning can play in predicting materials properties accurately using techniques such as linear regression, deep neural network and ensemble methods like Random Forest Regression and XGBoost.

#### Next steps
The current models were build on solely composition/elemental data. There are many factors that comes in to play when it comes to yield strength such as manufacturing process parameters (e.g., rolling conditions, heat treatment), microstructural features (e.g., grain size, phase fractions), environmental conditions during service (e.g., temperature, pressure). Incorporating thsese features would make more wholesome predictive models. once a final model is built, I would:
- Save the train model
- Create a development environment (still new to me)
- Load the saved model to the enviroment
- Create an API endpoint
- Monitor the model's performance and make improvement

#### Outline of project

- [Link to notebook 1]()
- [Link to notebook 2]()
- [Link to notebook 3]()


##### Contact and Further Information
jmgerie@gmail.com

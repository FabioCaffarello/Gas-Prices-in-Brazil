# Gas-Prices-in-Brazil
 - The objective of this project is to build a model to predict the average price of fuel resale in Brazil

# Data
- The data were collected from Kaggle (Available from: Matheus Eduardo Freitag)
  - Date Range: May-2004 to Jun-2019
  - **Link:** <a target="_blank" href="https://www.kaggle.com/matheusfreitag/gas-prices-in-brazil">Gas Prices in Brazil</a>
  
- **Description:** The National Agency of Petroleum, Natural Gas and Bio fuels (ANP in Portuguese) releases weekly reports of gas, diesel and other fuels prices used in transportation across the country. These datasets bring the mean value per liter, number of gas stations analyzed and other information grouped by regions and states across the country.

# Baseline

- The baseline was determined with the simple metric of stating that the price of the current week is iqual to that of the previous week
- **Notebook:** <a target="_blank" href="https://github.com/FabioCaffarello/Gas-Prices-in-Brazil/blob/master/02-NoteBooks/01-Baseline.ipynb">Baseline</a>

# Model Select

**LGBMRegressor**

- LightGBM extends the gradient boosting algorithm by adding a type of automatic feature selection as well as focusing on boosting examples with larger gradients. This can result in a dramatic speedup of training and improved predictive performance.

# Features Selection

**Gold mean:** obtained through the quandl api
**Mean Price Margin ratio:** original dataset >> average price margin ratio for the previous week's average price margin minus the average price margin of two weeks ago
**month cosine:** original dataset >> the numerical value of the month encoded by the cosine function
**ratio of current average price to Dollar:** obtained through the quandl api and original dataset >> Ratio current average price to average Dollar price

# Hyperparameter Tuning

>> The hyperparameter tuning was performed automatically through the skopt library, which performs the bayesian optimization method

# Conclusion

>> The baseline was overcome and the project can be improved with the study and implementation of other features. It can also be improved with a more robust ouco validation such as repeated Holdout or even a prequential sliding validation.

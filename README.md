# CSE151A_Project
Our first dataset had 62 rows with columns Abundance, Region, and Year. We explored a regression model to predict Abundance based on Year. We trained a linear regression model using Year to predict Abundance and evaluated its performance with metrics like Mean Squared Error (MSE), Mean Absolute Error (MAE), and Mean Absolute Percentage Error (MAPE). The results showed an intercept and coefficient for the model, which helps in predicting Abundance values for the second dataset.

We dropped one of the datasets from our previous milestone because it lacked attributes which would make it relevant for our research question. Instead, for our second dataset, we combined multiple new datasets (BATS.csv, BERM.csv, HAWI.csv) into a single combined_dataset. After renaming and cleaning up the columns, we extracted the 'Year' from the 'Sample' column and performed necessary data type conversions to numeric values. Min-Max normalization was then applied to the continuous variables (Depth, Salinity, Temp, d13C-DIC, DIC, ALK) to ensure consistent scaling of features for analysis, and any NaN values in the dataset were imputed based on the mean value for that year. We plotted pair plots for various features in the combined_dataset. After visualizing the distributions of DIC and ALK using histograms, we realized that they were only mildly skewed, so we incorporated Feature Expansion and computed the ratio of DIC to ALK as (DIC_ALK_Ratio), which could potentially help in capturing relationships in the data more effectively.

We used our previously trained abundanceModel to predict the Abundance for the combined_dataset based on the Year column. This model will provide an estimated Abundance value for each of the 1374 rows in the second dataset. The predicted Abundance values were added as a new column to the combined_dataset. We then created another Linear Regression model, which we used to train on the training set and made predictions for the validation, test, and train sets. We compared our results to that of a random model which generates predictions by sampling uniformly from the training set’s range and to that of  a baseline model. Our model outperforms both the random and baseline models. To test for overfitting or underfitting, we plotted the complexity of the model, which is varied by changing the number of features, against the training and test MSE. 

Finally, we concluded that our model performs well with low errors on both training and testing datasets, showing no signs of overfitting or underfitting. We plan to improve the model further by predicting Abundance using the exact date rather than just the year to capture finer variations in Abundance within the same year, and by exploring other fine-tuning methods.

[Link to our Project Notebook](https://colab.research.google.com/drive/1YpusAxOyCNkgLbNwInFFsIg0mX5Y-iJQ?usp=sharing)

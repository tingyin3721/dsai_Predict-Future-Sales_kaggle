# dsai_Predict-Future-Sales_kaggle
Kaggle Competition: Predict Future Sales

## 1. Description
 - Kaggle Competition: Predict Future Sales  https://www.kaggle.com/c/competitive-data-science-predict-future-sales/overview

## 2. Data File Descriptions
 - sales_train.csv - the training set. Daily historical data from January 2013 to October 2015.
 - test.csv - the test set. You need to forecast the sales for these shops and products for November 2015.
 - sample_submission.csv - a sample submission file in the correct format.
 - items.csv - supplemental information about the items/products.
 - item_categories.csv  - supplemental information about the items categories.
 - shops.csv- supplemental information about the shops.

## 3. Data Fields
 - ID - an Id that represents a (Shop, Item) tuple within the test set
 - shop_id - unique identifier of a shop
 - item_id - unique identifier of a product
 - item_category_id - unique identifier of item category
 - item_cnt_day - number of products sold. You are predicting a monthly amount of this measure
 - item_price - current price of an item
 - date - date in format dd/mm/yyyy
 - date_block_num - a consecutive month number, used for convenience. January 2013 is 0, February 2013 is 1,..., October 2015 is 33
 - item_name - name of item
 - shop_name - name of shop
 - item_category_name - name of item category

## 4. Evaluation
 - Submissions are evaluated by root mean squared error (RMSE). True target values are clipped into [0,20] range.
 - Submission File : For each id in the test set, predict a total number of sales. The file should contain a header and have the following format.

## 5. Using Method
**In this competition, I tried three method from now on.**
 - Method 1 : Using xgboost with feature engineering. LeaderBoard score is 0.90992.
 - Method 2 : Using lgbRegressor, and the feature engineering is as same as method 1. LeaderBoard score = 0.90501.
 - Method 3 : Using xgboost with different data preprocessing, feature interactions. LeaderBoard score = 0.88338.
 
**Method 3 has the best LeaderBoard score, 0.88338.**
 
## 6. Jupyter notebook link
 - Method 1 : https://nbviewer.jupyter.org/gist/tingyin3721/59ea3eb4553356f4081522b33d3ab72f
 - Method 2 : [feature engineering] https://nbviewer.jupyter.org/gist/tingyin3721/1ae300e165a614ca519cb0ab4f809e10
              [method algorithm] https://nbviewer.jupyter.org/gist/tingyin3721/5f4ca44684d1d146f9080823e72df7be
 - Method 3 : https://nbviewer.jupyter.org/gist/tingyin3721/658184e4ba74f4edb9a97fb8d74db4b6

## 7. 檔案說明
 - ./method1_xgboost/Feature engineering, xgboost.ipynb : Method 1 algorithm.
 - ./method1_xgboost/xgboost_submission.csv : Method 1 submission. LeaderBoard score = 0.90992.
 - ./method2_lgb/feature_engineering.ipynb : Data preprocessing for method2.
 - ./method2_lgb/lgb.ipynb : Method 2 algorithm.
 - ./method2_lgb/lgb_submission.csv : Method 2 submission. LeaderBoard score = 0.90501.
 - ./method3_xgboostWithDifferentDataPreprocessing/xgboost_withDifferentDataPreprocessing.ipynb : Method 3 algorithm.
 - ./method3_xgboostWithDifferentDataPreprocessing/boost_submission.csv : Method 3 submission. LeaderBoard score = 0.88338.

## 8. Reference
 **Thanks to the below authors:**
 - [Feature engineering, xgboost](https://www.kaggle.com/dlarionov/feature-engineering-xgboost)
 - [lgbRegressor](https://github.com/NoxMoon/predict-future-sales?fbclid=IwAR0pEGHZqywHNfwnGriuJy1y91YWgAQP0NPgtEhMh0bmighmWgK3RU2QQJs)
 - [Top10 solution on XGBoost](https://www.kaggle.com/obichkin/top10-solution-on-xgboost?fbclid=IwAR0okyD4pcGLaeLu9yiXaoVmbqC6luospMWKLFjfMd2FV1V6j-OYFrhOY0g)
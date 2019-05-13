# DSAI_MidtermProject
## Features of models
### V3
- 最一開始改了助教提供的 [xgboost model](https://www.kaggle.com/dhimananubhav/feature-engineering-xgboost) 裡所提供的 feature ，並將裡面的 Feature 改了一下。
- 原本的feature:
```clike=
    'date_block_num',
    'shop_id',
    'item_id',
    'item_cnt_month',
    'city_code',
    'item_category_id',
    'type_code',
    'subtype_code',
    'item_cnt_month_lag_1',
    'item_cnt_month_lag_2',
    'item_cnt_month_lag_3',
    'item_cnt_month_lag_6',
    'item_cnt_month_lag_12',
    'date_avg_item_cnt_lag_1',
    'date_item_avg_item_cnt_lag_1',
    'date_item_avg_item_cnt_lag_2',
    'date_item_avg_item_cnt_lag_3',
    'date_item_avg_item_cnt_lag_6',
    'date_item_avg_item_cnt_lag_12',
    'date_shop_avg_item_cnt_lag_1',
    'date_shop_avg_item_cnt_lag_2',
    'date_shop_avg_item_cnt_lag_3',
    'date_shop_avg_item_cnt_lag_6',
    'date_shop_avg_item_cnt_lag_12',
    'date_cat_avg_item_cnt_lag_1',
    'date_shop_cat_avg_item_cnt_lag_1',
    #'date_shop_type_avg_item_cnt_lag_1',
    #'date_shop_subtype_avg_item_cnt_lag_1',
    'date_city_avg_item_cnt_lag_1',
    'date_item_city_avg_item_cnt_lag_1',
    #'date_type_avg_item_cnt_lag_1',
    #'date_subtype_avg_item_cnt_lag_1',
    'delta_price_lag',
    'month',
    'days',
    'item_shop_last_sale',
    'item_last_sale',
    'item_shop_first_sale',
    'item_first_sale',
```
- 後來我取的 feature:
```clike=
    'date_block_num',
    'shop_id',
    'item_id',
    'item_cnt_month',
    'city_code',
    'item_category_id',
    'type_code',
    'subtype_code',
    'item_cnt_month_lag_1',
    'item_cnt_month_lag_2',
    'item_cnt_month_lag_3',
    'item_cnt_month_lag_4',
    'item_cnt_month_lag_5',
    'date_avg_item_cnt_lag_1',
    'date_item_avg_item_cnt_lag_1',
    'date_item_avg_item_cnt_lag_2',
    'date_item_avg_item_cnt_lag_3',
    'date_item_avg_item_cnt_lag_4',
    'date_item_avg_item_cnt_lag_5',
    'date_shop_avg_item_cnt_lag_1',
    'date_shop_avg_item_cnt_lag_2',
    'date_shop_avg_item_cnt_lag_3',
    'date_shop_avg_item_cnt_lag_4',
    'date_shop_avg_item_cnt_lag_5',
    'date_cat_avg_item_cnt_lag_1',
    'date_shop_cat_avg_item_cnt_lag_1',
    #'date_shop_type_avg_item_cnt_lag_1',
    #'date_shop_subtype_avg_item_cnt_lag_1',
    'date_city_avg_item_cnt_lag_1',
    'date_item_city_avg_item_cnt_lag_1',
    #'date_type_avg_item_cnt_lag_1',
    #'date_subtype_avg_item_cnt_lag_1',
    'delta_price_lag',
    'month',
    'days',
    'item_shop_last_sale',
    'item_last_sale',
    'item_shop_first_sale',
    'item_first_sale',
```
- 不一樣的 feature 在於:
```clike=
    'item_cnt_month_lag_1',
    'item_cnt_month_lag_2',
    'item_cnt_month_lag_3',
    'item_cnt_month_lag_4',
    'item_cnt_month_lag_5',
    'date_avg_item_cnt_lag_1',
    'date_item_avg_item_cnt_lag_1',
    'date_item_avg_item_cnt_lag_2',
    'date_item_avg_item_cnt_lag_3',
    'date_item_avg_item_cnt_lag_4',
    'date_item_avg_item_cnt_lag_5',
    'date_shop_avg_item_cnt_lag_1',
    'date_shop_avg_item_cnt_lag_2',
    'date_shop_avg_item_cnt_lag_3',
    'date_shop_avg_item_cnt_lag_4',
    'date_shop_avg_item_cnt_lag_5',
```
- feature importance:
![](https://i.imgur.com/nE2hBuc.png)

- 會做這些改變原因是因為想試看看 lag feature 對 xgboost model 的影響程度為何。在他的版本中只取了1,2,3,6,12，所以我取1,2,3,4,5試看看。
- LeaderBoard:==0.91213==
### V4
- feature:
```clike=
    'date_block_num', 
    'shop_id', 
    'item_id', 
    'item_cnt_month',
    'city_code',
    'item_category_id',
    'type_code',
    'subtype_code',
    'item_cnt_month_lag_1',
    'item_cnt_month_lag_2',
    'item_cnt_month_lag_3',
    'item_cnt_month_lag_4',
    'item_cnt_month_lag_5', 
    'item_cnt_month_lag_6', 
    'item_cnt_month_lag_7',
    'item_cnt_month_lag_8', 
    'item_cnt_month_lag_9', 
    'item_cnt_month_lag_10',
    'item_cnt_month_lag_11', 
    'item_cnt_month_lag_12',
    'date_avg_item_cnt_lag_1', 
    'date_item_avg_item_cnt_lag_1',
    'date_item_avg_item_cnt_lag_2',
    'date_item_avg_item_cnt_lag_3',
    'date_item_avg_item_cnt_lag_4',
    'date_item_avg_item_cnt_lag_5',
    'date_item_avg_item_cnt_lag_6',
    'date_item_avg_item_cnt_lag_7',
    'date_item_avg_item_cnt_lag_8', 
    'date_item_avg_item_cnt_lag_9',
    'date_item_avg_item_cnt_lag_10', 
    'date_item_avg_item_cnt_lag_11',
    'date_item_avg_item_cnt_lag_12',
    'date_shop_avg_item_cnt_lag_1',
    'date_shop_avg_item_cnt_lag_2', 
    'date_shop_avg_item_cnt_lag_3',
    'date_shop_avg_item_cnt_lag_4', 
    'date_shop_avg_item_cnt_lag_5',
    'date_shop_avg_item_cnt_lag_6', 
    'date_shop_avg_item_cnt_lag_7',
    'date_shop_avg_item_cnt_lag_8', 
    'date_shop_avg_item_cnt_lag_9',
    'date_shop_avg_item_cnt_lag_10',
    'date_shop_avg_item_cnt_lag_11',
    'date_shop_avg_item_cnt_lag_12', 
    'date_cat_avg_item_cnt_lag_1',
    'date_shop_cat_avg_item_cnt_lag_1', 
    'date_shop_type_avg_item_cnt_lag_1',
    'date_shop_subtype_avg_item_cnt_lag_1', 
    'date_city_avg_item_cnt_lag_1',
    'date_item_city_avg_item_cnt_lag_1',
    'date_type_avg_item_cnt_lag_1',
    'date_subtype_avg_item_cnt_lag_1', 
    'delta_price_lag_1',
    'delta_price_lag_2', 
    'delta_price_lag_3',
    'delta_price_lag_4',
    'delta_price_lag_5', 
    'delta_price_lag_6', 
    'delta_price_lag_7',
    'delta_price_lag_8',
    'delta_price_lag_9', 
    'delta_price_lag_10',
    'delta_price_lag_11',
    'delta_price_lag_12',
    'delta_revenue_lag_1',
    'month', 
    'days', 
    'item_shop_last_sale',
    'item_last_sale',
    'item_shop_first_sale', 
    'item_first_sale'
```
- v4 這個版本我想試看看，lag feature 對於 xgboost model 的影響到底有多大，上一個版本 v3 只取了1,2,3,4,5，這個版本 v4 我取了 1,2,3,4,5,6,7,8,9,10,11,12，並加入 delta_price_lag。
### V5
- V5 為 V3 + V4 ensemble 過後的結果。
- LeaderBoard:==0.91097==
### V7
- feature:
```clike=
    'date_block_num', 
    'shop_id', 
    'item_id', 
    'item_cnt_month',
    'city_code',
    'item_category_id',
    'type_code',
    'subtype_code',
    'item_cnt_month_lag_1',
    'item_cnt_month_lag_2',
    'item_cnt_month_lag_3',
    'item_cnt_month_lag_4',
    'item_cnt_month_lag_5', 
    'item_cnt_month_lag_6', 
    #'item_cnt_month_lag_7',
    #'item_cnt_month_lag_8', 
    #'item_cnt_month_lag_9', 
    #'item_cnt_month_lag_10',
    #'item_cnt_month_lag_11', 
    #'item_cnt_month_lag_12',
    'date_avg_item_cnt_lag_1', 
    'date_item_avg_item_cnt_lag_1',
    'date_item_avg_item_cnt_lag_2',
    'date_item_avg_item_cnt_lag_3',
    'date_item_avg_item_cnt_lag_4',
    'date_item_avg_item_cnt_lag_5',
    'date_item_avg_item_cnt_lag_6',
    #'date_item_avg_item_cnt_lag_7',
    #'date_item_avg_item_cnt_lag_8', 
    #'date_item_avg_item_cnt_lag_9',
    #'date_item_avg_item_cnt_lag_10', 
    #'date_item_avg_item_cnt_lag_11',
    #'date_item_avg_item_cnt_lag_12',
    'date_shop_avg_item_cnt_lag_1',
    'date_shop_avg_item_cnt_lag_2', 
    'date_shop_avg_item_cnt_lag_3',
    'date_shop_avg_item_cnt_lag_4', 
    'date_shop_avg_item_cnt_lag_5',
    'date_shop_avg_item_cnt_lag_6', 
    #'date_shop_avg_item_cnt_lag_7',
    #'date_shop_avg_item_cnt_lag_8', 
    #'date_shop_avg_item_cnt_lag_9',
    #'date_shop_avg_item_cnt_lag_10',
    #'date_shop_avg_item_cnt_lag_11',
    #'date_shop_avg_item_cnt_lag_12', 
    'date_cat_avg_item_cnt_lag_1',
    'date_shop_cat_avg_item_cnt_lag_1', 
    'date_shop_type_avg_item_cnt_lag_1',
    'date_shop_subtype_avg_item_cnt_lag_1', 
    'date_city_avg_item_cnt_lag_1',
    'date_item_city_avg_item_cnt_lag_1',
    'date_type_avg_item_cnt_lag_1',
    'date_subtype_avg_item_cnt_lag_1', 
    'delta_price_lag_1',
    'delta_price_lag_2', 
    'delta_price_lag_3',
    'delta_price_lag_4',
    'delta_price_lag_5', 
    'delta_price_lag_6', 
    #'delta_price_lag_7',
    #'delta_price_lag_8',
    #'delta_price_lag_9', 
    #'delta_price_lag_10',
    #'delta_price_lag_11',
    #'delta_price_lag_12',
    'delta_revenue_lag_1',
    'month', 
    'days', 
    'item_shop_last_sale',
    'item_last_sale',
    'item_shop_first_sale', 
    'item_first_sale'
```
- 試看看把 delta_price_lag_6 到 delta_price_lag_12 拿掉的結果。
- feature importance:
![](https://i.imgur.com/DSV6kSM.png)
- LeaderBoard:==0.91040==

### V9
- feature:
```clike=
             'date_block_num', 
             'shop_id', 
             'item_id', 
             'item_cnt_month',
             #'city_code',
             'item_category_id',
             #'type_code',
             'subtype_code',
             'item_cnt_month_lag_1',
             'item_cnt_month_lag_2',
             'item_cnt_month_lag_3',
             'item_cnt_month_lag_4',
             'item_cnt_month_lag_5', 
             'item_cnt_month_lag_6', 
             #'item_cnt_month_lag_7',
             #'item_cnt_month_lag_8', 
             #'item_cnt_month_lag_9', 
             #'item_cnt_month_lag_10',
             #'item_cnt_month_lag_11', 
             #'item_cnt_month_lag_12',
             'date_avg_item_cnt_lag_1', 
             'date_item_avg_item_cnt_lag_1',
             'date_item_avg_item_cnt_lag_2',
             'date_item_avg_item_cnt_lag_3',
             #'date_item_avg_item_cnt_lag_4',
             #'date_item_avg_item_cnt_lag_5',
             #'date_item_avg_item_cnt_lag_6',
             #'date_item_avg_item_cnt_lag_7',
             #'date_item_avg_item_cnt_lag_8', 
             #'date_item_avg_item_cnt_lag_9',
             #'date_item_avg_item_cnt_lag_10', 
             #'date_item_avg_item_cnt_lag_11',
             #'date_item_avg_item_cnt_lag_12',
             'date_shop_avg_item_cnt_lag_1',
             'date_shop_avg_item_cnt_lag_2', 
             #'date_shop_avg_item_cnt_lag_3',
             #'date_shop_avg_item_cnt_lag_4', 
             #'date_shop_avg_item_cnt_lag_5',
             #'date_shop_avg_item_cnt_lag_6', 
             #'date_shop_avg_item_cnt_lag_7',
             #'date_shop_avg_item_cnt_lag_8', 
             #'date_shop_avg_item_cnt_lag_9',
             #'date_shop_avg_item_cnt_lag_10',
             #'date_shop_avg_item_cnt_lag_11',
             #'date_shop_avg_item_cnt_lag_12', 
             'date_cat_avg_item_cnt_lag_1',
             'date_shop_cat_avg_item_cnt_lag_1', 
             'date_shop_type_avg_item_cnt_lag_1',
             'date_shop_subtype_avg_item_cnt_lag_1', 
             'date_city_avg_item_cnt_lag_1',
             'date_item_city_avg_item_cnt_lag_1',
             'date_type_avg_item_cnt_lag_1',
             'date_subtype_avg_item_cnt_lag_1', 
             'delta_price_lag_1',
             'delta_price_lag_2', 
             'delta_price_lag_3',
             'delta_price_lag_4',
             'delta_price_lag_5', 
             'delta_price_lag_6', 
             #'delta_price_lag_7',
             #'delta_price_lag_8',
             #'delta_price_lag_9', 
             #'delta_price_lag_10',
             #'delta_price_lag_11',
             #'delta_price_lag_12',
             'delta_revenue_lag_1',
             'month', 
             'days', 
             #'item_shop_last_sale',
             #'item_last_sale',
             'item_shop_first_sale', 
             'item_first_sale'
```
- 此版本將上一個版本 feature importance 較低的拿掉。
- feature importance:
![](https://i.imgur.com/ALOIExk.png)
- LeaderBoard:==0.90258==
### Final result
- 最後我將以上所有 model 依據不同的權重相加而得到最終結果。
- Finally result = 0.34125 * V3 + 0.03125 * V4 + 0.0625 * V5 + 0.25 * V7 + 0.315 * V9
- LeaderBoard:==0.89813==

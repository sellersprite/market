f### Request a gateway
{:toc #markdown-toc}
* The request gateway for external APIs is:[https://api.sellersprite.com/](https://api.sellersprite.com/)

### DEMO address
{:toc #markdown-toc2}
* DEMO code cloud address for external API access:[https://gitee.com/cdyunya/sellersprite-api-demo](https://gitee.com/cdyunya/sellersprite-api-demo)

### Public header description
{:toc #markdown-toc3}
* The access interface needs to apply for an access key. After obtaining the access key, you need to put the key into the header and pass it to the background, and the parameter type and return parameter type of the request interface are json. Request header examples:

| Header       | Value                            |
| -------------- | ---------------------------------- |
| secret-key   | 8957c4cd9rdc4a0eaa3c257e68bu767p |
| Content-Type | application/json;charset=utf-8   |

### Provider public return parameters

| Name    | Type   | Introduction | Example         |
| --------- | -------- | -------------- | ----------------- |
| code    | String | status code  | see table below |
| message | String | description  |                 |
| data    | Object | json         |                 |

### Code descriptions

| Code                     | Introduction          | Description                                                             |
| -------------------------- | ----------------------- | ------------------------------------------------------------------------- |
| OK                       | success               |                                                                         |
| ERROR_URL_NOT_FOUND      | url not found         |                                                                         |
| ERROR_SERVER_INTERNAL    | server internal error |                                                                         |
| ERROR_PARAM              | parameter error       | passed parameter is wrong, which parameter to check the content of data |
| ERROR_SECRET_KEY         | secret key error      |                                                                         |
| ERROR_SECRET_KEY_OVERDUE | secret key expired    |                                                                         |
| ERROR_VISIT_MAX          | visits exceeded       | interface access has reached the daily access or monthly access limit   |
| ERROR_SECRET_KEY_INVALID | secret key invalid    |                                                                         |

### market research

* Request URI：POST /v1/market/research

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code         | see table 1.2   | ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1   |  |
| topNum      | Integer  | Number of header listings          | 10         |  |
| newProduct  | Integer  | New Product Definition     | 6          |  |
| nodeIdPath  | String   | Category         | 172282:281407          |  |
| departmentKeyword       | String   | Category  keyword   | Electronics:Accessories & Supplies |  |
| minAvgUnits | Integer  | Minimum monthly average sales volume | 100        |  |
| maxAvgUnits | Integer  | The highest average monthly sales volume | 10000      |  |
| minAvgRevenue           | Float    | Minimum monthly average sales revenue           | 100        |  |
| maxAvgRevenue           | Float    | Maximum monthly average sales revenue           | 900        |  |
| minAvgRatings           | Integer  | Minimum average rating           | 100        |  |
| maxAvgRatings           | Integer  | Maximum average rating           | 500        |  |
| minAvgRating| Float    | Minimum average score           | 2.5        |  |
| maxAvgRating| Float    | Maximum average rating           | 3.0        |  |
| minAvgBsr   | Integer  | Lowest average BSR ranking          | 50         |  |
| maxAvgBsr   | Integer  | The highest average BSR ranking          | 100        |  |
| minAvgPrice | Float    | Minimum average price | 30         |  |
| maxAvgPrice | Float    | Maximum average price | 50         |  |
| minWeight   | Float    | Minimum weight     | 30         |  |
| maxWeight   | Float    | Maximum weight     | 60         |  |
| minVolume   | Float    | Minimum volume     | 20         |  |
| maxVolume   | Float    | Maximum volume     | 50         |  |
| minAvgProfit| Float    | Minimum average gross profit margin           | 20         |  |
| maxAvgProfit| Float    | Maximum average gross profit margin           | 70         |  |
| minTopAvgUnits          | Integer  | Minimum monthly average sales of the first part         | 200        |  |
| maxTopAvgUnits          | Integer  | The highest average monthly sales of the top tier         | 300        |  |
| minTopAvgRevenue        | Float    | Lowest monthly average sales revenue       | 2000       |  |
| maxTopAvgRevenue        | Float    | The highest monthly average sales revenue in the top tier       | 3000       |  |
| minTopAvgBsr| Integer  | Lowest head average BSR          | 68         |  |
| maxTopAvgBsr| Integer  | Maximum Head Average BSR          | 998        |  |
| minGoodsCount           | Integer  | Minimum quantity of goods | 40         |  |
| maxGoodsCount           | Integer  | Maximum quantity of goods | 90         |  |
| minBrands   | Integer  | Minimum number of brands | 10         |  |
| maxBrands   | Integer  | Maximum number of brands | 20         |  |
| minSellers  | Integer  | Minimum number of sellers | 6          |  |
| maxSellers  | Integer  | Maximum number of sellers | 10         |  |
| minAvgSellers           | Float    | Minimum average number of sellers         | 4.4        |  |
| maxAvgSellers           | Float    | Maximum average number of sellers         | 10.4       |  |
| minGoodsCrn | Float    | Minimum product concentration           | 45         |  |
| maxGoodsCrn | Float    | Maximum product concentration           | 55         |  |
| minBrandCrn | Float    | Minimum brand concentration           | 45         |  |
| maxBrandCrn | Float    | Maximum brand concentration           | 55         |  |
| maxSellerCrn| Float    | Minimum seller concentration           | 45         |  |
| minSellerCrn| Float    | Concentration of the largest sellers           | 55         |  |
| minEbcProportion        | Float    | Minimum A+quantity proportion           | 34         |  |
| maxEbcProportion        | Float    | Maximum proportion of A+quantity        | 54         |  |
| minFbaProportion        | Float    | Minimum FBA proportion  | 34         |  |
| maxFbaProportion        | Float    | Maximum proportion of FBA  | 54         |  |
| minFbmProportion        | Float    | Minimum FBM proportion  | 34         |  |
| maxFbmProportion        | Float    | Maximum proportion of FBM  | 54         |  |
| minAmazonSelfProportion | Float    | Minimum Amazon self operated proportion       | 34         |  |
| maxAmazonSelfProportion | Float    | Maximum proportion of self operated Amazon       | 56         |  |
| sellerLocation          | String   | Seller's location，see table 1.3      | US,GB      |  |
| minNewProportion        | Float    | Minimum proportion of new products         | 34         |  |
| maxNewProportion        | Float    | Maximum proportion of new products         | 56         |  |
| minNewCount | Integer  | Minimum New Product Quantity | 4          |  |
| maxNewCount | Integer  | Maximum number of new products | 20         |  |
| minNewAvgRatings        | Integer  | Minimum average rating for new products       | 23         |  |
| maxNewAvgRatings        | Integer  | Maximum average rating score for new products       | 554        |  |
| minNewAvgPrice          | Float    | Minimum average price of new products         | 34         |  |
| maxNewAvgPrice          | Float    | Maximum average price of new products         | 45         |  |
| minNewAvgRating         | Float    | Minimum average star rating for new products         | 4.0        |  |
| maxNewAvgRating         | Float    | Maximum average star rating for new products         | 4.5        |  |
| minNewAvgUnits          | Float    | Minimum monthly average sales of new products         | 400        |  |
| maxNewAvgUnits          | Float    | The highest monthly average sales of new products         | 800        |  |
| minNewAvgRevenue        | Float    | Minimum monthly average sales of new products       | 900        |  |
| maxNewAvgRevenue        | Float    | The highest monthly average sales of new products       | 2000       |  |
| page        | Integer  | Page numbers, starting from 1          | default 1    |  |
| size        | Integer  | Number of entries per page     | default 50，max 200    |  |
| order       | Object   | sort         |    |  |
| └field     | String   | sort field     | see table 1.4    |  |
| └desc      | boolean  | True is in descending order, false is in ascending order   | default desc   |  |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| marketplace           | String   | marketplace code         | US     |
| currency  | String   | The currency type of this market | USD    |
| nodeId    | String   | category ID           | 3732981|
| nodeLabelName         | String   | category name         | Mattresses         |
| nodeIdPath| String   | category id path       | 1055398:1063306:1063308:3732961:3732981    |
| nodeLabelPath         | String   | category name path     | Home & Kitchen:Furniture:Bedroom Furniture:Mattresses & Box Springs:Mattresses |
| nodeLabelLocale       | String   | Node Name Translation     | 床垫   |
| nodeLabelPathLocale   | String   | Node Name Path Translation | 家居用品 厨房:家具:家具卧室:床垫:床垫      |
| totalProducts         | Integer  | Total number of products         | 1000   |
| ranking   | Integer  | rank | 1      |
| topProducts           | Integer  | Sample quantity         | 100    |
| brands    | Integer  | Number of brands         | 34     |
| sellers   | Integer  | Number of sellers         | 60     |
| totalUnits| Integer  | Total monthly sales         | 539009 |
| totalRevenue          | Float    | Total monthly sales revenue       | 179950610.38       |
| avgUnits  | Integer  | Monthly average sales volume         | 5390   |
| avgRevenue| Float    | Monthly average sales revenue       | 1799506|
| avgPrice  | Float    | average price         | 296.11 |
| avgRatings| Integer  | Average rating score       | 14591  |
| avgRating | Float    | Average rating value       | 4.5    |
| avgBsr    | Integer  | Average BSR          | 198077 |
| baseAvgVolume         | Float    | Average volume(cm³)   | 529430.46          |
| avgVolume | Float    | Average volume(in³)   | 32307.87           |
| baseAvgWeight         | Float    | Average weight(g)      | 35301.19           |
| avgWeight | Float    | Average weight(pound)  | 77.8259|
| avgProfit | Float    | Average profit margin       | 68.76  |
| avgSellers| Float    | Average number of sellers       | 3.3    |
| ebcProportion         | Float    | A+Product proportion, percentage| 80     |
| amazonSelfProportion  | Float    | Amazon's self operated proportion, percentage        | 55     |
| fbaProportion         | Float    | FBA proportion, percentage  | 22     |
| fbmProportion         | Float    | FBM proportion, percentage   | 14     |
| sellerNation          | String   | Most sellers belong to code，see table 1.3 | US     |
| sellerNationLabel     | String   | Most sellers belong to label         | 美国   |
| sellerProportion      | Float    | Most sellers belong to           | 59.3   |
| top10Images           | List     | Pictures of the top 10 products   ||
| └asin    | String   | asin | B01IU6RJYA         |
| └image   | String   | ASIN image link     | [https://images-na.ssl-images-amazon.com/images/I/51+5VVLcXSL.\_AC\_US200\_.jpg](https://images-na.ssl-images-amazon.com/images/I/51+5VVLcXSL._AC_US200_.jpg) |
| returnRatio           | Float    | Return rate           | 3.51   |
| avgReturnRatio        | Float    | Average return rate category | 5.54   |
| searchToPurchaseRatio | Float    | Search purchase ratio| 0.94926| |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/research' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "size":20,\n  "page":1\n}' \
--compressed
```

### Category statistics

* Request URI：POST /v1/market/statistics

#### Request parameter

| Name        | Type    | Introduction        | Example        | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
|  month      | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| marketplace          | String   | marketplace code     | US    |
| currency | String   | The currency type of this market         | USD   |
| nodeIdPath           | String   | category ID   | 1064954:1069242:1069784:1069820:1069838:1069828       |
| nodeLabelPath        | String   | category name | Office Products:Office & School Supplies:Writing & Correction Supplies:Pens & Refills:Rollerball Pens:Gel Ink Rollerball Pens |
| nodeLabelLocale      | String   | Node Name Translation | 办公产品:办公室:写作:钢笔:滚珠笔:中性笔   |
| countryCode          | String   | National two simplified codes   | US    |
| totalProducts        | Integer  | Total number of products     | 5127  |
| products | Integer  | Number of sample products   | 100   |
| brands   | Integer  | Number of brands       | 4     |
| sellers  | Integer  | Number of sellers       | 58    |
| avgBsr   | Integer  | Average BSR      | 41970 |
| baseAvgVolume        | Float    | Average volume(cm³)           | 819942.68         |
| avgVolume| Float    | Average volume(in³)           | 50035.97          |
| baseAvgWeight        | Float    | Average weight(g)  | 2460.95           |
| avgWeight| Float    | Average weight(pound)          | 5.4255|
| avgProfit| Float    | Average profit margin   | 66.03 |
| avgUnits | Integer  | Monthly average sales volume     | 26255 |
| avgRevenue           | Float    | Monthly average sales revenue   | 344369|
| avgPrice | Float    | average price     | 13.91 |
| avgRatingsCv         | Integer  | Average monthly comment growth         | 0     |
| avgRatings           | Integer  | Average rating score   | 19071 |
| avgRating| Float    | Average star rating     | 4.7   |
| avgSellers           | Float    | Average number of sellers   | 5.2   |
| hlProducts           | Integer  | Number of top N product samples in the header listing           | 5     |
| hlAvgBsr | Integer  | The average BSR of the top N products in the top listing          | 13126 |
| hlAvgUnits           | Integer  | The top N products in the top listing have an average monthly sales volume         | 1123  |
| hlAvgRevenue         | Float    | The monthly average sales revenue of the top N products in the top listing       | 12342.85          |
| hlAvgPrice           | Float    | The average price of the top N products in the top listing         | 11.77 |
| hlAvgRatingsCv       | Integer  | The average growth rate of monthly reviews for the top N products in the top listing | 0     |
| hlAvgRatings         | Integer  | The average number of comments on the top N products in the top listing       | 2794  |
| hlAvgRating          | Float    | The average star rating of the top N products in the top listing         | 4.7   |
| newProducts          | Integer  | Number of new products     | 67    |
| newProductProportion | Float    | Proportion of new product quantity | 67    |
| newAvgPrice          | Float    | Average price of new products | 14.14 |
| newAvgRatings        | Integer  | Average rating score for new products           | 24295 |
| minNewRatings        | Integer  | Minimum New Product Review Score           | 24    |
| maxNewRatings        | Integer  | Highest New Product Review Score           | 6432  |
| newAvgRating         | Float    | Average star rating of new products | 4.7   |
| newAvgUnits          | Integer  | Monthly average sales of new products | 26425 |
| newAvgRevenue        | Float    | Monthly average sales revenue of new products           | 350209.91         |
| firstShelfDate       | String   | First listing date of the product         | 2014-10-30        |
| lastShelfDate        | String   | Latest listing date of the product         | 2021-04-28        |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/statistics' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Product concentration

* Request URI：GET /v1/market/goods

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| asins       | List     | filter asin     | ["B00P19MFYE"]          |  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| title | String   | tile        | Pilot G2, Dr. Grip Gel/Ltd, ExecuGel G6, Q7 Rollerball Gel Ink Pen Refills, 0.7mm, Fine Point, Black Ink, 3 Packs of 2         |
| asin  | String   | asin        | B00P19MFYE         |
| asinUrl           | String   | asin url    | [https://www.amazon.com/dp/B00P19MFYE](https://www.amazon.com/dp/B00P19MFYE)          |
| imageUrl          | String   | image url    | [https://images-na.ssl-images-amazon.com/images/I/51hxvoxGnjL.\_AC\_US200\_.jpg](https://images-na.ssl-images-amazon.com/images/I/51hxvoxGnjL._AC_US200_.jpg) |
| ranking           | Integer  | rank        | 1      |
| brand | String    | brank        | PILOT  |
| sellerName        | String   | seller name    | JA Wholesale LLC   |
| sellerType        | String   | seller type    | FBA    |
| price | Float     | price        | 6.19   |
| shelfDate         | String   | Listing time    | 2014-10-30         |
| ratings           | Integer  | Score evaluation      | 5695   |
| reviews           | Integer  | Number of comments      | 133    |
| rating| Float     | Comment value      | 4.8    |
| newFlag           | Integer  | Is it a new product? 1 new product, 0 non new product | 0      |
| totalUnits        | Integer  | Total sales volume      | 2515   |
| totalRevenue      | Float    | Total sales      | 18837.35           |
| totalUnitsRatio   | Float    | Total sales proportion  | 0.4478 |
| totalRevenueRatio | Float    | Proportion of total sales  | 0.3052 |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/goods' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Brand concentration

Request URI: POST /v1/market/brand

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| brand | String   | 品牌名称           | PILOT          |
| ranking           | Integer  | 排名   | 1  |
| asins | List     | 包含的商品ASIN集合 | ["B00P19MFYE"] |
| products          | Integer  | 商品数量，包含新品 | 4  |
| newProducts       | Integer  | 新品数量           | 1  |
| newUnits          | Integer  | 新品销量           | 45 |
| newRevenue        | Float    | 新品销售额         | 2342           |
| newUnitsRatio     | Float    | 新品销量占比       | 4.3|
| newRevenueRatio   | Float    | 新品销售额占比     | 4  |
| avgPrice          | Float    | 平均价格           | 6.19           |
| ratings           | Integer  | 评分数 | 5695           |
| rating| Float    | 评分值 | 4.8|
| reviews           | Integer  | 评论数 | 234|
| totalUnits        | Integer  | 总销量 | 32342          |
| totalRevenue      | Float    | 总销额 | 18837.35       |
| totalUnitsRatio   | Float    | 总销量占比         | 0.4478         |
| totalRevenueRatio | Float    | 总销额占比         | 0.3052         |

####

#### Request example

```
    curl 'https://api.sellersprite.com/v1/market/brand' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 卖家集中度

Request URI: POST /v1/market/seller

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| name  | String   | 卖家名称           | JA Wholesale LLC |
| ranking           | Integer  | 排名   | 1    |
| asinSet           | List     | 包含的商品ASIN集合 | ["B00P19MFYE"]   |
| products          | Integer  | 商品数量，包含新品 | 4    |
| newProducts       | Integer  | 新品数量           | 1    |
| newUnits          | Integer  | 新品销量           | 45   |
| newRevenue        | Float    | 新品销售额         | 2342 |
| newUnitsRatio     | Float    | 新品销量占比       | 4.3  |
| newRevenueRatio   | Float    | 新品销售额占比     | 4    |
| avgPrice          | Float    | 平均价格           | 6.19 |
| ratings           | Integer  | 评分数 | 5695 |
| rating| Float    | 评分值 | 4.8  |
| reviews           | Integer  | 评论数 | 234  |
| totalUnits        | Integer  | 总销量 | 32342|
| totalRevenue      | Float    | 总销额 | 18837.35         |
| totalUnitsRatio   | Float    | 总销量占比         | 0.4478           |
| totalRevenueRatio | Float    | 总销额占比         | 0.3052           |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/seller' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 卖家类型分布

Request URI: POST /v1/market/seller/type

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | 类型说明     | Amazon自营 |
| asinNum    | Integer  | ASIN数量     | 4          |
| asinRatio  | Float    | ASIN数量占比 | 0.03       |
| units      | Integer  | 月销量       | 79875      |
| unitsRatio | Float    | 月销量占比   | 0.0345     |
| ratings    | Integer  | 评分数       | 6607       |
| rating     | Float    | 评分值       | 4.7        |
| productNum | Integer  | 商品总数     | 3          |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/seller/type' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 卖家所属地分布

Request URI: POST /v1/market/seller/location

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | 类型说明       | 美国           |
| country    | String   | 国家           | 美国           |
| asins      | List     | 包含的asin列表 | ["B00P19MFYE"] |
| products   | Integer  | 产品数         | 3  |
| revenue    | Float    | 销售额         | 47492.83       |
| units      | Integer  | 销量           | 4107           |
| unitsRatio | Float    | 销量占比       | 0.7313         |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/seller/location' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 商品需求趋势

Request URI: POST /v1/market/performance

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| asinCount    | String   | asin数量       | 22187      |
| returnRatio  | String   | 退货率，百分比 | 1.38       |
| searchToPurchaseRatio    | List     | 搜索购买比，千分比         | 3.17875    |
| avgReturnRatio           | Integer  | 类目平均退货率，百分比     | 2.72       |
| avgSearchToPurchaseRatio | Float    | 类目平均搜索购买比，千分比 | 2.6        |
| items        | List     | 月浏览趋势     |    |
| └date       | String   | 时间，yyyy-MM-dd格式       | 2022-09-10 |
| └glanceViews| Integer  | 浏览量         | 2          |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/performance' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 上架时间分布

Request URI: POST /v1/market/shelf/time

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | 类型说明       | 3年以上        |
| shelfTime  | String   | 上架时间       | 3年以上        |
| asins      | List     | 包含的asin列表 | ["B00P19MFYE"] |
| products   | Integer  | 产品数         | B07Z82895W     |
| revenue    | Float    | 销售额         | 40846.76       |
| units      | Integer  | 销量           | 4684           |
| unitsRatio | Float    | 销量占比       | 0.834          |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/shelf/time' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 上架趋势分布

Request URI: POST /v1/market/shelf/trend

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | 类型说明       | 2014           |
| year       | String   | 年份，yyyy格式 | 2014           |
| asins      | List     | 包含的asin列表 | ["B00P19MFYE"] |
| products   | Integer  | 产品数         | 1  |
| revenue    | Float    | 销售额         | 2515           |
| units      | Integer  | 销量           | 18837.35       |
| unitsRatio | Float    | 销量占比       | 0.4478         |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/shelf/trend' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 评分数分布

Request URI: POST /v1/market/ratings

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | 类型说明       | 500以上        |
| asins      | List     | 包含的asin列表 | 5  |
| products   | Integer  | 产品数         | ["B00P19MFYE"] |
| revenue    | Float    | 销售额         | 61714.24       |
| units      | Integer  | 销量           | 5616           |
| unitsRatio | Float    | 销量占比       | 0.9743         |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/ratings' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 评分值分布

Request URI: POST /v1/market/rating

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | 类型说明       | 4.5以上        |
| asins      | List     | 包含的asin列表 | ["B00P19MFYE"] |
| products   | Integer  | 产品数         | 5  |
| revenue    | Float    | 销售额         | 59934.22       |
| units      | Integer  | 销量           | 5418           |
| unitsRatio | Float    | 销量占比       | 0.9647         |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/rating' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### 价格分布

Request URI: POST /v1/market/price

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | 类型说明       | 5-10           |
| asins      | List     | 包含的asin列表 | ["B00P19MFYE"] |
| products   | Integer  | 产品数         | 3  |
| revenue    | Float    | 销售额         | 33058.76       |
| units      | Integer  | 销量           | 4024           |
| unitsRatio | Float    | 销量占比       | 0.7165         |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/price' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### A+视频分布

Request URI: POST /v1/market/ebc

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | 市场 id      | 见表 1.2    | ✓       |
|  month      | String   | 筛选日期,默认最近30天，最早查询时间为2021年7月份 | 见表 1.1    |  |
| topN        | Integer  | 头部Listing数量          | 10          |  |
| newProduct  | Integer  | 新品定义     | 6           |  |
| nodeIdPath  | String   | 节点 id 路径字符串       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label         | String   | 类型说明         | 有A+有视频 |
| products      | Integer  | 产品数           | 1          |
| productsRatio | Float    | 类目名称产品占比 | 20         |
| units         | Integer  | 销量 | 1311       |
| unitsRatio    | Float    | 销量占比         | 23.34      |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/ebc' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: 你的密钥' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

        ## 附录

#### 表 1.1 查询日期

| 参数值        | 说明   |
| ------------------- | ------------------------------------ |
| nearly        | 最近 30 天         |
| 格式为 yyyyMM | 具体某一月，代表某一个月的日期 |

#### 表 1.2 市场

| 参数值 | 说明     |
| ------------ | -------------- |
| US     | 美国站   |
| UK     | 英国站   |
| DE     | 德国站   |
| FR     | 法国站   |
| JP     | 日本站   |
| CA     | 加拿大站 |
| IT     | 意大利   |
| ES     | 西班牙   |

| 参数值 | 说明     |
| ------------ | -------------- |
| EN     | 信封装   |
| ST     | 标准     |
| OS     | 大件     |
| O      | 其他尺寸 |

#### 表 1.3 卖家所属地

| 参数值 | 说明         |
| ------------ | ------------------ |
| CN     | 中国         |
| HK     | 中国香港特区 |
| US     | 美国         |
| JP     | 日本         |
| DE     | 德国         |
| FR     | 法国         |

其他国家二字码见链接：[http://www.mamicode.com/info-detail-1583748.html](http://www.mamicode.com/info-detail-1583748.html)

#### 表 1.4 选产品和查竞品排序字段

| 参数值   | 说明           |
| -------------------------- | -------------------- |
| total_units          | 月销量         |
| total_amount         | 月销售额       |
| bsr_rank | bsr排名        |
| price    | 价格           |
| rating   | 评分           |
| reviews  | 评分数         |
| profit   | 毛利率         |
| reviews_rate         | 留评率         |
| available_date       | 上架时间       |
| questions| Q & A          |
| total_units_growth   | 月销量增长率   |
| total_amount_growth  | 月销售额增长率 |
| reviews_increasement | 月新增评分数   |
| bsr_rank_cv          | 近7天BSR增长数 |
| bsr_rank_cr          | 近7天BSR增长率 |

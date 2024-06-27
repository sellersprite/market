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
| month      | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
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
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| brand | String   | brand           | PILOT          |
| ranking           | Integer  | rank   | 1  |
| asins | List     | The set of ASINs for the included products | ["B00P19MFYE"] |
| products          | Integer  | Product quantity, including new products | 4  |
| newProducts       | Integer  | Number of new products           | 1  |
| newUnits          | Integer  | New product sales           | 45 |
| newRevenue        | Float    | New product sales         | 2342           |
| newUnitsRatio     | Float    | New product sales proportion       | 4.3|
| newRevenueRatio   | Float    | New product sales proportion     | 4  |
| avgPrice          | Float    | average price           | 6.19           |
| ratings           | Integer  | Score evaluation | 5695           |
| rating| Float    | Rating value | 4.8|
| reviews           | Integer  | Number of comments | 234|
| totalUnits        | Integer  | Total sales volume | 32342          |
| totalRevenue      | Float    | Total sales | 18837.35       |
| totalUnitsRatio   | Float    | Total sales proportion         | 0.4478         |
| totalRevenueRatio | Float    | Proportion of total sales         | 0.3052         |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/brand' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Seller concentration

Request URI: POST /v1/market/seller

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| name  | String   | seller name           | JA Wholesale LLC |
| ranking           | Integer  | rank   | 1    |
| asinSet           | List     | The set of ASINs for the included products | ["B00P19MFYE"]   |
| products          | Integer  | Product quantity, including new products | 4    |
| newProducts       | Integer  | Number of new products           | 1    |
| newUnits          | Integer  | New product sales           | 45   |
| newRevenue        | Float    | New product sales         | 2342 |
| newUnitsRatio     | Float    | New product sales proportion       | 4.3  |
| newRevenueRatio   | Float    | New product sales proportion     | 4    |
| avgPrice          | Float    | Average price | 6.19 |
| ratings           | Integer  | Score evaluation | 5695 |
| rating| Float    | Rating value | 4.8  |
| reviews           | Integer  | Number of comments | 234  |
| totalUnits        | Integer  | Total sales volume | 32342|
| totalRevenue      | Float    | Total sales | 18837.35         |
| totalUnitsRatio   | Float    | Total sales proportion         | 0.4478           |
| totalRevenueRatio | Float    | Proportion of total sales         | 0.3052           |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/seller' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Distribution of seller types

Request URI: POST /v1/market/seller/type

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | Type Description     | Amazon self operated |
| asinNum    | Integer  | Number of ASINs     | 4          |
| asinRatio  | Float    | The proportion of ASIN quantity | 0.03       |
| units      | Integer  | Monthly sales volume       | 79875      |
| unitsRatio | Float    | Monthly sales proportion   | 0.0345     |
| ratings    | Integer  | Score evaluation       | 6607       |
| rating     | Float    | Rating value       | 4.7        |
| productNum | Integer  | Total number of products     | 3          |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/seller/type' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Distribution of seller's location

Request URI: POST /v1/market/seller/location

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | Type Description       | 美国           |
| country    | String   | country           | 美国           |
| asins      | List     | List of ASINs included | ["B00P19MFYE"] |
| products   | Integer  | Number of products         | 3  |
| revenue    | Float    | value of sales         | 47492.83       |
| units      | Integer  | sales volume           | 4107           |
| unitsRatio | Float    | Sales proportion       | 0.7313         |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/seller/location' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Product demand trend

Request URI: POST /v1/market/performance

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| asinCount    | String   | Number of ASINs       | 22187      |
| returnRatio  | String   | Return rate, percentage | 1.38       |
| searchToPurchaseRatio    | List     | Search purchase ratio         | 3.17875    |
| avgReturnRatio           | Integer  | Average return rate of categories, percentage     | 2.72       |
| avgSearchToPurchaseRatio | Float    | Average search to purchase ratio of categories, percentage per thousand | 2.6        |
| items        | List     | Monthly browsing trends     |    |
| └date       | String   | Time, yyyy MM dd format       | 2022-09-10 |
| └glanceViews| Integer  | View volume         | 2          |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/performance' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Distribution of listing time

Request URI: POST /v1/market/shelf/time

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | Type Description       |         |
| shelfTime  | String   | Listing time       | 3年以上        |
| asins      | List     | List of ASINs included | ["B00P19MFYE"] |
| products   | Integer  | Number of products         | B07Z82895W     |
| revenue    | Float    | value of sales         | 47492.83       |
| units      | Integer  | sales volume           | 4107           |
| unitsRatio | Float    | Sales proportion       | 0.7313         |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/shelf/time' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Distribution of Listing Trends

Request URI: POST /v1/market/shelf/trend

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | Type Description       |            |
| year       | String   | Year, in yyyy format | 2014           |
| asins      | List     | List of ASINs included | ["B00P19MFYE"] |
| products   | Integer  | Number of products         | 1  |
| revenue    | Float    | value of sales         | 47492.83       |
| units      | Integer  | sales volume           | 4107           |
| unitsRatio | Float    | Sales proportion       | 0.7313         |

####

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/shelf/trend' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Score distribution

Request URI: POST /v1/market/ratings

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |


#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | Type Description       |            |
| asins      | List     | List of ASINs included | ["B00P19MFYE"] |
| products   | Integer  | Number of products         | 1  |
| revenue    | Float    | value of sales         | 47492.83       |
| units      | Integer  | sales volume           | 4107           |
| unitsRatio | Float    | Sales proportion       | 0.7313         |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/ratings' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Score distribution

Request URI: POST /v1/market/rating

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | Type Description       |            |
| asins      | List     | List of ASINs included | ["B00P19MFYE"] |
| products   | Integer  | Number of products         | 1  |
| revenue    | Float    | value of sales         | 47492.83       |
| units      | Integer  | sales volume           | 4107           |
| unitsRatio | Float    | Sales proportion       | 0.7313         |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/rating' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### Price distribution

Request URI: POST /v1/market/price

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | Type Description       |            |
| asins      | List     | List of ASINs included | ["B00P19MFYE"] |
| products   | Integer  | Number of products         | 1  |
| revenue    | Float    | value of sales         | 47492.83       |
| units      | Integer  | sales volume           | 4107           |
| unitsRatio | Float    | Sales proportion       | 0.7313         |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/price' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

### A+Video Distribution

Request URI: POST /v1/market/ebc

#### Request parameter

| Name| Type    | Introduction        | Example      | Required |
| ----------------- | --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------- |
| marketplace | String   | marketplace code       | see table 1.2| ✓       |
| month       | String   | The filter date is the last 30 days by default, and the earliest query time is July 2021 | see table 1.1|  |
| topN        | Integer  | Number of header listings          | 10          |  |
| newProduct  | Integer  | New Product Definition     | 6           |  |
| nodeIdPath  | String   | Node ID path string       | 1064954:1069242:1069784:1069820:1069838:1069828 | ✓       |

#### Response parameter

| Name           | Type    | Description        | Example         |
| ---------------- | --------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| label      | String   | Type Description       |            |
| products   | Integer  | Number of products         | 1  |
| revenue    | Float    | value of sales         | 47492.83       |
| units      | Integer  | sales volume           | 4107           |
| unitsRatio | Float    | Sales proportion       | 0.7313         |

#### Request example

```
curl 'https://api.sellersprite.com/v1/market/ebc' \
-H 'Content-Type: application/json;charset=UTF-8' \
-H 'secret-key: your secret key' \
--data-raw $'{\n  "marketplace":"US",\n  "nodeIdPath":"1064954:1069242:1069784:1069820:1069838:1069828"\n}' \
--compressed
```

## Appendix

#### Table 1.1 Query month

| Value              | description           |
| -------------------- | ----------------------- |
| nearly             | last 30 days          |
| formated as yyyyMM | example:202202202213  |

#### Table 1.2 Marketplace code

| Value | Description    |
| ------- | ---------------- |
| US    | United States  |
| UK    | United Kingdom |
| DE    | Germany        |
| FR    | France         |
| JP    | Japan          |
| CA    | Canada         |
| IT    | Italy          |
| ES    | Spain          |

#### Table 1.3 Seller's Nationality

| Value | Description     |
| ------- | ----------------- |
| CN    | China           |
| HK    | Hong Kong,China |
| US    | United States   |
| JP    | Japan           |
| DE    | Germany         |
| FR    | France          |

See link for 2-character codes for other countries：[http://www.mamicode.com/info-detail-1583748.html](http://www.mamicode.com/info-detail-1583748.html)

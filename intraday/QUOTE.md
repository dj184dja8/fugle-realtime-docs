# QUOTE

提供盤中個股/指數逐筆交易金額、狀態、最佳五檔及統計資訊

```
GET /intraday/quote
```

```
curl -X GET "https://api.fugle.tw/realtime/v0.3/intraday/quote?symbolId=2884&apiToken=demo" -H "accept: */*"
```

## Example

### request url
```
https://api.fugle.tw/realtime/v0.3/intraday/quote?symbolId=2884&apiToken=demo
```

### websocket
```
wss://api.fugle.tw/realtime/v0.3/intraday/quote?symbolId=2884&apiToken=demo
```

### parameters
| Name | Type | Required | Description |
|:--|:--|:--|:--|
|  `symbolId` | string | yes | 個股、指數識別代碼 |
|  `apiToken` | string | yes | personal api token |
|  `oddLot` | boolean | no | 設置 `true` 回傳零股行情。預設值：`false` |

### response
```json
{
  "apiVersion": "0.3.0",
  "data": {
    "info": {
      "date": "2021-09-30",
      "type": "EQUITY",
      "exchange": "TWSE",
      "market": "TSE",
      "symbolId": "2884",
      "countryCode": "TW",
      "timeZone": "Asia/Taipei",
      "lastUpdatedAt": "2021-09-30T13:30:00.000+08:00"
    },
    "quote": {
      "isCurbing": false,
      "isCurbingFall": false,
      "isCurbingRise": false,
      "isTrial": false,
      "isOpenDelayed": false,
      "isCloseDelayed": false,
      "isHalting": false,
      "isClosed": true,
      "total": {
        "at": "2021-09-30T13:30:00.000+08:00",
        "transaction": 1900,
        "tradeValue": 487239.45,
        "tradeVolume": 18556,
        "tradeVolumeAtBid": 12779,
        "tradeVolumeAtAsk": 5278,
        "serial": 6324797
      },
      "trial": {
        "at": "2021-09-30T13:29:56.580+08:00",
        "bid": 26.3,
        "ask": 26.35,
        "price": 26.3,
        "volume": 7087
      },
      "trade": {
        "at": "2021-09-30T13:30:00.000+08:00",
        "bid": 26.3,
        "ask": 26.35,
        "price": 26.3,
        "volume": 7278,
        "serial": 6324797
      },
      "order": {
        "at": "2021-09-30T13:30:00.000+08:00",
        "bids": [
          {
            "price": 26.3,
            "volume": 85
          },
          {
            "price": 26.25,
            "volume": 962
          },
          {
            "price": 26.2,
            "volume": 3027
          },
          {
            "price": 26.15,
            "volume": 1936
          },
          {
            "price": 26.1,
            "volume": 2042
          }
        ],
        "asks": [
          {
            "price": 26.35,
            "volume": 1211
          },
          {
            "price": 26.4,
            "volume": 2198
          },
          {
            "price": 26.45,
            "volume": 1491
          },
          {
            "price": 26.5,
            "volume": 1620
          },
          {
            "price": 26.55,
            "volume": 879
          }
        ]
      },
      "priceHigh": {
        "price": 26.35,
        "at": "2021-09-30T09:00:15.041+08:00"
      },
      "priceLow": {
        "price": 26.15,
        "at": "2021-09-30T09:14:33.355+08:00"
      },
      "priceOpen": {
        "price": 26.35,
        "at": "2021-09-30T09:00:15.041+08:00"
      },
      "priceAvg": {
        "price": 26.26,
        "at": "2021-09-30T13:30:00.000+08:00"
      },
      "change": -0.05,
      "changePercent": -0.19,
      "amplitude": 0.76,
      "priceLimit": 0
    }
  }
}
```

## Schema
| Name | Type | Description |
|:--|:--|:--|
|  `apiVersion` | string |  api version |
|  `data` | [data object](#data-object) |  - |

### data object
| Name | Type | Description |
|:--|:--|:--|
|  `info` | [info object](#info-object) | - |
|  `quote` | [quote object](#quote-object) | -  |


### info object
| Name | Type | Description |
|:--|:--|:--|
|  `date` | string | 本筆資料所屬日期 |
|  `type` | string | ticker 類別 |
|  `exchange` | string | 交易所|
|  `market` | string | 市場別 |
|  `symbolId` | string | 股票代號 |
|  `countryCode` | string | 股票所屬國家ISO2代碼 |
|  `timeZone` | string | 股票所屬時區 |
|  `lastUpdatedAt` | ISO 8601 | 本筆資料最後更新時間 |


### quote object
| Name | Type | Description |
|:--|:--|:--|
|  `isCurbing` | boolean | 最近一次更新是否為瞬間價格穩定措施 |
|  `isCurbingFall` | boolean | 最近一次更新是否為暫緩撮合且瞬間趨跌 |
|  `isCurbingRise` | boolean | 最近一次更新是否為暫緩撮合且瞬間趨漲 |
|  `isTrial` | boolean |  最近一次更新是否為試算 |
|  `isOpenDelayed` | boolean | 最近一次更新是否為延後開盤狀態 |
|  `isCloseDelayed` | boolean | 最近一次更新是否為延後收盤狀態 |
|  `isHalting` | boolean | 最近一次更新是否為暫停交易 |
|  `isClosed` | boolean | 當日是否為已收盤 |
|  `total` | [total object](#total-object) |   |
|  `trial` | [trial object](#trial-object) |   |
|  `trade` | [trade object](#trade-object) |   |
|  `order` | [order object](#order-object) |   |
|  `priceHigh` | [price object](#price-object) | 當日之最高價<br/>第一次到達當日最高價之時間 |
|  `priceLow` | [price object](#price-object) | 當日之最低價<br/>第一次到達當日最低價之時間 |
|  `priceOpen` | [price object](#price-object) | 當日之開盤價，開盤定義：當天第一筆成交時才開盤<br/>當日第一筆成交時間 |
|  `priceAvg` | [price object](#price-object) | 當日之成交均價<br/>當日最後一筆成交時間 |
|  `change` | number | 當日股價之漲跌 |
|  `changePercent` | number | 當日股價之漲跌幅 |
|  `amplitude` | number | 當日股價之振幅 |
|  `priceLimit` | number | 0 = 正常；1 = 跌停；2 = 漲停 |


### total object
| Name | Type | Description |
|:--|:--|:--|
|  `at` | ISO 8601 | 最新一筆成交時間  |
|  `transaction` | number | 總成交筆數 |
|  `tradeValue` | number | 總成交金額 |
|  `tradeVolume` | number |  總成交數量 |
|  `tradeVolumeAtBid` | number |  個股內盤成交量 |
|  `tradeVolumeAtAsk` | number |  個股外盤成交量 |
|  `bidOrders` | number |  總委買筆數 (僅加權、櫃買指數) |
|  `askOrders` | number |  總委賣筆數 (僅加權、櫃買指數) |
|  `bidVolume` | number |  總委買數量 (僅加權、櫃買指數) |
|  `askVolume` | number |  總委賣數量 (僅加權、櫃買指數) |
|  `serial` | number |  最新一筆成交之序號 |


### trial object
| Name | Type | Description |
|:--|:--|:--|
|  `at` | ISO 8601 | 最新一筆試撮時間  |
|  `bid` | number |  最新一筆試撮買進價 |
|  `ask` | number |  最新一筆試撮賣出價 |
|  `price` | number |  最新一筆試撮成交價 |
|  `volume` | number |  最新一筆試撮成交量 |


### trade object
| Name | Type | Description |
|:--|:--|:--|
|  `at` | ISO 8601 | 最新一筆成交時間  |
|  `bid` | number |  最新一筆成交買進價 |
|  `ask` | number |  最新一筆成交賣出價 |
|  `price` | number |  最新一筆成交價 |
|  `volume` | number |  最新一筆成交量 |
|  `serial` | number |  最新一筆成交之序號 |


### order object
| Name | Type | Description |
|:--|:--|:--|
|  `at` | ISO 8601 | 最新一筆最佳五檔更新時間  |
|  `bids` | [[bid ask object](#bid-ask-object)] |   |
|  `asks` | [[bid ask object](#bid-ask-object)] |   |


#### bid ask object
| Name | Type | Description |
|:--|:--|:--|
|  `price` | number | 價格  |
|  `volume` | number | 數量 |

#### price object
| Name | Type | Description |
|:--|:--|:--|
|  `price` | number | 價格  |
|  `at` | ISO 8601 |  時間 |
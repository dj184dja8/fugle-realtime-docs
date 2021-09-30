# DEALTS

取得個股當日所有成交資訊（ex: 個股價量、大盤總量）

```
GET /intraday/dealts
```

```
curl -X GET "https://api.fugle.tw/realtime/v0.3/intraday/dealts?symbolId=2884&apiToken=demo" -H "accept: */*"
```

## Example

### request url
```
https://api.fugle.tw/realtime/v0.3/intraday/dealts?symbolId=2884&apiToken=demo&limit=5
```

### parameters
| Name | Type | Required | Description |
|:--|:--|:--|:--|
|  `symbolId` | string | yes | 個股、指數識別代碼 |
|  `apiToken` | string | yes | realtime api token |
|  `limit` | number | no | 限制最多回傳的資料筆數。預設值：`50` |
|  `offset` | number | no | 指定從第幾筆後開始回傳。預設值：`0` |
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
      "timeZone": "Asia/Taipei"
    },
    "dealts": [
      {
        "at": "2021-09-30T13:30:00.000+08:00",
        "bid": 26.3,
        "ask": 26.35,
        "price": 26.3,
        "volume": 7278,
        "serial": 6324797
      },
      {
        "at": "2021-09-30T13:24:58.979+08:00",
        "bid": 26.25,
        "ask": 26.3,
        "price": 26.3,
        "volume": 2,
        "serial": 6295543
      },
      {
        "at": "2021-09-30T13:24:57.570+08:00",
        "bid": 26.25,
        "ask": 26.3,
        "price": 26.25,
        "volume": 2,
        "serial": 6294781
      },
      {
        "at": "2021-09-30T13:24:56.696+08:00",
        "bid": 26.25,
        "ask": 26.3,
        "price": 26.25,
        "volume": 1,
        "serial": 6294300
      },
      {
        "at": "2021-09-30T13:24:53.651+08:00",
        "bid": 26.25,
        "ask": 26.3,
        "price": 26.25,
        "volume": 1,
        "serial": 6291991
      }
    ]
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
|  `dealts` | [[dealt object](#dealt-object)] | -  |

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

### dealt object
| Name | Type | Description |
|:--|:--|:--|
|  `at` | ISO 8601 | 此筆交易的成交時間 |
|  `bid` | number | 此筆交易的買進價 |
|  `ask` | number | 此筆交易的賣出價 |
|  `price` | number | 此筆交易的成交價 |
|  `volume` | number |  此筆交易的成交量 |
|  `serial` | number |  此筆交易的序號 |
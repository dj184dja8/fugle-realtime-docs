# VOLUMES

提供盤中個股即時分價量

```
GET /intraday/volumes
```

```
curl -X GET "https://api-dev.fugle.tw/realtime/v0.3/intraday/volumes?symbolId=2884&apiToken=demo" -H "accept: */*"
```

## Example

### request url
```
https://api.fugle.tw/realtime/v0.3/intraday/volumes?symbolId=2884&apiToken=demo
```

### parameters
| Name | Type | Required | Description |
|:--|:--|:--|:--|
|  `symbolId` | string | yes | 個股識別代碼 |
|  `apiToken` | string | yes | personal api token |
|  `oddLot` | string | no | 設置 true 回傳零股行情。預設值：false |

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
      "lastUpdatedAt": "2021-09-30T13:55:12.883+08:00"
    },
    "volumes": [
      {
        "price": 26.35,
        "volume": 503
      },
      {
        "price": 26.3,
        "volume": 8266
      },
      {
        "price": 26.25,
        "volume": 4223
      },
      {
        "price": 26.2,
        "volume": 4755
      },
      {
        "price": 26.15,
        "volume": 812
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
|  `info` | [[info object](#info-object)] | -  |
|  `volumes` | [[volumes object](#volumes-object)] | -  |


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


### volumes object
| Name     | Type   | Description |
|:-------- |:------ |:----------- |
| `price`  | string | 成交價      |
| `volume` | number | 成交量      |
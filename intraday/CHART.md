# CHART

提供盤中個股/指數 線圖時所需的各項即時資訊

```
GET /intraday/chart
```

```
curl -X GET "https://api.fugle.tw/realtime/v0.3/intraday/chart?symbolId=2884&apiToken=demo" -H "accept: */*"
```

## Example

### request url
```
https://api.fugle.tw/realtime/v0.3/intraday/chart?symbolId=2884&apiToken=demo
```

### websocket
```
wss://api.fugle.tw/realtime/v0.3/intraday/chart?symbolId=2884&apiToken=demo
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
      "lastUpdatedAt": "2021-09-30T09:05:00.000+08:00"
    },
    "chart": {
      "o": [
        26.35,
        26.25,
        26.25,
        26.25,
        26.25
      ],
      "h": [
        26.35,
        26.3,
        26.3,
        26.3,
        26.3
      ],
      "l": [
        26.25,
        26.25,
        26.25,
        26.25,
        26.25
      ],
      "c": [
        26.25,
        26.3,
        26.3,
        26.25,
        26.3
      ],
      "v": [
        893,
        48,
        40,
        231,
        117
      ],
      "t": [
        1632963660000,
        1632963720000,
        1632963780000,
        1632963840000,
        1632963900000
      ]
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
|  `chart` | [chart object](#chart-object) | -  |


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


### chart object
| Name | Type | Description |
|:--|:--|:--|
|  `o` | number | 此分鐘的開盤價 |
|  `h` | number | 此分鐘的最高價 |
|  `l` | number | 此分鐘的最低價 |
|  `c` | number | 此分鐘的收盤價 |
|  `v` | number | 此分鐘的成交量 (指數：金額；個股：張數；興櫃股票及零股：股數) |
|  `t` | number | Unix timestamp (每分鐘單位) |
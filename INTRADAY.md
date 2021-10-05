# Intraday

## Resource

| Resource  | Available endpoints | Description |
|:--|:--|:--|
|  [chart](./intraday/CHART.md) | `/intraday/chart` |  個股/指數 線圖時所需的各項即時資訊 |
|  [quote](./intraday/QUOTE.md) |  `/intraday/quote` | 取得 個股/指數 逐筆交易金額、狀態、統計資訊 |
|  [meta](./intraday/META.md) |  `/intraday/meta` | 取得 個股/指數 當日基本資訊 |
|  [dealts](./intraday/DEALTS.md) |  `/intraday/dealts` | 取得個股當日所有成交資訊 |
|  [volumes](./intraday/VOLUMES.md) |  `/intraday/volumes` | 提供盤中個股即時分價量 |

## Required Parameters
| Name | Type | Required | Description |
|:--|:--|:--|:--|
|  `symbolId` | string | yes | 個股、指數識別代碼 |
|  `apiToken` | string | yes | personal api token |

## Mode List

| Mode | Description |
|:--|:--|
| `twse-sem` | 上市 |
| `tpex-otc` | 上櫃 |
| `tpex-emg` | 興櫃 |
| `tpex-sem-oddlot` | 上市零股 |
| `tpex-otc-oddlot` | 上櫃零股 |

## Status codes
The following table gives an overview of how the API functions generally behave.

| Request type | Description |
|:--|:--|
| `GET` | Access one resource and return the result as JSON. |

| Request values | Description |
|:--|:--|
| `200` | Response Success |
| `400` | General purpose error, ex: <br/>  - invalid parameters <br/> - missing required parameters |
| `401` | Unauthorized |
| `403` | Rate limit or quota exceeded |
| `404` | Resource Not Found |


## Error Responses

### example
```json
{
  "apiVersion": "0.0.0",
  "error": {
    "code": 0,
    "message": "this is error message"
  }
}
```

### schema
| Name | Type | Description |
|:--|:--|:--|
|  `apiVersion` | string |  api version |
|  `error` | [error object](#error-object) |  - |

### error object
| Name | Type | Description |
|:--|:--|:--|
|  `code` | integer |  error code |
|  `message` | string | error message  |

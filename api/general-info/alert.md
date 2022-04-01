# 所有alert数量

## 描述
返回当前所有的Alert数量，不返回任何具体Alert(Label Record)，用于读取Alert 列表时分页

## Request
- Method: **GET**
- URL: `/general/alert`
- Headers: `Authorization: <Auth-Token>` 需要携带bearer token
- Body:

## Response
- Success Body (200):
```json
{
    "status": true,
    "message": "OK!",
    "errors": null,
    "data": {
        "alerts": 100,
        "total": 100000 // total number of label records
    }
}
```
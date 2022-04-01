# 在线Blackbox

## 描述
返回当前所有在线的Blackbox数量

## Request
- Method: **GET**
- URL: `/general/blackbox`
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
        "blackbox": 100,
        "total": 100000 // total number of label records
    }
}
```
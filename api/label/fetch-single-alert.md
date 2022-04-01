# 获取单个故障

## 描述
根据UUID获取一个Label Record的故障信息

## Request
- Method: **GET**
- URL: `/label/:id/alert`
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
       "alert": [
           {
               "timestamp": "DD-MM-YYYY", // ISO date and time,
               "failure": "lost connection",
           },
           ...
       ]
    }
}
```

- Error Body (400):
如果id不存在则返回错误
```json
{
    "status": false,
    "message": "Failed to process request",
    "errors": [
        "id not found"
    ],
    "data": {}
}
```
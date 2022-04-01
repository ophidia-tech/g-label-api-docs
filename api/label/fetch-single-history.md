# 获取单个历史

## 描述
根据UUID获取一个Label Record的历史记录

## Request
- Method: **GET**
- URL: `/label/:id/history`
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
       "history": [
           {
               "timestamp": "DD-MM-YYYY", // ISO date and time,
               "user": "John Smith",
               "action": "View the label",
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
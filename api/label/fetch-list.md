# 获取多个 (列表)

## 描述
获取label records的列表

## Request
- Method: **GET**
- URL: `/label`
- Headers: `Authorization: <Auth-Token>` 需要携带bearer token
- Body: 
```json
{
    "page": 10, // 第几页
    "numPerPage": 10 // 每页多少个
}
```

## Response
- Success Body (200):
```json
{
    "status": true,
    "message": "OK!",
    "errors": null,
    "data": {
       "labels": [
           {
               "studyNumber": "Some Text",
               "productName": "Some Text",
               "country": "Some Text",
               "createDate": "DD-MM-YYYY", // ISO date
               "expiryDate": "DD-MM-YYYY", // ISO date
               "status": "Pending Verification",
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
        "page is not valid",
        "page index is not valid"
    ],
    "data": {}
}
```
# 条件搜索

## 描述
根据内容搜索，需要完全匹配
## Request
- Method: **GET**
- URL: `/label`
- Headers: `Authorization: <Auth-Token>` 需要携带bearer token
- Body: 
```json
{
    "type": "list", // map or list
    "page": 10, // 第几页
    "numPerPage": 10, // 每页多少个
    "search": "text to search", // 搜索内容，optional,
    "filter": { //过滤，optional; filter 内容(4个)是一定要输入的
        "id": "Some Text", 
        "country": "United Kingdom",
        "status": "Ready",
        "labelType": "any", // 如果搜索所有则选any
    }
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
                "coordinates": {
                    "longitude": "-0.127758",
                    "latitude": "51.507351",
                },
           },
           ...
       ]
    }
}
```

- Error Body (400):
如果body错误则返回错误
```json
{
    "status": false,
    "message": "Failed to process request",
    "errors": [
        "page is missing",
        "page index is not valid"
    ],
    "data": {}
}
```
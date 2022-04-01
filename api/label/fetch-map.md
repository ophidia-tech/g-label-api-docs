# 获取多个 (地图)

## 描述
获取label records的地图列表

## Request
- Method: **GET**
- URL: `/label`
- Headers: `Authorization: <Auth-Token>` 需要携带bearer token
- Body: 
```json
{
    "type": "map", // map or list
    "scale": "70", // 70% (100 - 10)
    // 地图范围
    "lat": {
        "from": "51.507351",
        "to": "-0.127758",
    },
    "long": {
        "from": "51.507355",
        "to": "-0.127722",
    },
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
如果id不存在则返回错误
```json
{
    "status": false,
    "message": "Failed to process request",
    "errors": [
        "scale is not valid",
        "range is not valid"
    ],
    "data": {}
}
```
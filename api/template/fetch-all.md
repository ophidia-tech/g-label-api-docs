# 获取所有

## 描述
获取label records的列表

## Request
- Method: **GET**
- URL: `/template`
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
       "templates": [
           {
                "id": "7143dbaa-0316-4a66-a769-d97269d53701", // uuid v4
                "name": "Some Name",
           },
           ...
       ]
    }
}
```
# 更改

## 描述
更改一个Label Record

## Request
- Method: **PUT**
- URL: `/label/:id`
- Headers: `Authorization: <Auth-Token>` 需要携带bearer token
- Body:
```json
{
    "country": "United Kingdom",
    "expiryDate": "DD-MM-YYYY", // ISO date Format
    "dose": "Some Text",
    "routeOfAdministration": "Some Text",
    "storageCondition": "Some Text",
    "instructionOfUse": "Some Text",
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
        "id": "7143dbaa-0316-4a66-a769-d97269d53701", //v4 uuid: internal ID
    }
}
```

- Error Body (400):
如果json field不匹配DTO则返回错误
```json
{
    "status": false,
    "message": "Failed to process request",
    "errors": [
        "Key: 'LabelDTO.Dose' Error:Field validation for 'Dose' failed on the 'dose' tag"
    ],
    "data": {}
}
```

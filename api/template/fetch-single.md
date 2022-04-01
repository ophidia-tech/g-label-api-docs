# 获取单个

## 描述
根据UUID获取一个Label Template

## Request
- Method: **GET**
- URL: `/template/:id`
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
        "inputs": {
            "type":"种类",
            "country": "国家和地区",
            "studyIdentification": "Some Text",
            "productName": "Nom du Produit",
            "formulation": "Some Text",
            "studyIdentification": "Some Text",
            "lot": "Some Text",
            "expiryDate": "过期时间", 
            "dose": "δόση",
            "routeOfAdministration": "Some Text",
            "storageCondition": "Some Text",
            "instructionOfUse": "Some Text",
            "sponsorShortName": "Some Text",
            "treatmentNumber": "Some Text",
            "packNumber": "رقم العبوة",
            "internalGSKNumber": "Some Text",
        },
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
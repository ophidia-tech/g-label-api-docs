# 获取单个

## 描述
根据UUID获取一个Label Record

## Request
- Method: **GET**
- URL: `/label/:id`
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
       "inputs": {  // use all inputs to mock the preview
            "type":"Primary Label",
            "country": "United Kingdom",
            "studyIdentification": "Some Text",
            "productName": "Some Text",
            "formulation": "Some Text", // optional depend on the ticked box
            "studyIdentification": "Some Text",
            "lot": "Some Text",
            "expiryDate": "DD-MM-YYYY", // ISO date Format
            "dose": "Some Text",
            "routeOfAdministration": "Some Text",
            "storageCondition": "Some Text",
            "instructionOfUse": "Some Text",
            "sponsorShortName": "Some Text",
            "treatmentNumber": "Some Text",
            "packNumber": "Some Text",
            "internalGSKNumber": "Some Text",
       },
       "createDate": "DD-MM-YYYY", // ISO date Format
       "status": "attached",
       "vialId": "Some Text", // Hardware MAC address,
       "coordinates": {
           "longitude": "-0.127758",
           "latitude": "51.507351",
       },
       "temperature": "-20" // in centigrade
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

# 新建

## 描述
新建一个Label Template，对应label上的翻译，用json文件输入template

## Request
- Method: **POST**
- URL: `/template`
- Headers: `Authorization: <Auth-Token>` 需要携带bearer token
- Body:
内容必须支持unicode
```json
{
    "name": "Some Name",
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
        "packNumber": "Some Text",
        "internalGSKNumber": "Some Text",
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
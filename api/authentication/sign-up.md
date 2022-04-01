# 注册

## 描述
进行姓名、邮箱、国家、时区、手机号、密码注册登录 (手机号不是必填)

## Request
- Method: **POST**
- URL: `/auth/register`
- Headers:
- Body:
```json
{
    "email": "test@ophidia.com",
    "password": "password",
    "firstName":"Terry",
    "lastName":"Williams",
    "country":"United Kingdom", // from default country region List
    "timeZone": "GMT+1", // from default timezone List
    "mobile": "+447410000000"
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
        "id": 4,
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiNCIsImV4cCI6MTY4MDM3ODIxOSwiaWF0IjoxNjQ4ODQyMjE5LCJpc3MiOiJvcGhpZGlhIn0.pBLtRFWK-IZvRdJnzAGwZ6lPtrmV-G8ilPBYIKvPiOk"
    }
}
```
- Error Body (400):
```json
{
    "status": false,
    "message": "Failed to process request",
    "errors": [
        "Key: 'LoginDTO.Email' Error:Field validation for 'Email' failed on the 'email' tag"
    ],
    "data": {}
}
```
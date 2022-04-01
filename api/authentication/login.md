# 登陆

## 描述
邮箱 + 密码登陆

## Request
- Method: **POST**
- URL: `/auth/login`
- Headers:
- Body:
```json
{
    "email": "test@ophidia.com",
    "password": "password",
}
```

## Response
- Success Body (200):
如果成功，返回值一定会含有token和id其他data中的field不一定存在
```json
{
    "status": true,
    "message": "OK!",
    "errors": null,
    "data": {
        "id": 4,
        "name": "Test User",
        "email": "test@ophidia.com",
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
- Error Body (401):
```json
{
    "status": false,
    "message": "Please check again your credential",
    "errors": [
        "Invalid Credential"
    ],
    "data": {}
}
```
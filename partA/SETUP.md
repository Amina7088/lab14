# Part A — Setup

## Сонгосон API: DummyJSON

### Brief
DummyJSON нь үнэгүй, нээлттэй REST API бөгөөд хуурамч өгөгдөл (users, posts, products) буцаадаг.
CRUD үйлдэл бүгд дэмжигддэг бөгөөд JWT authentication-тай тул chain хийх дасгалд тохиромжтой.

### Base URL
```
https://dummyjson.com
```

### Authentication
JWT Bearer Token — `/auth/login` endpoint-оос username/password-аар token авна.

```json
{
  "username": "emilys",
  "password": "emilyspass"
}
```

Token-ыг environment variable-д хадгалж дараагийн request-үүдэд ашиглана:
```
Authorization: Bearer {{token}}
```

### Rate Limit
Байхгүй (үнэгүй tier-д хязгаарлалт бага)

### Документац
https://dummyjson.com/docs

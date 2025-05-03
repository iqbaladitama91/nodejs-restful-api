# User API Spec

## Regiter User API

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "pzn",
  "password": "rahasia",
  "name": "Muhammad Iqbal Aditama"
}
```

Response Body Success :

```json
{
  "data": {
    "username": "pzn",
    "name": "Muhammad Iqbal Aditama"
  }
}
```

Response Body Error :

```json
{
  "errors" : "Username already registered"
}
```

## Login User API

Endpoint : POST /api/users/login

Response Body :

```json
{
  "username" : "iqbaladitama",
  "password" : "rahasia"
}
```

Response Body Success:

```json
{
  "data": {
    "token": "unique token"
  }
}
```

Response Body Error:

```json
{
  "errors" : "Username or password wrong"
}
```

## Update User API

Endpoint PATCH /api/users/current

Response Body :

```json
{
  "name" : "new iqbal aditama", //optional
  "password" : "new password" //optional
}
```

Response Body Success:

```json
{
 "data": {
    "username": "pzn",
    "name": "new iqbal aditama"
  }
}
```

Response Body Error:

```json
{
  "errors" : "Name length max 100"
}
```

## Get User API

Endpoint : GET /api/users/current

Headers :
- Authorization : token

Response Body Success:

```json
{
 "data": {
    "username": "pzn",
    "name": "iqbal aditama"
  }
}
```

Response Body Error:

```json
{
  "errors" : "Unauthorized"
}
```

## Logout User API

Endpoint : DELETE /api/users/logout

Headers :
- Authorization : token


Response Body Success:

```json
{
 "data": "Logout success"
}
```

Response Body Error:

```json
{
  "errors" : "Unauthorized"
}
```


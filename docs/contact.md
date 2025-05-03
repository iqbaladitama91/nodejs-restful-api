# Contact API Spec

## Create Contact API

Endpoint : POST /api/contacts

Headers :

- Authorization : token

Request Body :

```json
{
  "firstName": "Eko",
  "lastName": "rahasia",
  "email": "ekorahasia@gmail.com"
}
```

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "firstName": "Eko",
    "lastName": "rahasia",
    "email": "ekorahasia@gmail.com",
    "phone": "981234798234"
  }
}
```

Response Body Error :

```json
{
  "errors": "email is not valid"
}
```

## Update Contact API

Endpoint : POST /api/contacts

Headers :

- Authorization : token

Response Body :

```json
{
  "firstName": "Eko",
  "lastName": "rahasia",
  "email": "ekorahasia@gmail.com",
  "phone": "981234798234"
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
  "errors": "Username or password wrong"
}
```

## Get Contact API

Endpoint GET /api/contacts/:id

Headers :

- Authorization : token

Response Body Success:

```json
{
  "data": {
    "id": 1,
    "firstName": "Eko",
    "lastName": "rahasia",
    "email": "ekorahasia@gmail.com",
    "phone": "981234798234"
  }
}
```

Response Body Error:

```json
{
  "errors": "Contact is not found"
}
```

## Search Contact API

Endpoint : GET /api/users/current

Headers :

- Authorization : token

Query params :

- name: Search by firstName or lastName, using like, optional
- email: Search by email using like, optional
- phone: Search by phone using like, optional
- page: number of page, default 1
- size: size per page, default 10

Response Body Success:

```json
{
  "data": [
    {
      "id": 1,
      "firstName": "Eko",
      "lastName": "rahasia",
      "email": "ekorahasia@gmail.com",
      "phone": "981234798234"
    },
    {
      "id": 2,
      "firstName": "Eko",
      "lastName": "rahasia",
      "email": "ekorahasia@gmail.com",
      "phone": "981234798234"
    }
  ],
  "pagination": {
    "page": 1,
    "totalPage": 3,
    "totalItem": 30
  }
}
```

Response Body Error:

```json
{
  "errors": "Unauthorized"
}
```

## Remove Contact API

Endpoint : DELETE /api/contacts/:id

Headers :

- Authorization : token

Response Body Success:

```json
{
  "data": "Delete success"
}
```

Response Body Error:

```json
{
  "errors": "Unauthorized"
}
```

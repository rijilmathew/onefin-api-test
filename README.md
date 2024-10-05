# Postman API Collection for User Login and Movie List

This repository contains a Postman collection that includes Three APIs: 
1. **Login API** to authenticate users.
2. **Movie API** to retrieve a paginated list of movies.
3. **Pagination nexturl api** to retrive nex  paginated list of moviews using url provided by movie api response 


## API 1: User Login

### Endpoint
`POST https://demo.onefin.in/api/v1/usermodule/login/`

### Sample Request Body
```json
{
  "username": "testuser",
  "password": "v^4!C%CQ94f0"
}

Sample Sucess Response

{
   "is_success": true,
   "data": {
       "token": "<Token to be sent for authentication of future requests>"
   }
}

Description

This API allows users to log in by providing their username and password. The response will contain an authentication token that is required for making authenticated requests to other APIs, such as the Movie API.



API 2: Get Movie List

Endpoint

GET https://demo.onefin.in/api/v1/maya/movies/

Headers

Authorization: Token <token obtained from the login API>
Sample Response

{
    "count": 45466,
    "next": "https://demo.onefin.in/api/v1/maya/movies/?page=2",
    "previous": null,
    "results": [
        {
            "title": "Queerama",
            "description": "50 years after decriminalisation of homosexuality in the UK, ...",
            "genres": "",
            "uuid": "57baf4f4-c9ef-4197-9e4f-acf04eae5b4d"
        },
        {
            "title": "Satana likuyushchiy",
            "description": "In a small town live two brothers, one a minister ...",
            "genres": "",
            "uuid": "163ce013-03e2-47e9-8afd-e7de7688c151"
        },
        ...
    ]
}
Description
This API returns a paginated list of movies, showing 10 movies at a time. You need to send an authentication token in the headers to access the movie list. The next field in the response contains a link for the next set of movies.

API 3: Get Paginated  Movie List
The next URL provided in the movie API response should be stored in the environment variable as nexturl.

Postman Collection
You can import the Postman collection and test these APIs. The Postman collection file is located in the repository.


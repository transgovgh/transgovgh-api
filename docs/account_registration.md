### Account signup
- Method: `POST`
- Endpoint: `https://api.example.org/api/v1.0/users/signup/`
  
- Request: ``[JSON Body]``

        {
        "email": "user@user.com",
        "username": "username",
        "password": "xxxxxxxx"
        }
  
  - Response: ``201 Created``


        {
        "email": "user@user.com",
        "username": "username",
        "token": "xxxxxxxxxxxxxxxxxxxxxx"
        }


### Account login
  - Method: `POST`

  - Endpoint: `https://api.example.org/api/v1.0/users/login/`
  
  - Request: ``[JSON Body]``

        {
        "username": "username",
        "password": "xxxxxxxx"
        }
  
  - Response: ``201 Created``

        {
        "email": "user@user.com",
        "username": "username",
        "token": "xxxxxxxxxxxxxxxxxx"
        }








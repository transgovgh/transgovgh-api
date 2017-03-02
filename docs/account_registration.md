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
        "id": 9,
        "auth_token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "email": "user@user.com",
        "username": "username",
        "first_name": "",
        "last_name": "",
        "profile": null
        }


### Account login
  - Method: `POST`

  - Endpoint: `https://api.example.org/api/v1.0/users/login/`
  
  - Request: ``[JSON Body]``

        {
        "username": "username",
        "password": "xxxxxxxx"
        }
  
  if the user has filled his/her profile, the profile object will be included else profile field will return null.

  - Response: ``201 Created``

        {
        "id": 1,
        "auth_token": "xxxxxxxxxxxxxxxxxxxx",
        "email": "xxxxx@xxxx.com",
        "username": "username",
        "first_name": "first name",
        "last_name": "last name",
        "profile": {
          "id": 1,
          "location": "location",
          "phone_number": 00000000,
          "fcm_id": ""
          }
        }








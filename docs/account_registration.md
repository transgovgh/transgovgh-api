### Account signup
`Endpoint: POST https://api.example.org/api/v1.0/users/signup/`
  
  ``Request: [JSON Body]``

    {
    "email": "user@user.com",
    "username": "username",
    "password": "xxxxxxxx"
    }
  
  ``Response: 201 Created``

    {
    "email": "user@user.com",
    "username": "username",
    "token": "xxxxxxxxxxxxxxxxxxxxxx"
    }


### Account login
`Endpoint: POST https://api.example.org/api/v1.0/users/login/`
  
  ``Request: [JSON Body]``

    {
    "username": "username",
    "password": "xxxxxxxx"
    }
  
  ``Response: 201 Created``

    {
    "email": "user@user.com",
    "username": "username",
    "token": "xxxxxxxxxxxxxxxxxx"
    }


### Update Profile
`Endpoint: POST https://api.example.org/v1.0/users/2/update-profile/0`
  
  ``Request: [JSON Body]``

    {
    "first_name":"Kelvin",
    "last_name": "Anyinatoe",
    "location": "Abeka",
    "phone_number": "0246424340"
    }


  ``Response: 201 Created``
    
    {
      "id": 2,
      "auth_token": "687a95d0bcefcec5278820fd6939e8d4291a372a",
      "email": "user@user.com",
      "username": "user",
      "first_name": "Kelvin",
      "last_name": "Anyinatoe",
      "profile": {
        "id": 2,
        "location": "Abeka",
        "phone_number": 246424340,
        "fcm_id": ""
      }
    }






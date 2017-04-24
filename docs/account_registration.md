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
          "auth_token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxx",
          "email": "xxxxxxx@gmail.com",
          "username": "kenmartey",
          "first_name": "Kennedy",
          "last_name": "Anyinatoe",
          "profile": {
            "id": 1,
            "region": {
              "id": 1,
              "region": "Greater Accra",
              "author": 1,
              "created_date": "2017-03-29T10:14:22.989213Z",
              "modified": "2017-03-29T10:14:22.989254Z"
            },
            "suburb": {
              "id": 1,
              "region": {
                "id": 1,
                "region": "Greater Accra",
                "author": 1,
                "created_date": "2017-03-29T10:14:22.989213Z",
                "modified": "2017-03-29T10:14:22.989254Z"
              },
              "suburb": "Abeka",
              "author": 1,
              "created_date": "2017-03-29T10:14:38.891566Z",
              "modified": "2017-03-29T10:14:38.891606Z"
            },
            "phone_number": "+233246424340",
            "profile_image": "https://xxxxxxxxxxxx.amazonxx.com/profile_image/profilepic.jpg",
            "fcm_id": ""
          },
          "firebase": null
        }








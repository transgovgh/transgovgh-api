### Update user account 
update user account with first name and and last name

- Endpoint: `https://api.example.org/v1.0/users/update-user-firstname-lastname/`

` This endpoint updates the user account with first name and last name

  - User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxxxxxxxxxxxxx"

  - Request: ``[JSON Body]``

        {
        "first_name": "first name",
        "last_name": "last name"
        }

- Response: ``201 Created``

          {
            "status_code": 201,
            "message": "Successfully added first name and last name",
            "result": {
              "id": 2,
              "auth_token": "687a95d0bcefcec5278820fd6939e8d4291a372a",
              "email": "user@user.com",
              "username": "user",
              "first_name": "Kennedy",
              "last_name": "Anyinatoe",
              "profile": {
                "id": 4,
                "location": "Dansoman",
                "phone_number": 246424340,
                "fcm_id": ""
              },
              "firebase": null
            }
          }

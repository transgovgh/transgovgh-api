
### Add Profile
- Method `POST`

- Endpoint: `https://api.example.org/v1.0/users/{userid}/add-profile/`

This enpoint adds location and phone number to user if it doesn't exist, and updates same fields: ``location`` and  ``phone number`` if it exists.
  
  - User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxxxxxxxxxxxxx"

  - Request: ``[JSON Body]``

        {
        "location": "Abeka",
        "phone_number": 0246424340
        }

- If it's first time adding ``location`` and ``phone number`` 

    - Response: ``201 Created``
      
              {
                "status_code": 201,
                "message": "You have added your location and phone number",
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


- If ``location`` and ``phone number`` already exist, it will update it

    - Response: ``201 Created``

            {
              "status_code": 201,
              "message": "You have updated your profile details "
            }

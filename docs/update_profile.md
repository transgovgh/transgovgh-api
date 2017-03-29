
### Add Profile
- Method `POST`

- Endpoint: `https://api.example.org/v1.0/users/add-profile/`

This enpoint adds region, suburb and phone number to user if it doesn't exist, and updates same fields: ``region`` , ``suburb`` and  ``phone number`` if it exists.
  
  - User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxxxxxxxxxxxxx"

  - Request: ``[JSON Body]``

        {
        "region": 1,
        "suburb": 1,
        "phone_number": "0246424340"
        }

- If it's first time adding ``region`` , ``suburb`` and ``phone number`` 

    - Response: ``201 Created``
      
              {
                "status_code": 201,
                "message": "You have added your location and phone number",
                "result": {
                  "id": 1,
                  "auth_token": "b15623ed0d3caaa1ad406033a3ba619af3f8ff88",
                  "email": "kenmartey89@gmail.com",
                  "username": "kenmartey",
                  "first_name": "Kennedy",
                  "last_name": "Anyinatoe",
                  "profile": {
                    "id": 9,
                    "region": "Greater Accra",
                    "suburb": "East Legon",
                    "phone_number": "0246424340",
                    "fcm_id": ""
                  },
                  "firebase": 9
                }
              }


- If ``region`` , ``suburb``  and ``phone number`` already exist, it will update it

    - Response: ``201 Created``

            {
              "status_code": 201,
              "message": "You have updated your profile details "
            }

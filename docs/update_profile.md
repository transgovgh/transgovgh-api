
### Add Profile
- Method `POST`

- Endpoint: `https://api.example.org/v1.0/users/add-profile/`

This enpoint adds region, suburb, phone number and profile_image to user if it doesn't exist, and updates same fields: ``region`` , ``suburb``, ``phone number`` and ``profile_image`` if it exists.
  
  - User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxxxxxxxxxxxxx"

  - Request: ``[JSON Body]``

  - Note: ``profile_image`` are is a file field

        {
        "region": 1,
        "suburb": 1,
        "phone_number": "0246424340",
        "profile_image": "/media/images/profile-image.jpg"
        }

- If it's first time adding ``region`` , ``suburb``, ``phone number`` and ``profile_image`

    - Response: ``201 Created``
      
              {
                "status_code": 201,
                "message": "You have added your location and phone number",
                "result": {
                  "id": 1,
                  "auth_token": "806215e74ce5640a86136b462115301f846023d7",
                  "email": "kenmartey89@gmail.com",
                  "username": "kenmartey",
                  "first_name": "",
                  "last_name": "",
                  "profile": {
                    "id": 2,
                    "region": {
                      "id": 1,
                      "region": "Greater Accra",
                      "author": 1,
                      "created_date": "2017-03-29T09:42:47.763945Z",
                      "modified": "2017-03-29T09:42:47.763970Z"
                    },
                    "suburb": {
                      "id": 1,
                      "region": {
                        "id": 1,
                        "region": "Greater Accra",
                        "author": 1,
                        "created_date": "2017-03-29T09:42:47.763945Z",
                        "modified": "2017-03-29T09:42:47.763970Z"
                      },
                      "suburb": "Abeka",
                      "author": 1,
                      "created_date": "2017-03-29T09:43:07.583824Z",
                      "modified": "2017-03-29T09:43:07.583849Z"
                    },
                    "phone_number": "0246424340",
                    "profile_image": "/media/profile_image/profile.jpg",
                    "fcm_id": ""
                  },
                  "firebase": null
                }
              }


- If ``region`` , ``suburb``, ``phone number`` and ``profile_image` already exist, it will update it

    - Response: ``201 Created``

            {
              "status_code": 201,
              "message": "You have added your location and phone number",
              "result": {
                "id": 1,
                "auth_token": "806215e74ce5640a86136b462115301f846023d7",
                "email": "kenmartey89@gmail.com",
                "username": "kenmartey",
                "first_name": "",
                "last_name": "",
                "profile": {
                  "id": 2,
                  "region": {
                    "id": 1,
                    "region": "Greater Accra",
                    "author": 1,
                    "created_date": "2017-03-29T09:42:47.763945Z",
                    "modified": "2017-03-29T09:42:47.763970Z"
                  },
                  "suburb": {
                    "id": 1,
                    "region": {
                      "id": 1,
                      "region": "Greater Accra",
                      "author": 1,
                      "created_date": "2017-03-29T09:42:47.763945Z",
                      "modified": "2017-03-29T09:42:47.763970Z"
                    },
                    "suburb": "Abeka",
                    "author": 1,
                    "created_date": "2017-03-29T09:43:07.583824Z",
                    "modified": "2017-03-29T09:43:07.583849Z"
                  },
                  "phone_number": "0246424340",
                  "profile_image": "/media/profile_image/profile.jpg",
                  "fcm_id": ""
                },
                "firebase": null
              }
            }

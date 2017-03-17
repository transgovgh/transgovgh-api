### Update FCM id

Firebase Cloud Messaging (FCM) is meant for sending messages to users. FCM id field will be used to store Firebase key per user to enable them receive notifications on any update in the app.

- Method: `POST`

- Endpoint: `https://api.example.org/api/v1.0/users/update-fcm/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"

  - Request ``[JSON Body]``

         {
         "fcm_id": "xxxxxxxxxxxxxxxxxxxxxxxxx"
         } 

 - Response: ``201 Created``

          {
            "id": 8,
            "fcm_id": "xxxxxxxxxxxxxxxxxxxxxxxxx",
            "user": 1
          }
